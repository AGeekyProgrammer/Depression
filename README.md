# Depression
Is the person depressed?
GOAL: Explore factors that may cause individuals to experience depression.

**Data**
Data is from a mental health survey. 
The following data is recorded: academic/working pressure, study.job satisfaction, work/study hours, financial stress, sleep duration, dietare habbits, suicide thoughts history, mental health ilnesses family history. 
The data is divided into: 
  train.csv - all the columns + 'Depression' label
  test.csv - all the columns + NO 'Depression' label

## Tech Stack
- LightGBM (Light Gradient Boosting Machine)
- To evaluate the accuracy metric was used. Highest accuracy: 0.89136.
- To find the best parameters for the model: GridSearchCV was used.
- Data exploration: check the distribution of data in train dataset
- Data cleaning: encoding all the categorical data, create categories for sleep duration and dietary habbits, delete nonsense values. 

**Clarifications**
1. Why use LightGBM?
  + Great with categorical data. Which here there is a lot of
  + Great with big datasets.
  + Handles missing values very well. There are a lot of missing values in the data.
2. What did data explortion show?
  There are way more non depressed people (81.83%) that depressed (18.17%). However, this difference is not large enough to skew the model, thus no down- or     upsampling is needed.
  There is a lot of data which is onle seen 1 or 2 times in the dataset, like the answers used for sleep duration or dietary habbits -> this is why those were   manualy encoded.
3. How was the classificator trained?
  Test.csv doesn't contain 'Depression' labels, to test it the submission.csv needs to be uploaded to Kaggle and it calculates accuracy. To test the model       locally the train dataset was split into training and test. I tried 2 different models: lightGBM and XGBoost (Extreme Gradient Boosting). LightGBM won based   on accuracy measure. 
  Then GridSearchCV was used to find the best parameters for the model. 
  After this I trained the model on the whole training set, with the best parameters and then predicted the test dataset. This is how the highest accuracy of    0.89136. was achieved.


 
