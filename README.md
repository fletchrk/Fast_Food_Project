# ![Image](https://github.com/fletchrk/Fast_Food_Project/blob/main/Resources/Image.png)

## Group Project Shared Repository

- Selected topic: The relationship between fast food restaurants and diabetes across the United States

- Reason why topic was selected: The team selected this topic based on common interests among the team members. Several other topics were considered such as personality tests, Michelin restaurants, unemployment rates and topics related to the pandemic. However, we settled on Fast Foods and diabtes for logistical reasons, such as access to the necessary data sets. 

- Description of data source: The data set was obtained from kaggle.com and was uploaded by Datafiniti's Business Database. The data can be found [here.](https://www.kaggle.com/datafiniti/fast-food-restaurants) We have two sets of restaurant data that will be merged using postgres SQL. Then a dataframe will be created to add the diabetes data. The diabetes data set was obtianed from the CDC website and can be found [here.](https://gis.cdc.gov/grasp/diabetes/DiabetesAtlas.html#) We are using a third data set from census.gov to obtain the population from each state. This data can be found [here.](https://www.census.gov/acs/www/data/data-tables-and-tools/data-profiles/2017/)

- Questions we hope to answer with the data:
 
  1- Which states have the most fast food restaurants per capita?
  
  2- What are the Fast food restaurants per capita for all states?
  
  3- Which Fast food restaurants have the most locations nationally?
  
  4- What is the number of fast food restaurants per capita nationally?
  
  5- Which states have the most cases of diabetes?
  
  6. What is the national number of diabetes cases?
  
  7- Does the number of fast food restaurants correlate to the number of diabetes cases by state?
  
 - Description of the data exploration phase of the project: The main data sets consisted of two files for fast food restaurant data. We created the tables in  postgres SQL, renamed the columns to match each other and then merged the data using a full join. Then the data exported and uploaded into the jupyter notebook for additional exploratory analysis. When we ran some code to create additional joins, we relized other areas that needed cleaning in the data. For example when running the code to groupby state, we realized one data set had included Puerto Rico but the other did not. We then dropped those rows for consistency. Another important element we discovered, was that we originally intended to analyze the data by counties and by states, but we realized the fast food data set did not include a county. We did have the longitude and latitude for the restaurants but were unable to find a way to add the counties using these, since counties overlap cities and longitude and logitude. We instead decided to focus our analysis by state. 
 
 - Description of the analysis phase of the project: For the analysis phase we included all teh relevent information into one data frame. Then we created two additional columns to calculate and input the per capita rates for both diabetes and number of restaurants. We alos created a scatter plot to show that when the number of restaurants increase, the number of diabetes cases increase as well. However, when we used another scatter plot to show that the rate of diabetes per capita also has a postive correlation with the rate per capita of number of restaurants, we ended with a cluster and not a positive correlation. This means that potentially while the more restaurants could mean more diabetes, the size of the population does not necesarily reflect the same pattern, as would have been expected.  

- Description of preliminary data preprocessing: After merging and cleaning the data, we then defined X and y. X is the independent variable and for this project was the number of restaurants per state. Y is the dependent variable, which for this project is the number of diabetes cases per state. 

- Description of preliminary feature engineering and preliminary featureselection, including their decision-making process: Since we are attempting to establish a correlation and the data is continuous, we used teh linear regression model. The plot created suggests that there is a positive correlation between the number of fast food restaurants per dtate and the number of diabetes cases. 

- Description of how data was split into training and testing sets: After we fit the model using the linear regression template from sklearn.linear_model, the model effectively created the predictions. 

- Explanation of model choice, including limitations and benefits: The benefit of this model is that after establishing a correlation the model is able to predict the value of y when the value of x is given. This would be useful information if we wanted to develop a plan to decrease the rate of diabetes per state or nationally. We would have an understanding of what the ratios should look like and make decisions from there. We could also plan diabetes treatment based on the number of cases we expect to see as we see the the number of restaurants increase. The modeled data and the actual data show a similar trend. The limitation is that there are other variables to consider and this model is not able to take all of that into consideration. 

- Dashboard draft can be found [here.](https://public.tableau.com/app/profile/rachel.fletcher3993/viz/Fast_Food_Project/_FF_Restaurants)

## Communication Protocol:
- The team will primarily communicate via slack.
- Any urgent communication will occur via phone or text.
- Emails have been exchanged to share any documents, templates or links.
- Meetings outside of class will occur via zoom and scheduled in advance while taking into account everyone's availability.
