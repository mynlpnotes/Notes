# Forward Propagation

* Sentiment analysis: Many to One RNN
*

    <figure><img src="../.gitbook/assets/image (9) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
*

    <figure><img src="../.gitbook/assets/image (10) (1) (1) (1).png" alt="" width="230"><figcaption></figcaption></figure>
* Since this is many to one, we apply softmax as this is multiclass classification
* For binary we apply sigmoid
* Then we get predicted class
* We apply loss function between actual and predicted and then we update all the weights
