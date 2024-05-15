This project is for data prediction based on the tragedy of Titanic. This is a competition released by Kaggle (https://www.kaggle.com/competitions/titanic). 

1. Problem and goals description: 

"The sinking of the Titanic is one of the most infamous shipwrecks in history.

On April 15, 1912, during her maiden voyage, the widely considered “unsinkable” RMS Titanic sank after colliding with an iceberg. 
Unfortunately, there weren’t enough lifeboats for everyone onboard, resulting in the death of 1502 out of 2224 passengers and crew.

While there was some element of luck involved in surviving, it seems some groups of people were more likely to survive than others.

In this challenge, we ask you to build a predictive model that answers the question: “what sorts of people were more likely to survive?” 
using passenger data (ie name, age, gender, socio-economic class, etc)."

2. Softwares and languages used:
   - Python
   - VS Code

3. Steps of the solution:
   - Importing libraries on VS Code for Python
   - Reading the train.csv file, treating the data and cleaning it
   - Reading the test.csv file, treating the data and cleaning it
   - Creating graphs to understand better our dataset and also the correlation between variables
   - Creating our train set to train our models
   - Using different predict methods to predict the 'Survived' column on the test dataset
   - Checking to see which method is the most efficient
   - After the prediction of the 'Survived' column, saving our file with the columns 'PassengerId' and 'Survived'
  
4. Files description:
   - "Submission_file.csv" - Final file to submit on Kaggle for the competition
   - "predict_model.ipynb" - Code
   - "test.csv" - Test database to predict the 'Survived' column
   - "train.csv" - Train database to use as base for training the models
  
5. Initial problems checked and found:
   -  Empty values on columns 'Age', 'Cabin' and 'Embarked' on our 'train.csv' dataset. It was treated by getting the median for numerical column 'Age', randomic choice among most common values for categoric column 'Cabin', and filling the empty value with
   the one most common value on column 'Embarked'.
   - Since for the 'Name' column we had a lot of titles and some of them were rare among the others, it was decided to turn it into 'Rare' and for the others it was created a pattern. I.e.: 'Ms' as 'Miss', 'Mlle' as 'Miss' and 'Mme' as 'Mrs'. Also, to turn it into a
   numeric column, it was chosen to make each title into a number.
   - For 'Age' column, it was decided to make some groups of ages and turn each group into a number to minimize the data and make it more efficient to compare with the test.csv.
   - Since the columns 'Sibsp' and 'Parch' were both family data, it was chosen to sum these two columns for each passenger to get what are the number of family members. It was also created a column for 'IsAlone' data from the family members column.
   - The Fare column was turned into groups to minimize the data and make our analysis more efficient, since it will be difficult for us to have the same fare number for more than one passenger and this would turn our model into a less efficient one.
   - Since all the data from the 'Cabin' column have the pattern 'Letter' + 'Number', and the letters are common among all the passengers, it was decided to turn it into only letter and grouping the passengers by Cabin.
   - For 'Sex' to be a numerical column to make our analysis mnore efficient, we turned 'female' into 1 and 'male' into 0.
   - It was also checked to duplicated values in our dataset and wrong values in the columns that we already had something specified (i.e.: 'Sex' column could only have 'female' or 'male').
   - It was checked for correlations.

   These checks and corrections were done also in our 'test.csv' dataset, and after all, we dropped some columns that didn't make sense and reordered them to make both datasets have the same columns in the same order.

6. Prediction methods:
  - Logistic Regression
  - KNN or k-Nearest Neighbors
  - Support Vector Machines
  - Naive Bayes classifier
  - Decision Tree
  - Random Forrest
  - Perceptron
  - Artificial neural network
  - RVM or Relevance Vector Machine

   The comparison among all these methods score showed us that the most efficients were 'Support Vector Machines' and 'KNN' for this dataset.
