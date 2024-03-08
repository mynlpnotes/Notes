# Interview Questions

1. **What is train, test and validation**

* &#x20;Dataset - Train(For model training), Test(Model never sees this, this is for testing, if model sees this then it is called data leakage)
* Training is again split into training and validation(For hyper parameter tuning)
* Hyper parameter tuning done using cross validation using grid search and randomized search cv

2. **Why random forest instead of decision tree**

* Decision tree has low bias and high variance(Since there can be over fitting in DT)
* So make this low bias and low variance we use RF

3. **What is this distribution?**

<figure><img src=".gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="" width="375"><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="" width="375"><figcaption></figcaption></figure>

* Pareto can be converted to normal distribution using Box Cox transform

4. **What is the technique to understand if a distribution is normal or gaussian distribution?**

* Q-Q Plots

5. **What is standard normal distribution?**
6. **What is the relations between mean, median and mode in below distribution?**![](<.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1).png>)
7. **Difference between fit and fit\_transform?**
8. **When do we use fit\_predict method?**
9. **What is the difference between normalization and standardization?**
10. **Why LSTM RNN instead of RNN?**

* Vanishing gradient problem/Dead neuron
* The context info

11. **Sparse matrix:**

```python
from scipy.sprase import csr_matrix

a = csr_matrix(matrix)
It will store only the locations of 1

a.todense() --> to convert back to dense matrix
```
