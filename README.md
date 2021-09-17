# In17-S7-CS4622-Project
# 170326U
# T.G.V.S.H.Kumara

**Machine Learning Project on Pump it Up Competition by DrivenData**

## 1. Visualize

#### 1. mi_score
Tried calculating mi_score by using factorize() for encoding.
RAM out of storage and failed to execute

#### 2. Graph
Used plt.hist() and plt.show()

Used sns.relplot(x=feature_name, y="status_group", data=train);
Plot x for all the columns in dataset against y as status_group

#### 3. Data view
describe()
value_count()
head() used to view data

## 2. Preprocessing

#### 1. Missing values
First dropped all the columns contained null values and checked accuracy.
For some columns contained null values, median was added and submitted.

#### 2. Encoding
ordinalencoding
checked wheather columns can be encoded or not.
some columns dropped due to inability to encode ('wpt_name' and 'ward')

#### 3. Data cleaning
Remove another column('quality_group') by observing description on the competition,
and analyzing given data.
Remove 'recorded_by' because of NaN data.

## 3. Feature Engineering

#### 1. Created new features
Got the recorded year as a int out of date_recorded string.

#### 2. Checked corrrelation
remove few colums which had highly correlated.

## 4. Submissions

##### 1.  0.6203    
Used only numbered columns
model = RandomForestClassifier(n_estimators=100, max_depth=5, random_state=1)
##### 2.  0.7015    3958/12373
Used ordinal encoder
Used 14 columns
model = RandomForestClassifier(n_estimators=100, max_depth=5, random_state=1)
##### 3.  0.7129    3920/12373
Used ordinary encoder, remove 2 columns that cannot be ordinalencoded
model = RandomForestClassifier(n_estimators=100, max_depth=5, random_state=1)
##### 4.  0.7151   3909/12377
Remove recorded_by column
Check corr() and remove 9 other columns
Check describe()
##### 5.  0.8135 	2003/12381
XGBoost()
Found hyperparameters using Gridsearch
Decreased max_depth by 1 and submitted
Errors occured with labels containing strings. 
Encode label and train XGBoost and got the output
Decode and submit in the correct string format
##### 6.  0.8128  	 2003/12382
Reset max_depth to the output of grid search output. Accuracy decreased
##### 7.  0.8121	2003/12389
Gradient boost
##### 8.  0.8084   
Remove one of the 0.65 correlated features. But got lower accuracy
##### 9.  0.8137	1997/12422
Although there was a low correlation between water_quality and quality group,
checking the description of the features on drivendata homepage and then,
dropped one of the features and increased accuracy.
##### 10.  0.8140   	1968
Add **True** to permit column missing values

## 5. Models

####  1. Random forest
Unable to do hyperparameter tuning by RandomizedSearchCV (processing time exceeded).
manually changed some hyperparameters and got some increased accuracy.

####  2. XG Boost
split the trainset and used GridSearchCV for hyperparameter tuning.
used label encoding for labels : {'functional':int(1), 'non functional':int(0),'functional needs repair':2}

####  3. Gradient Boost 
Increased the grid size for GridSearch; processing time exceeded.
Used same hyperparameters as XG boost.

#### Final Sumbission accuracy  : 0.8140
#### Final Rank                 : 1997


## ******************************************************************************
