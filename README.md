# Movie-Studio-Analysis

#### Objective
This project aimed to analyze data found at: https://www.kaggle.com/carolzhangdc/imdb-5000-movie-dataset to look for features that a movie studio could use when planning their future porjects to increase the liklihood of them being very profitable.

#### Process (in progress)
After uploading the data to python, the first step was to look more carefully at what information was in it.  I did this analysis with the help of a profiling report created using the pandas-profiling package (https://pandas-profiling.github.io/pandas-profiling/docs/master/index.html). This report makes it very easy to do a quick visual analysis of what each attribute contains.  The report provides information about the range of each variable and the percentage of values that are missing or distinct.  It also creates a bar graph and warnings for properties of the attribute that might cause issues during analysis. In addition, the report provides several different correlation matrices showing the amount of correlation between various variables.

This is what I observed on my first look through the data:

* About half of the varaiables contained information that could be used to plan future productions. 
* The other half of the information was about things that studios would have little or no control over, such as the number of facebook likes or reviewer on imdb.
* Some of the variables, like director and actor, had a lot of different possible values.  This could make it more difficult to use with Machine Learning algorithms.
* The first movie in the database was from 1916.  Movies that are from far in the past might not be as good at helping to predict future movie sales.
* Data was heavily scewed towards color movies, english language and movies made in the US. As most movies are made in color now, this variable could probably be dropped. Language and country data would either need some processing before use or to drop them as well.
* Most of the data did not have missing values. Unfortunately, budget and gross, two of the more important ones for this analysis had a high percentage of missing values.
* Very few of the values had normal distribution.  Some of this was likely due the changes in technology over time and inflation.
* Many of the values had high correlations between them. Some of this was also likely due to changes over time.
* Both budget and gross had an extremely wide spread.  Part of this was probably due to inflation. Adjusting amounts for inflation might help with this to some extent.



I found inflation data at: https://data.worldbank.org/indicator/FP.CPI.TOTL.ZG
