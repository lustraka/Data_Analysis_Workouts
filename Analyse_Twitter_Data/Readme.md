# Wrangle and Analyze WeRateDogs Data

![WeRateDogsPhotp](https://cdn10.bostonmagazine.com/wp-content/uploads/sites/2/2017/04/WeRateDogs.jpg)

*Provided by WeRateDogs*
## Introduction
The purpose of this project is to wrangle and analyze data from WeRateDogs Twitter archive.

## Assess Data
### Create an Extended Info Table

```python
# Copy rows of pd.info () to this multiline string
info = """"""

rows = info.split('\n')

# Show positions of columns
for idx, letter in enumerate(rows[0]):
  print(idx, letter)

# Print the header of a table
print('| # | Variable | Non-Null | Nunique | Dtype | Notes |')
print('|---|----------|----------|---------|-------|-------|')

# Print the rows (but adjust slicing parameters beforehand)
for row in rows:
  print(f'| {row[:4].strip()} | {row[5:14].strip()} | {row[15:19].strip()} | | {row[31:].strip()} | |')
```
## Clean Data
| Define (Design) | Code (Execute) | Test (Evaluate) |
| --- | --- | --- |
| Add missing observations | [pd.concat()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.concat.html) | df.shape |
| Check computation or impute | df.nVarY = f(df.nVarX1, ..., df.nVarP) | assert statement with df.all().all() |
| Extract catergorical variable | [pd.Series.str.extract()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.str.extract.html), [pythex.org](https://pythex.org/), [regex_cheatsheet](https://learnbyexample.github.io/python-regex-cheatsheet/#re-module-functions), [df.drop()](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.drop.html) | df.info(), df.sample() |
| Unpivot a dataframe | [pd.melt()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.melt.html), [pd.Series.str.split()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.str.split.html) | df.head() |
| Add new variables; Consolidate variables in multiple data sets | [df.merge()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.merge.html), [df.join()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.join.html) | df.head() |
| Convert dtype of a variable | [df.astype()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.astype.html), [pd.to_datetime()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.to_datetime.html) | df.info(), df.head() |
| Replace an incorrect value | [df.replace()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.replace.html), [df.where()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.where.html), [df.at()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.at.html) | df.query() |
| Transform values of a variable |  [df.apply()](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.apply.html)| df.query(), df.value_counts() |
| Remove incorrect observation | [Indexing and selecting data](https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html) | |
| | | |

```python
# Object_ID should be the only duplicate column in case of multiple data sets
all_columns = pd.Series(list(df1) + list(df2) + list(dfn))
all_columns[all_columns.duplicated()]
```

## Store Data
### Storing raw data
Gathering data via the Twitter API requires about half of an hour. To iterate easily, store and load data using **SQLAlchemy**:

```python
# Store dataframes for further processing
from sqlalchemy import create_engine

# Create SQLAlchemy engine and empty database
engine = create_engine('sqlite:///weratedogsdata.db')

# Store dataframes in database
dfa.to_sql('dba', engine, index=False)
dfi.to_sql('dbi', engine, index=False)
dft.to_sql('dbt', engine, index=False)

# Upload the file to GitHub !
```

```python
# Store dataframes for further processing
from sqlalchemy import create_engine

# Upload the database from GitHub
url_db = 'https://github.com/lustraka/Data_Analysis_Workouts/blob/main/Analyse_Twitter_Data/weratedogsdata.db?raw=true'
r = requests.get(url_db)
with open('weratedogsdata.db', 'wb') as file:
  file.write(r.content)

# Create SQLAlchemy engine and connect to the database
engine = create_engine('sqlite:///weratedogsdata.db')

# Read dataframes from SQlite database
dfa = pd.read_sql('SELECT * FROM dba', engine)
dfi = pd.read_sql('SELECT * FROM dbi', engine)
dft = pd.read_sql('SELECT * FROM dbt', engine)
```
### Restoring clean data
```python
# Store dataframes for further processing
from sqlalchemy import create_engine

# Upload the database from GitHub
url_db = 'https://github.com/lustraka/Data_Analysis_Workouts/blob/main/Analyse_Twitter_Data/weratedogsdata_clean.db?raw=true'
r = requests.get(url_db)
with open('weratedogsdata_clean.db', 'wb') as file:
  file.write(r.content)

# Create SQLAlchemy engine and connect to the database
engine = create_engine('sqlite:///weratedogsdata_clean.db')

# Read dataframes from SQlite database
df_clean = pd.read_sql('SELECT * FROM df_clean', engine)
df_clean.shape
```

## Report Insights
[StackOverflow: How to hide code from cells in ipython notebook visualized with nbviewer?](https://stackoverflow.com/questions/27934885/how-to-hide-code-from-cells-in-ipython-notebook-visualized-with-nbviewer)
```
jupyter nbconvert --to html --TemplateExporter.exclude_input=True act_report.ipynb 
```
[StackOverflow: ipython notebook align table to the left of cell](https://stackoverflow.com/questions/21892570/ipython-notebook-align-table-to-the-left-of-cell)
```python
%%html
<style>
table {float:left}
</style>
```
or
```python
from IPython.core.display import HTML
table_css = 'table {align:left;display:block} '
HTML('<style>{}</style>'.format(table_css))
```

## References
- [Udacity: Project Overview](https://classroom.udacity.com/nanodegrees/nd002/parts/cd0015/modules/0d74f2b3-e708-4fe7-b07e-6548d45e491d/lessons/a9596390-9691-4891-9a86-1d6044976f09/concepts/48566cfd-e9c5-4b49-aaff-f63c16672b0e)
- [Udacity: Project Rubric](https://review.udacity.com/#!/rubrics/1136/view)
- [Twitter: WeRateDogs @dog_rates](https://twitter.com/dog_rates)
- [Wikipedia: WeRateDogs](https://en.wikipedia.org/wiki/WeRateDogs)
- [BostonMagazine: WeRateDogs Is Coming to Cambridge](https://www.bostonmagazine.com/arts-entertainment/2017/04/18/dog-rates-mit/)
