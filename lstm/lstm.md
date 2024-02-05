# LSTM

* Long short term memory
* Understand what to remember and what not to remember
* We don’t need to remember the entire review, only the highlighted part is important
*

    <figure><img src="../.gitbook/assets/image (2) (1) (2).png" alt=""><figcaption></figcaption></figure>
*

    <figure><img src="../.gitbook/assets/image (3) (1) (2).png" alt=""><figcaption></figcaption></figure>
* Developed in 1997
* C(t-1) – information coming previous unit
* H(t-1) – Hidden state
*

    <figure><img src="../.gitbook/assets/image (4) (1) (2).png" alt=""><figcaption></figcaption></figure>
* tf.keras.LSTM() – Optimized for GPU
* tf.keras.RNN(tf.keras.layer.LSTMCell()) – Optimized for more customization than GPU
*

    <figure><img src="../.gitbook/assets/image (5) (1) (2).png" alt=""><figcaption></figcaption></figure>
* We are getting output at different time instances from RNN/LSTM
* We might require this to be passed to an ANN
* For this we need to use tf.keras.TimeDistributed(tf.keras.layers.Dense())
* it will wait for different timestamps and then it will take input and pass it to ANN
