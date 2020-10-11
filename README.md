# GooglePlayStoreRatings
Introduction :
Humans are highly dependent on the data they gain from relatives, neighbours and friends before making decisions, particularly before purchasing an expensive item. Currently, people are getting most of the information from the worldwide Web. Due to the over flooding information, customers usually face difficulties to locate their needs and item of interest. Recommendation systems play a significant role, to provide personalized recommendations to customers or users and also helps to deal with information overload. In this paper, ratings of applications is predicted to find out the success rate of the application.
The Google Play Store is one of the largest app market among all the mobile apps distribution platform in the world. With the ever-growing mobile app market, android app developers are rising. To keep pace with the competitive android app market an effective way should be determined by the developers to make their current position stable to retain their place in the market and it may be a solution for the developers to predict the success through the rating of end-users and installation as we know that the success of a new app is determined by its user rating and installation number.

Data Collection: 
I chose Google Play Store Applications dataset from Kaggle which consists of attributes like Category, Rating, Last Updated, Size, Installs, Type, Price and many other. Initially, the dataset consists of 10,840 tuples and 13 attributes.

Data Cleaning:
Cleaning of the datasets for various variables, beginning from ‘Categories’. The column is of string data type which cannot be convenient for our analysis. So, we convert into string by using the map function and for the function to iterate and assign a unique number to each category. The same process is applied to ‘Content rating’ and ‘Genres’. As, the number of unique variables is many we do not perform a One hot encoding now. It is performed during data transformation. Performing this would increase the size of these data frames exponentially.
‘Installations’ column has numbers in millions and thousands. The ‘M’ and ‘K’ with 1000000 and 1000 respectively. The empty values are converted into nan. The commas are also stripped off.
For the ‘Type’ column, which says if the app is free or paid is converted to binary from classification. The column including prices and reviews is converted to numeric. Now, we plot the missing data graph to find out the number of missing data.
The ‘last updated’ column which tells us when the application last updated is split in two columns. The first column is the year of the app being updated and the second column of the month. All the missing values were dumped, as the number was small.

Data Selection and Transformation:
After cleaning the unknown data out and getting rid of the unwanted values, the data frame consists of 9360 rows and 17 columns. To transform the data, One Hot encoding is used for the category’s column. The categories for ‘Type’ columns were free and paid which converted to numerical values to (0,1) to smear to the algorithms. To choose relevant columns for analysis, we implement the Pearson matrix. In the correlation matrix, values greater than 0.2 are chosen and values greater than 0.8 are not chosen as it has levels to correlation. Looking at the table, we choose 5 independent variables. The ‘Category’ variable is converted categorical data using dummy variables.

Training and Testing Data:
For the application of machine learning algorithms, splitting the preprocessed data into training and testing tests by 75% and 25% respectively. Next step involves constructing a model on the training data using data mining models.

Methodology:
It is clearly understood that the target variable is a rating which is dependent on various factors like no. of reviews, category of the app, year and month added and genre. Two approaches are used to compare the accuracy of both the models. The first approach is the Random Forest Classifier:
The Random Forest classifier consists of multiple decision trees. The final class of an instance is assigned by outputting the class that is the mode of the outputs of individual trees, which can produce robust and accurate classification. It also can handle a very large number of input variables. Relatively, it is very robust to overfitting and can handle datasets which have highly imbalanced class distributions. While using this approach the classifier is applied the original set and the dummy values and the scatter plot is used to show the differences. 
Logistic Regression models are the probabilities for binary classification problems. It describes the relationship between an independent variable which can be nominal, ratio-level, ordinal or interval and a dependent binary variable.
Here, logistic regression is applied to startup investment dataset to interpret the status of the company and to all explanatory variables to predict if the company is closed or acquired. It is observed that Logistic regression has better accuracy than Random Forest. Both the algorithms are a good fit.

Confusion Matrix: 
A confusion matrix is applied to Google Play Store dataset. The benefit of this model is that it can be applied to both categorical and continuous variables. The matrix table is shown below which demonstrates that the model predicted. The accuracy of the model is 0.72 (72%) without dummy variables and 0.73(73%) with dummy variables.

Result:
In this work, the first dataset is a list of applications on the Google Play Store. To predict the ratings, I applied Logistic Regression and Random Forest Classifier. Both the algorithms were found to be a good fit for the dataset. For future work, I would like to predict the ratings along with sentiment analysis that can be performed on the reviews




