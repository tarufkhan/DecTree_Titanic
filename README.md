## Using Decision Tree technique to predict the survial of passengers of the Titanic

### What we did here & Results -
* Import all the required libraries & modules.
* Load the dataset from the titanic.csv file.
* The dataset has a shape of 891 rows and 12 columns. Not such a big dataset.
* Using only ‘Pclass’, ‘Sex’, ‘Age’, ‘SibSp’ (Siblings aboard), ‘Parch’ (Parents/children aboard), and ‘Fare’ for the prediction where a passenger survived or not. So we dropped others.
* Now, our dataset has 891 rows and 7 columns. Only the ‘Age’ column has 177 null values. It is around 19% of the whole dataset. So we can drop null rows from the ‘Age’ column.
* Finally, we get a dataset with shape of 714, 7.
* The column named ‘Sex’ has categorical string values [‘male’, ‘female’]. We changed it to ‘male’ = 1, ‘female’ = 0, so that we can plot and work with it easily.
* Now, the data distribution we have is -

![img1](/img/dt1.PNG)

* Seems like we can use this data and on outlier detection we got -

![img2](/img/dt2.PNG)

* Concluding that the data is good to use, we moved forward preparing the dataset to fit in the Decision Tree model.
* After applying the Standard Scaler, we did check the VIF and got very good results in the range of 1.1 to 1.7.
* Splitting data into train and test parts then fitting the train data on the Decision Tree we got an accuracy of 74% on test data.
* We did plot and saved the Decision Tree image that was formed. Here, it is -

![img](/DT_Titanic.png)

* The Confusion Matrix we got is -

![img3](/img/dt3.PNG)

* Values of other Evaluation metrics are -
  * Accuracy - 0.7430167597765364
  * Precision - 0.803921568627451
  * Recall - 0.7592592592592593
  * F1 Score - 0.780952380952381
  * Specificity - 0.7183098591549296
  * AUC - 0.7331296154825567
* The ROC AUC Curve is -

![img4](/img/dt4.PNG)

* Our accuracy is 74% which is good but we did apply Hyper Parameter tuning to check if we can increase model accuracy or not.
* The parameters we tried to tune are 
  * 'criterion', 'max_depth', 'min_samples_leaf', 'min_samples_split', 'splitter'.
* On using the GridSearchCV for tuning, we got the best values of above mentioned parameters.
  * 'criterion': 'gini', 'max_depth': 8, 'min_samples_leaf': 3, 'min_samples_split': 3,'splitter': 'best'
* After using these values we got a slight increase in the model accuracy of 3%.
* The Final accuracy was 77%.
