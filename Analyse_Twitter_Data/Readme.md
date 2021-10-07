# Wrangle and Analyze WeRateDogs Data

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

## Store Data
### Storing raw data
Gathering data via the Twitter API requires about half of an hour. To iterate easily, store and load data using **SQLAlchemy**:

```python
# Store dataframes for further processing
# Import dependencies
from sqlalchemy import create_engine
# Create SQLAlchemy Engine and empty database
engine = create_engine('sqlite:///weratedogsdata.db')
# Store dataframes in database
dfa.to_sql('dba', engine, index=False)
dfi.to_sql('dbi', engine, index=False)
dft.to_sql('dbt', engine, index=False)
```

```python
# Download the database
url_db = 'https://github.com/lustraka/Data_Analysis_Workouts/blob/main/Analyse_Twitter_Data/weratedogsdata.db?raw=true'
r = requests.get(url_db)
with open('weratedogsdata.db', 'wb') as file:
  file.write(r.content)

from sqlalchemy import create_engine
# Create SQLAlchemy Engine and connect to the database
engine = create_engine('sqlite:///weratedogsdata.db')

# Read dataframes from SQlite database
dfa = pd.read_sql('SELECT * FROM dba', engine)
dfi = pd.read_sql('SELECT * FROM dbi', engine)
dft = pd.read_sql('SELECT * FROM dbt', engine)
```

## References
- [Udacity: Project Overview](https://classroom.udacity.com/nanodegrees/nd002/parts/cd0015/modules/0d74f2b3-e708-4fe7-b07e-6548d45e491d/lessons/a9596390-9691-4891-9a86-1d6044976f09/concepts/48566cfd-e9c5-4b49-aaff-f63c16672b0e)
- [Udacity: Project Rubric](https://review.udacity.com/#!/rubrics/1136/view)
