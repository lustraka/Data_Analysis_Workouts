# Data Visualization Project's Exercises
## Diamond Case Study
- [Example_Project_ipynb](https://cdn.jsdelivr.net/gh/lustraka/Data_Analysis_Workouts@blob/main/Communicate_Data_Findings/SandBox/Example_Project_Diamonds_Part1.html)
- [Example_Project_slides](https://github.com/lustraka/Data_Analysis_Workouts/blob/main/Communicate_Data_Findings/SandBox/Example_Project_Diamonds_Part2.slides.html)

## Bar Chart using Seaborn
```
seaborn.countplot(*, x=None, y=None, data=None, order=None, orient=None, color=None)
```
```python
# The `color_palette()` returns the the current / default palette as a list of RGB tuples. 
# Each tuple consists of three digits specifying the red, green, and blue channel values to specify a color. 
# Choose the first tuple of RGB colors to reduce unnecessary distractions
base_color = sb.color_palette()[0]

# Dynamic-ordering the bars
# The order of the display of the bars can be computed with the following logic.
# Count the frequency of each unique value in the 'generation_id' column, and sort it in descending order
# Returns a Series
freq = pokemon['generation_id'].value_counts()

# Get the indexes of the Series
gen_order = freq.index

# Plot the bar chart in the decreasing order of the frequency of the `generation_id`
sb.countplot(data=pokemon, x='generation_id', color=base_color, order=gen_order);

# Use xticks to rotate the category labels (not axes) counter-clockwise
plt.xticks(rotation=90)
```
> **Additional Variation** - Refer to the `CategoricalDtype` to convert the column into an ordered categorical data type. By default, pandas reads in string data as object types, and will plot the bars in the order in which the unique values were seen. By converting the data into an ordered type, the order of categories becomes innate to the feature, and we won't need to specify an "order" parameter each time it's required in a plot.

## Pie (& Donut) Chart
```
matplotlib.pyplot.pie(x_data, labels, colors, startangle, counterclock, wedgeprops)
```

## Histograms
### Pyplot
```
matplotlib.pyplot.hist(x, bins)
matplotlib.pyplot.hist(data, x, bins)
```
### Seaborn
See [Seaborn: Visualizing distributions of data](https://seaborn.pydata.org/tutorial/distributions.html) tutorial to learn about
- choosing the bin size,
- conditioning on other variables,
- normalized histogram statistics,
- kernel density estimation (kde),
- empirical cumulative distributions,
- visualizing bivariate distributions,
- [distribution vizualization in other settings](https://seaborn.pydata.org/tutorial/distributions.html#distribution-visualization-in-other-settings)
- plotting many distributions (sns.pairplot())
```
seaborn.distplot(Series, bins, kde, hist_kws)
seaborn.displot(data, x)
seaborn.histplot(data, x)
seaborn.kdeplot()
```

## Plot Relative Frequencies Pattern
```python
# Define a function
def plot_top_rel_freq(data, title, top=None, nobs=None):
  """Plot `top` values the `data` series.
  
  Args:
     data - a pd.Series with counts to plot
     title - a chart's title ({} displays a number of categories)
     top - if None, plot all categories
     nobs - if None, use `data.sum()`"""
  
  def set_step(step):
    """Set nicely rounded step size."""
    lg = -1*np.log10(step)
    if lg > 0.1:
      return round(step, round(lg))
    else:
      return round(step, -1)
  
  # Choose the first tuple of RGB colors to reduce distraction
  base_color = sns.color_palette()[0]

  # Check the order of values
  data = data.sort_values(ascending=False)

  # If top == None, plot all observations.
  if top == None or top > data.shape[0]:
    top = data.shape[0]
  
  # If nobs == None, use data.sum()
  if nobs == None:
    nobs = data.sum()
  
  # Compute the lenght of the longest bar in terms of proportion
  max_prop = data.iloc[0] / nobs
  # Produce a set of evenly spaced proportioned values
  tick_props = np.arange(0, max_prop, set_step(max_prop/5))
  # Create tick labels
  tick_names = [f'{v:.1%}' for v in tick_props]

  fig, ax = plt.subplots(figsize=(6.4, 4.8))
  ax = sns.barplot(x=data[:top].values, y=data[:top].index, color=base_color)
  # Change tick locations and labels
  plt.xticks(tick_props * nobs, tick_names)

  # Print the proportion text on the bars
  for i in range(top):
      # Read count
      count = data.iloc[i]
      # Convert count into a percentage, and then into string
      pct_count = f'{count/nobs:.1%}'
      # Print the string value on the bar
      plt.text(count+round(data[0]/100), i, pct_count, va='center')

  # Render the chart
  left, right = plt.xlim()
  plt.xlim(left, right+round(data[0]/15))
  ax.set_title(title.format(top))

  return None
```
