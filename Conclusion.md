# Conclusion/Recommendation
---
*By Ihza Gonzales*

## Conclusion

There are three machine learning models utilized throughout the project. These models are VAR model, voting regressor, and K-means cluster. For each model, the appropriate dataset had to be obtained either by webscraping or downloading an established dataset. There are 393 batters with a total of 14 stats each. There are 410 pitchers with a total of 10 stats each. The salaries of each player was also included among the data. 

The first model is VAR model. This is a Vector Auto Regression model which deals with multivariate time series. This model used the game log stats of players from 2018 - 2020 to forecast stats for next season. The RMSE for batter's statistics are around one for discrete variables. The continuous variables had an RMSE around 0.05. The RMSE for pitcher's statistics were a bit more variable with some stats having an RMSE of 2. Though the RMSE for both batters and pitchers are low, some stats with a difference of 1 can mean a lot. For instance, a pitcher stats of wins(W) having that difference of 1 can be a big deal to a player who do not usually start a game. The forecasted stats are also tested on what would be a third of the mlb season. The more games that are predicted the less accurate the model becomes and the model ends up predicting the mean of the stats. 

The second model is the voting regressor. The models used for this are adaBoost regressor, ridge, lasso, and elastic net to predict the salary of players. The historical data from 1985 to 2016 of salaries and stats of players that were acquired from SeanLahman.com was used. The stats of the pitcher and batter were used to predict the salary. For batters, a R2 of train is 0.096 and a R2 of test is 0.074. This is very low R2 which most likely due to the fact that there was not many features to predict with. Using polynomial features was tried but the difference between the train and test R2 was very great and still had a low train R2. In this model the train and test had very close R2 which is more desirable. The RMSE of batters was 3.7 million which seems a great difference but some players are making 36 million. Another reason this RMSE might be acceptable is that some players who are all star caliber players still have a "rookie" salary. The same can be said about the pitchers which have a train R2 of 0.128 and test R2 of 0.068. The RMSE is 3 million.

The last model is a K-Means cluster which is an unsupervised learning. This was used to cluster the batters and pitchers. The reason this step was taken is to help strengthen the recommendation by adding this as a feature in addition to the stats of the players. The silhouette score is to tell how far apart the clusters are from each other. The closer the silhoutte score is to 1 the further apart is the clusters from each other. The batter silhouette score was 0.225 and for pitchers it was 0.276. The amount of clusters used is 5 for each. After having tested how many clusters produced the best silhouette score, five clusters ended up being the best. 

To showcase the recommender system, a Flask app was made. A user can type a player name and a recommendation of 10 similar players along with their predicted stats and salary for next season will be displayed.

## Recommendation

As for answering the problem statement of being able to create a baseball player recommender that will also display forecasted stats and predicted salary, yes is the answer. The recommendation itself seemed to perform well as far as my knowledge of baseball players. The recommendations given for players would be ones that makes sense. As for forecasting the stats of players, the evaluation of forecast were good. But the more games predicted the worse the model could possibly be. The predictions for the salary did not fare well. They could simply be used as a basis for how much that player should make. This is a system that can potential help small market MLB teams or even big market MLB teams that want to reduce their team salary target similar all-star players without having to spend that much money.

## Next Steps

For this recommender system, only MLB players were looked at but essentially this recomendation system can be extended to minor league players or even international players like Japan. It could recommend the next all star MLB player. There are so many stats for baseball pitcher or batter. This can provide more features to use predict salary and even the recommendation system. To help improve the regression model, maybe just looking at veteran players with the MLB salary and not those who still have a "rookie" salary. There was an issue with getting player with Juniors in their name. The time series model is not static with more current data the better the forecasts. A way to automate the collection of game data to include to time series data. 