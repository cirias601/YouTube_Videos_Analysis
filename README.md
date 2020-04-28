# YouTube_Trending_Videos_Analysis
![](images/YouTube%20Logo.png)

An analysis on the amount of engagement (likes, dislike, views, comment count) Youtube Trending videos get and the relationship between each of these datas.

## Problem Statement
Assuming that there is a strong correlation between the amount of engagement a video recieves, can we then predict the amount of likes, for example, based the on the views and comment count that a video recieves? And from these datas, can we predict the genre of that video? 

## Text Findings
For my project, I wanted to analyze the relationships between the amount of engagement Youtube videos recieve and how these datas affect one another. So I created a pairplot to see the relationships between each of these datas (likes, views, dislikes, and comment count). From this I saw that, of course, the more views a video recives, the more likes it will get. Same goes with the amount likes to comment count, amount of likes to dislikes, and so on. Afterwards I checked to see from these relationships, which of these variables have a strong correlation with one another and that will allow me to grab an independent variable to predict a dependent variable. I saw that the amount of views, likes, dislikes and comment count all have a strong correlation with one another meaning that these variables have an affect with one another. Because there is a strong correlation between views to likes, for example, I decided to predict the amount of likes a video will recieve given the amount of views it will get. I then created a reg plot to perform a simple univariate linear regression model. I plotted all the views and likes from my dataset for each video and also the given and predicted value that I just made. This plot has allowed me to see a regression line in my dataset as well and visually see where my predicted value lies in the plot in comparison to all the data in the dataset. I then sampled my data by splitting it into training data and testing data. This will take data from my dataset ("train data") for both x (views) and y (likes) and then test my model's predictions of this data. Lastly I evaluated my erros using the metrics from sklearn. My MAE was 41261, my MSE was 15 M, and my RMSE was 126,182. These errors will determine how good or bad my model is. The lower the errors, the better the model. My errors seem to be larger numbers so I decided to do this same exact analysis but on a multivariate linear regression. So instead of just using one indepedent variable (the amount of views) to predict a dependent varaible (the number of likes), I used multiple independent variable. So instead, I predicted the amount of likes from number of views AND comment count. This allows me to use more data from my dataset and as a result will make better and accurate predictions since there are more variables involved. I outputted my errors like I did with my univariate linear regression and got lower errors which shows that this model is better to use. The lower the errors, the better the model is.  The last part of my project was to answer if I am able to predict the genre of a video based on the amount of engagement it recieves. I created a new column called, "Genre', and added the Genre of each video to that column based on its category ID. I did this because it would be easier to read the actual genre of the video instead of having to interpret the category ID. I then subset my data and sampled on only 1000 rows from my whole dataset to use for my decision tree because using the whole dataset would make the decision tree extremely unreadable. I then analyzed my data and got the mean likes and views of each genre of videos from this subset to get a better understanding on what genres will be more trendy based on those averages. I saw that 'Music' and 'Film and Animation' are the most viewed and liked genres and that also proves how both of those datas have a very strong relationship between one another. This is just such some statistics I wanted to calculate to have an idea on what is to be expected in my decision tree. I then selected my indepedent variables (likes, dislikes, views, comment count) and depedent variable (what I am trying to predict = Genre) for classfication. I did a train test split with these variables to further be able to see the model accuracy. Because I only looked at 1000 rows from my dataset, of course my accuracy percentage was going to be lower(0.26) compared to if I looked at my whole dataset, but when I previously looked at the model accuracy of my whole dataset, the accuracy percentage was 0.5. I then was able to output my decision tree successfully and that as a result, showed how each video can be classified by genres based on the amount of engagement (likes, dislikes, views, comment count) it will recieve. My problem to this project was successfully because I was able to prove that the engagement recieved in youtube videos are in relation with one another which allowed me to make predictions with this finding and from these datas (likes, dislikes, views, and comment count), I was able to also predict the genre based on the amount of a engagement a video recieves. 

## Instructions to run your code
### Special libraries needed to run code: 
#### Libraries: Data Visualizations
import pandas as pd  
import matplotlib.pyplot as plt  
import seaborn as sns  

Pandas loads the data file as a Pandas data frame and analyzes the data.
Matplotlib and seaborn are data visualization libraries.

#### Libraries: Linear Regression
from sklearn.linear_model import LinearRegression (create a linear regression model)
from sklearn import metrics (used to evaluate errors)
#### Libraries: Decision Tree
from sklearn.tree import DecisionTreeClassifier (imports decision tree classifer)
from sklearn.model_selection import train_test_split (imports train_test_split function)
from sklearn import metrics (import scikit-learn metrics module for accuracy calculation)

from sklearn.externals.six import StringIO 
from IPython.display import Image
from sklearn.tree import export_graphviz
import pydotplus

These last four libraries are used to make the decision tree visualizations. 

## Visualizations
Pair Plot: 
This shows the relationship between likes, views, dislikes, and comment count

![](images/Youtube%20Trending%20Videos%20PairPlot.png)

Decision Tree:
This tree classfies youtube videos by genre based on the amount of engagement it recieves. 

![](images/Youtube_Trending_Videos_Decision_Tree_Subset.png)

