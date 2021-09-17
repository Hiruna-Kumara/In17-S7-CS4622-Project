# In17-S7-CS4622-Project

**Machine Learning Project on Pump it Up Competition by DrivenData**


##1.Submissions

*0.6203    
Used only number columns
model = RandomForestClassifier(n_estimators=100, max_depth=5, random_state=1)
*0.7015    3958/12373
Used ordinary encoder
Used 14 columns
model = RandomForestClassifier(n_estimators=100, max_depth=5, random_state=1)
*0.7129    3920/12373
Used ordinary encoder, remove 2 columns that cannot be encoded
model = RandomForestClassifier(n_estimators=100, max_depth=5, random_state=1)
*0.7151   3909/12377
Remove recorded_by column
Check corr() and remove 9 column
Check describe()
*0.8135 	2003/12381
XGBoost()
Found hyperparameters using Gridsearch
Increase max_depth+=1 and submitted
Errors accrued with labels containing strings. 
Encode label and train XGBoost and got the output
Decode and submit in the correct string format
*0.8128  	 2003/12382
Reset max_depth to the output of grid search output. Accuracy decreased
*0.8121	2003/12389
Gradient boost
*0.8084   
Remove one of the 0.65 correlated features. But got lower accuracy
*0.8137	1997/12422
Although there was a low correlation between water_quality and quality group I checked the description of the features on drivendata homepage and then dropped one of the features and increased accuracy.
*0.8140   	1968
Add True to permit column missing value
