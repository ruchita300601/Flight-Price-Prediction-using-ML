# Flight-Price-Prediction-using-ML

**ABSTRACT** 
The cost of flight tickets is subject to fluctuations due to various factors such as flight timing, duration, and destination. In this project, historical data of flights will be collected and machine learning algorithms will be applied to develop a predictive model. However, determining the optimal time for purchasing flight tickets from a customer's perspective is difficult as they have limited information about future price changes. The main objective of this research is to use historical data to identify patterns in flight pricing in India, including the specific times of the day or month when prices are expected to be highest. The project's scope can be expanded to various routes within the Indian Domestic Airline market to help customers save significantly on flight ticket purchases.


**Data source: Kaggle**


**Dataset Collection:**
  
The data set of flight fare is in two Excel files: 1. Training 
                                                   2. Testing 
The train set contains 10683 records, there are 10 input features and 1 output column ‘Price’.
Test set has 2671 records and 10 input features.


**About Dataset:**
Airline: The column lists the names of various airlines like  Vistara, Air India, Jet, Airways, Indigo and many more.
Date_of_Journey: It specifies that the date on which the passenger's journey is started to begin.
Source: This column represents starting location of the passengers.
Destination: It column represents the ending location of the passengers.
Route: Route column contains information about the travel route that the passenger has selected.
Dep_time: This column represents the departure time of the flight.
Arrival_Time: it represents Arrival time of the flight.
Duration: The 'Duration' column represents the total time taken by the flight to complete the journey
Total_Stops: This column tells us about the number of stops the flight will make during the journey.
Additional_Info: In this column, it provides details on additional amenities such as food options, and other facilities.
Price: Price column indicates the total fare of the flight, which includes all expenses incurred before boarding the flight.


**Data Cleaning:**
The first step in data pre-processing is to clean the data by removing any irrelevant or duplicate information, handling missing values, and dealing with outliers.
The dataset does not contain Null values or Duplicate values.



**Data Transformation:**
We transform the data into a suitable format so, that can be used by machine learning models. 
The pandas to_datetime function can be used to convert object data types into datetime data types. Using the .dt.day method, we can extract the day from a given date, while the .dt.month method extracts the month. 
In the case of the 'Date_of_Journey' variable, we  extract both 'Journey_day' and  'Journey_Month'. 
We can extract 'Departure_Hour' and 'Departure_Minute', and aslo 'Arrival_Hour' and 'Arrival_Minute', from 'Dep_Time' and 'Arrival_Time' variables, respectively. Once these columns have been converted into integers, the original columns can be dropped since they are no longer needed.




**Data Endocing:**
Some of them categorical data are,
In case of Nominal data (data are not in any order) we use OneHotEncoder.
In case of Ordinal data(data are in order) we use  LabelEncoder.
‘Airline’ is a Nominal Categorical data so, we perform OneHotEncoding
‘Source’ is Nominal Categorical data so, we perform OneHotEncoding
For total_stops we use LabelEncoder as it is Ordinal data.


**Testdata Set:**
Similarly, to ensure consistency between the training and testing datasets, any exploratory data analysis (EDA) and data preprocessing steps applied to the training dataset should also be applied to the testing dataset. This includes checking the shape of the dataset, creating new features from existing ones, applying one-hot encoding to categorical features, dropping non-useful features, and keeping only the relevant features. By performing the same preprocessing steps on both datasets, we can ensure that our model is trained and tested on similar data, which can improve the model's performance and generalizability.


**Feature Selection:**
 The common practice in machine learning to try out multiple models on a given problem and compare their performance using appropriate evaluation metrics. This process is known as model selection. Here, we used Extra tree Regressor, Random Forest Regressor, Decision Tree, Logistic Regression.
To explore the correlation between variables in our dataset, we used the Seaborn function sns.heatmap(). The heatmap revealed a positive correlation between 'Total_Stops' and 'Price', indicating that an increase in the total number of stops leads to a higher ticket price. Furthermore, 'Total_Stops' was found to be highly correlated with 'Duration_hours'. This suggests that as the number of stops increases, the duration of the flight also increases accordingly. Understanding these correlations can be useful in feature engineering and in developing an accurate prediction model.


 **Splitting the dataset:**
The dataset  splits into 80% training data and 20% testing data.



**Model building:**

   We will fit the data into various regression analysis techniques to compare their performance and select the most efficient model. This process aims to identify the optimal model that best predicts the target variable and maximizes its accuracy. By comparing the efficiency of different models, we can evaluate their strengths and weaknesses, and ultimately choose the best model for the given data. Once we have selected the best model, we can then use it to forecast the results and make predictions about future data points.
 We are using : 
1. Random forest
2. Decision Tree
3. Logistic Regression


**Conclusion:**
The dataset of flight fares is subjected to Machine Learning algorithms to forecast the fluctuating prices of flights. The predictions are aimed at providing the users with the cheapest possible ticket prices. Random Forest Regressor is predicting high accuracy than other algorithms. The model's accuracy is remarkably high, which is evident from the distribution plot and scatter plot of the training and testing data. The dataset attributes have been illustrated using data visualization techniques. To obtain more dependable results, more accurate data with additional features could be utilized.


