# ![Image](https://github.com/fletchrk/Fast_Food_Project/blob/main/Resources/Image.png)

## Group Project Shared Repository

- Selected topic: The relationship between fast food restaurants and diabetes across the United States

- Reason why topic was selected: The team selected this topic based on common interests among the team members. Several other topics were considered such as personality tests, Michelin restaurants, unemployment rates and topics related to the pandemic. However, we settled on Fast Foods and diabtes for logistical reasons, such as access to the necessary data sets. 

- Description of data source: The data set was obtained from kaggle.com and was uploaded by Datafiniti's Business Database. The data can be found [here.](https://www.kaggle.com/datafiniti/fast-food-restaurants) We have two sets of restaurant data that were merged using postgress SQL. A dataframe was created to add the diabetes data. The diabetes data set was obtianed from the CDC website and can be found [here.](https://gis.cdc.gov/grasp/diabetes/DiabetesAtlas.html#) Additionally, from the CDC we obtained more data sets of other features (i.e. obesity rates, smoking rates and non-activity rates) that may also contribute to number of diabetes cases. The last data set was obtained from census.gov to obtain the population from each state to calculate per capita rates. This data can be found [here.](https://www.census.gov/acs/www/data/data-tables-and-tools/data-profiles/2017/)

- Questions we hope to answer with the data:
 
  1- Which states have the most and least fast food restaurants?
  
  2- What are the top 10 Fast food restaurants nationally? Which Fast food restaurants have the most locations nationally?
  
  3- What is the number of fast food restaurants per capita by state?
  
  4- Which states have the most cases of diabetes?
  
  5- What is the national number of diabetes cases? Number of diabetes realated risk factors (smokers, obesity, non-activity levels)?
  
  6- Does the number of fast food restaurants correlate to the number of diabetes cases by state? 
  
 - Description of the data exploration phase of the project: The main data sets consisted of two files for fast food restaurant data. We created the tables in  postgress SQL, renamed the columns to match each other and then merged the data using a full join. Then the data was exported and uploaded into the jupyter notebook for additional exploratory analysis. When we ran some code to create additional joins, we realized other areas that needed cleaning in the data. For example when running the code to groupby state, we realized one data set had included Puerto Rico but the other did not. We then dropped those rows for consistency. Another important element we discovered, was that we originally intended to analyze the data by counties and by states, but we realized the fast food data set did not include a county. We did have the longitude and latitude for the restaurants but were unable to find a way to add the counties using these, since counties overlap cities and longitude and logitude. We instead decided to focus our analysis by state. 
 
 - Description of the analysis phase of the project: For the analysis phase we included all the relevent information into one data frame. Then we created two additional columns to calculate and input the per capita rates for all the variables. We also created a scatter plot to show the relationship between diabetes and all the X variables. The scatter plot showed a positive correlation between diabetes and obesity, smoking and inactivity. However, it did not show a clear relationship with number of restaurants.  

- Description of preliminary data preprocessing: After merging and cleaning the data, we then defined X and y. X is the independent variable and for this project was the number of restaurants per capita per state. Y is the dependent variable, which for this project is the number of cases of diabetes per capita per state. During additional exploratory analysis and feedback received, we decided to add additional variables with the other risk factors for the diabetes. These factors were all included as X features (obesity, smoking, and inactivity). 

- Description of preliminary feature engineering and preliminary feature selection, including their decision-making process: Since we are attempting to establish a correlation and the data is continuous, we initially used the simple linear regression model. The plot we created suggested that there is a positive correlation between the number of fast food restaurants per state and the number of diabetes cases. After adding the additional features, we used a multiple linear regression model to analyze the additional features and compare the relationship with diabetes. 

- Description of how data was split into training and testing sets: Initially we scaled the data. However, after we calculated the data using per capita rates, it was unnecesary since all the values were between 0 and 1.  Also, the random forest model does not need the data scaled. Then we fit the model using the linear regression template from sklearn.linear_model, and the data was split using a 80/20 ratio of training to testing. 

- Explanation of model choice, including limitations and benefits: The benefit of this model is that after establishing a correlation the model is able to predict the value of y when the value of x is given. This would be useful information if we wanted to develop a plan to decrease the rate of diabetes per state or nationally. We would have an understanding of what the ratios should look like and make decisions from there. We could also plan diabetes treatment based on the number of cases we expect to see as we see the the number of restaurants increase. The modeled data and the actual data show a similar trend. The limitation is that when using this model, we included other possible risk factors, but there are many more to consider and this model is not able to take all of that into consideration. Additionally, another limitation is found within the data sets. The data used is a sample, and even though it was randomly selected and should be predictive of the actual values, it is still a sample and could have some skewed data. When evaluating the linear regression model, the scores were all very promising. We decided to include a second model to compare the scores. We chose the Random Forest Regression model, because while it does not provide the speed the linear regression model does with large data sets, it will increase the acurracy by creating several predictions and providing an average.

- Result of analysis: Based on the Pearson Correlation Coefficient and the visualizations, the machine learning models were both very effective at predicting the values of "y" (diabetes per capita). The linear regression model had a Pearson value of 97.0%, while the Random Forest Regression Model had a value of 96.9%. 

- Recommendation for future analysis: Given more time for an analysis, we would recommend further research into predictors of Diabetes and include those variables in our data frames and machine learning models. Obviously there are various factors that contribute to Diabetes in the U.S., like location, genes, health and physical habits, and more. We recommend including as many X variables as possible to create a sufficient model that can accurately predict Diabetes and portray the strength of each correlation between the dependent variables and independent variable. Another recommendation for future analysis would be to include bar charts for the different predictors of Diabetes and their prevelance in each state. Creating these visuals would show how the severity of each predicor varies across the country. Finally, finding and including relevant data sets from other countries could help broaden and strengthen the analysis. 

- Anything the team would have done differently: We decided to work with data from a sample found on Kaggle and the CDC website for Diabetes in the United States. After working with the Diabetes and restaurant data and comparing it to the population size in the United States, we decided that if we had more time to complete this analysis, we would try to get bigger data sets that are more representative of the population sizes in each state. Another aspect of the project that we would have done differently is incoporating various X variables from the beginning. As we worked on the machine learning section of the analysis, we realized that we should have incorporated more predictors of Diabetes. We can't formally comment on and find a direct relationship between Diabetes and fast food restaurants, as there are a ton of other factors that play into that relationship. We were able to incorporate various predictors in our analysis, but we wish we brought them in sooner. In addition, with more time we could have added more questions with relation to the newly added variables and visuals to explore these relationships, as well as find data on various years for all of the predictors, not just for the years 2017 and 2018. Finally, if we had more time for the project, we would have spent more time on the introductory analysis in Python, to make the database integration smoother. 

- Description and explanation of model’s confusion matrix, including final accuracy score: Since our predictions were continuous, we did not evaluate the model using the confusion matrix. Instead we calculated Mean Square Error, R Squared, Spearman Correlation Coeficient, Pearson Correlation Coefficient and p-values. The mean square error: is the variance around the fitted regression line. The lower the number, the smaller the “errors/ variance”. 
R squared: measures the strength of the relationship between the model and the rates of diabetes. Generally, the higher the better, but if it is too close to 100%, then there could be overfitting.  Spearman Correlation Coefficient: can take values from +1 to -1.  +1 indicates a perfect association, zero indicates no association between ranks and -1 indicates a perfect negative association.  The smaller the p-value, the stronger the evidence that you should reject the null hypothesis. The p-value is the probability that the null hypothesis is true.  Pearson Correlation Coefficient: If the coefficient value lies between ± 0.50 and ± 1, then it is said to be a strong correlation. Both models did exceptionally well in all areas in which they were evaluated and compared. Below is an image of the results. 

![lrm](https://github.com/fletchrk/Fast_Food_Project/blob/main/Resources/lrm.png)


![rfr](https://github.com/fletchrk/Fast_Food_Project/blob/main/Resources/rfr.png)


### Technologies Used
- Data Cleaning and Analysis:
Pandas was used to clean the data and perform an exploratory analysis. Further analysis was completed using Python in a Jupyter Notebook.

- Database Storage:
Postgres SQL is the database we used for storing and merging the initial data sets.

- Machine Learning:
SciKitLearn is the Machine Learning library for Python we'll be using to create a supervised learning model. This entails creating the model, training the model and then creating predictions. More specifically we intend to use a multiple linear regression model since our data is continuous and not categorical, as well as a Random Forest Regression model to draw comparisons. 

- Dashboard:
We will use Tableau for a fully functioning and interactive dashboard and can be found [here.](https://public.tableau.com/app/profile/giulia.tasca/viz/Fast_Food_Project_16250237518670/Dashboard_Graphics_1)

- Google Slides:
To access the presentation click on the google slides [link.](https://drive.google.com/file/d/1He-NSL58hJ7rZ04gDH3EYZGbVNBDyOa9/view?usp=sharing)
