# Data Visualization Project's Exercises
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

### Plot Relative Frequencies Pattern
```python
# Initialize variables
df = dataframe
variable = variable
title = 'Relative Frequency of ...'

def plot_rel_freq(df, variable, title):
  """Plots a relative frequency bar chart for a `variable` in a dataframe `df`."""

  # Assign counts of variable values
  var_counts = df[variable].value_counts()
  # var_counts.head()
  # Assign sum of values
  n_val = var_counts.sum()

  # Compute the lenght fo the longest bar in terms of proportion
  max_prop = var_counts[0] / n_val
  # Produce a set of evenly spaced proportioned values
  tick_props = np.arange(0, max_prop, 0.02)
  # Create tick labels
  tick_names = [f'{v:.0%}' for v in tick_props]
  # Check ticks
  # print('max_prop = ', max_prop)
  # print('tick_props = ', tick_props)
  # print('tick_names = ', tick_names)

  sb.countplot(data=df, y=variable, color=base_color, order=var_counts.index)
  # Change tick locations and labels
  plt.xticks(tick_props * n_val, tick_names)

  # Print the proportion text on the bars
  for i in range(var_counts.shape[0]):
      # Read count
      count = var_counts[i]
      # Convert count into a percentage, and then into string
      pct_count = f'{count/n_val:.1%}'
      # Print the string value on the bar
      plt.text(count+1, i, pct_count, va='center')
      
  left, right = plt.xlim()
  plt.xlim(left, right+10)
  plt.xlabel('relative count')
  plt.title(title)
  plt.show()

plot_rel_freq(df, variable, title)
```
