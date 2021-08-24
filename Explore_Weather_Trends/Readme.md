# Explore Weather Trends

## Purpose
An introductory project from Udacity's Data Analyst Nanodegree Program analyzes local and global temperature data and compares the temperature trends in selected cities with overall global temperature trends.

## Dataset
There are three tables in the database:
- `city_list` - This contains a list of cities and countries in the database. Look through them in order to find the city nearest to you.
- `city_data` - This contains the average temperatures for each city by year (ºC).
- `global_data` - This contains the average global temperatures by year (ºC).

Data for analysis is extracted using the following SQL query:

```
SELECT  city.year,
        city.city,
        city.avg_temp as city_avg_temp,
        global.avg_temp as glob_avg_temp
FROM city_data city, global_data global
WHERE  city.year = global.year AND
       city in ('Prague', 'Johannesburg', 'New York', 
                'Shanghai', 'Sydney', 'Rio De Janeiro')
```

## Analysis

## Results

## References
- [Udacity: Project Instructions](https://classroom.udacity.com/nanodegrees/nd002/parts/93426fc7-0e68-4957-b16b-9fde38776c26/modules/6cfbf770-e84f-4cb7-be34-2ae3e04b42a6/lessons/d551938c-d004-4801-a269-4b8dd784cc3b/project)
- [Udacity: Project Rubrics](https://review.udacity.com/#!/rubrics/1125/view)
- [Udacity: Project FAQ](https://sites.google.com/udacity.com/data-analyst-project-1/home)
- [CarbonBrief Explainer: How do scientists measure global temperature?](https://www.carbonbrief.org/explainer-how-do-scientists-measure-global-temperature)


## Appendix
**Moving averages in Pandas**. A code snippet from the exercise:
```
! curl https://video.udacity-data.com/topher/2017/September/59b0650b_moving-average-exercise/moving-average-exercise.csv --output moving-average-exercise.csv
sales = pd.read_csv('moving-average-exercise.csv', index_col='Date')
sales.Sales = sales.Sales.apply(lambda s: int(s.replace(',', '')))
sales.rolling(14).mean().iloc[75:80]

                Sales
Date	
3/17/2009	9980.785714
3/18/2009	9998.571429
3/19/2009	9981.071429
3/20/2009	10007.214286
3/21/2009	10069.642857

```
<!--
SELECT *
FROM city_list
WHERE city in ('Prague', 'Johannesburg', 'New York', 
               'Shanghai', 'Sydney', 'Rio De Janeiro')
-->
