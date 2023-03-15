# Investigating the TMDb Movies Dataset
## by Harnex Kakandelwa


## Dataset
This dataset contains information about movies collected from the movies database, TMDb. The data provides information related to the budget, revenue, popularity, votes, directors, studios, release dates and genres of the movies among others. The dataset has information for 10,000 movies, covering over four decades. Additional information about the dataset can be found at the original data page on <a href="https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata?select=tmdb_5000_movies.csv">Kaggle</a>.

For this project, I wanted to find out what movie runtimes and movie ratings are associated with high revenue. I also explored how revenue from movies has changed over time and whether newer (2000s) movies are generating more revenue than older (90s) movies.

Before conducting the analysis, I resolved a few tidiness and quality issues in the data. The issues resolved include the following:
* Since I wanted to work with only unique movies in the data, duplicates were deleted
* The minimum value for movie `runtime` was 0, which shows that some movies had 0 length. This is unusual and not appropriate for the investigation. Therefore, to analyze runtime, a new dataframe was created, which did not have values of 0 for `runtime`
* The association between movie rating and revenue was analyzed by creating a new column with bins for different values of vote_average
* The association between runtime and revenue was analyzed by creating a new column with bins for different values of runtime


## Summary of Findings
* On average, it seems that movies that have runtimes in the range of 180 minutes to 300 minutes are associated with higher revenue than shorter or longer movies.
* Movies with a vote average above 5 are associated with a higher level of revenue than movies with lower ratings.
* On average, movie revenues plummeted in the mid 1960's before reaching a peak in the 1970's but dropped in the 1980's and were on a steady decline into the 2000's.


## Limitations
* In this analysis, an assumption was made that runtime is in minutes although it is not explicitly stated any where in the dataset-related documentation. This is a limitation because it is also possible that some of the runtime values would have been in hours (for example, the really small values) or seconds (for example, the really large values).
* It is not clear whether all the revenue values in the dataset are in the same currency, which would make the comparisons across different variables difficult. Nonetheless, this analysis assumes that all the revenue values are in the same currency.

## Further research
Since most of the movies that have runtimes in the range of 180 minutes to 300 minutes seem to be associated with higher revenues on average, it would be interesting to investigate what genres make up most of the movies in this range. Similarly, further investigation can be conducted on what genres attract better ratings and thus associated with higher levels of revenue as per the findings in this investigation.