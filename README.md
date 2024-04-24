# sc1015-miniproject

## About

This is mini-project for SC1015, Intro to Data Science and Artificial Intelligence.
For our mini-project we decided to look at trends in popular songs over the past few years.

## Dataset and problem definition

Dataset - [Top 100 Spotify songs from 2010-2019](https://www.kaggle.com/datasets/muhmores/spotify-top-100-songs-of-20152019)

Problem Definition - Try and identify trends over the years to predict what attributes the top songs in the next few years will have

## Data preparation
- Dropping unnecessary columns from the dataset (year released, title, artist, added)
- Keeping numeric values like attributes (bpm, dnce, nrgy, etc.)
- Removing numeric values outside 2.5 standard deviations from the mean to try and remove outliers (145 values removed), improves the accuracy of the regression
- Splitting the data into 2010-2017 and 2018-2019 as the train and test respectively

## EDA/Visualisation
- Created a boxplot of all the numeric variables to try and see any trends
- 3 variables seemed to have trends: 
    - pop - The popularity of a track is a value between 0 and 100, with 100 being the most popular. The popularity is calculated by algorithm and is based, in the most part, on the total number of plays the track has had and how recent those plays are. 
    - Nrgy - Energy is a measure from 0 to 100 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. For example, death metal has high energy, while a Bach prelude scores low on the scale
    - Val - A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry)
- We observed a decrease in both nrgy and val and an increase in pop
- To confirm this we used hypothesis testing to confirm our trends, and these 3 variables showed more significant change than other variables which could confirm our original hypothesis. 

## Machine Learning
- To test our predictions we will use the 2018-2019 dataset we split earlier
- We use 2 types of regression, linear and random forest to try and compare which ones were giving us better results
- From both regression models we got the smallest RMSE from pop, and the highest RMSE from val. So it seems like out of the three attributes, pop is the best at predicting whether a song would be in the top 100, followed by nrgy and then val
- Comparing the regression models, random forest gave us lower errors for val and nrgy, but only slightly higher for pop. So we can say that random forest is a better model to use compared to linear regression in this case

## Conclusion and Observations
- From our results it seems that in the future the top 100 songs will have less energy, and will start to be more negative. This makes sense because songs with lesser energy also seem more negative. 
- The songs are also going to be higher in popularity, which can be attributed to a larger number of users on Spotify, so songs have to be more and more popular to make it onto the top 100 songs playlists.

## What new things did we learn
- We learnt about random forest regression
- We learnt about hypothesis testing
