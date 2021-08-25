# Explore Weather Trends

## Purpose
This project from Udacity's Data Analyst Nanodegree Program analyzes local and global temperature data and compares the temperature trends in selected cities with overall global temperature trends.

## Explore_Weather_Trends.ipynb
Results of an analysis are presented in the Pyton Jupyter notebook. Best rendering of pdf from ipynb provides jupyter.org.

## References
- [Udacity: Project Instructions](https://classroom.udacity.com/nanodegrees/nd002/parts/93426fc7-0e68-4957-b16b-9fde38776c26/modules/6cfbf770-e84f-4cb7-be34-2ae3e04b42a6/lessons/d551938c-d004-4801-a269-4b8dd784cc3b/project)
- [Udacity: Project Rubrics](https://review.udacity.com/#!/rubrics/1125/view)
- [Udacity: Project FAQ](https://sites.google.com/udacity.com/data-analyst-project-1/home)
- [CarbonBrief Explainer: How do scientists measure global temperature?](https://www.carbonbrief.org/explainer-how-do-scientists-measure-global-temperature)
- [Udacity: Project Submission Review](https://review.udacity.com/?utm_campaign=ret_000_auto_ndxxx_submission-reviewed&utm_source=blueshift&utm_medium=email&utm_content=reviewsapp-submission-reviewed&bsft_clkid=417ba2b2-348a-4ffb-ae78-a8ba97adda3b&bsft_uid=cdc7152a-1404-4c6c-a86f-5d67acbdf89a&bsft_mid=35dc52c4-9876-4cf8-9346-643ddceb6003&bsft_eid=6f154690-7543-4582-9be7-e397af208dbd&bsft_txnid=a580e9fb-68e7-435e-b4dd-bc62e7557ca5&bsft_mime_type=html&bsft_ek=2021-08-25T07%3A52%3A48Z&bsft_aaid=8d7e276e-4a10-41b2-8868-423fe96dd6b2&bsft_lx=2&bsft_tv=5#!/reviews/3122246)


## Appendix
**Moving averages in Pandas**. A code snippet from the concomitant exercise:
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
