# Interview Questions

1. **What is train, test and validation**

* &#x20;Dataset - Train(For model training), Test(Model never sees this, this is for testing, if model sees this then it is called data leakage)
* Training is again split into training and validation(For hyper parameter tuning)
* Hyper parameter tuning done using cross validation using grid search and randomized search cv

2. **Why random forest instead of decision tree**

* Decision tree has low bias and high variance(Since there can be over fitting in DT)
* So make this low bias and low variance we use RF
