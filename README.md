# Movie-Studio-Analysis

#### Objective
This project aimed to analyze data found at: https://www.kaggle.com/carolzhangdc/imdb-5000-movie-dataset to determine what "factors go into making a successful film". For this project, I have defined a successful film as a film that is in the top 25% of profitability for the year.
#### Process (in progress)
After uploading the data to python, the first step was to look more carefully at what information was in it.  I did this analysis with the help of a profiling report created using the pandas-profiling package (https://pandas-profiling.github.io/pandas-profiling/docs/master/index.html). This report makes it very easy to do a quick visual analysis of what each attribute contains.  The report provides information about the range of each variable and the percentage of values that are missing or distinct.  It also creates a bar graph and warnings for properties of the attribute that might cause issues during analysis. In addition, the report provides several different correlation matrices showing the amount of correlation between various variables.

##### This is what I observed on my first look through the data:

* About half of the variables contained information that studios had direct control over in planning future productions. 
* The other half of the information was about things that studios would have little or no control over, such as the number of facebook likes or reviewer on imdb.  However, this information could possibly be used when choosing actors or directors for a movie.
* Some of the variables, like director and actor, had a lot of different possible values.  These could be more difficult to use with Machine Learning algorithms. It might be necessary to look at a smaller set of data if this information is going to be used.  For example, including only movies by directors who have made at least 5 movies. 
* The first movie in the database was from 1916.  Movies that are from far in the past might not be as good at helping to predict future movie sales.  Perhaps looking at movies only in the more recent past might give better results.
* Data was heavily scewed towards color movies, english language and movies made in the US. As most movies are made in color now, the variable color could probably be dropped. Language and country data will either need some pre-processing before use to reduce the imbalance or they will also need to dropped.
* Most of the data did not have missing values. Unfortunately, budget and gross, two of the more important ones for this analysis had a high percentage of missing values.  In addition, many of the values are referring to different information.  Some values refer to total gross US and Canada sales, while others refer only to the opening weekend. Reobtaining this information and ensuring it all refers to the same type of information would give more valid results.
* Very few of the values had normal distribution.  Some of this was likely due the changes in technology over time and inflation.
* Many of the values had high correlations between them. Some of this, for example the correlation betwen year and facebook likes, was also likely due to changes over time.
* Both budget and gross had an extremely wide distribution.  Part of this was probably due to inflation. Adjusting amounts for inflation might help with this to some extent.

##### Questions to Investigate

1. Is there a correlation between particular genres and profits?
2. Is there a correlation between content rating and profits?
3. Are some genres more profitable for specific content ratings?
4. Does an increase in the number of Facebook likes for directors or actors correlate with an increase in profits?
5. Is being in or directing a larger number of movies correlated with more profits?
6. Are some topics correlated with more profits?

I found inflation data at: https://data.worldbank.org/indicator/FP.CPI.TOTL.ZG
