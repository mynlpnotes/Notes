# Back Propagation

*

    <figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>
*

    <figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>
* We need to update w and wdash here
* first we will update wdash using weight update rule at t = 4
* And after that we update w
* After that we update wdash at t = 3
*

    <figure><img src="../.gitbook/assets/image (6).png" alt="" width="375"><figcaption></figcaption></figure>
* This backpropagation will happen for the no. of epochs
* if no. of time instance is more then in backpropagation vanishing gradient problem will happen
* if we have used sigmoid, the range of output of sigmoid is 0 to 1 and its derivative is between 0 and 0.25, so it might happen that there is no weight updation