# Overview

<figure><img src="../.gitbook/assets/image (41).png" alt="" width="210"><figcaption></figcaption></figure>

* Above is a unidirectional RNN or vanilla RNN

**Issues:**

1. A regular RNN only looks at past and present input before generating output. This is called as casual network. It cannot look into the future
2. ![](<../.gitbook/assets/image (1) (2).png>)

* Here without knowing the next word, it wont be able to understand that queen is used in which context
* A regular RNN will go only L to R, so it wont be able to understand the context and may not predict correct output
* If we are able to feed the reverse, then we will be knowing the next sequence also
*

    <figure><img src="../.gitbook/assets/image (2) (3).png" alt=""><figcaption></figcaption></figure>
* We will be having forward and backward layer
* We are getting the feed in both the direction
* Once we have the output of both the layers, we will be concatenating the output
* For neural machine translation task it is preferable to look ahead at next word before encoding a given word
* So all the queens will be having different embeddings
* Run 2 RNNs on the same input, one is reading from L to R and another is reading from R to L
* Combine the output at each time step by concatenating them
* Tf.keras.layers.BiDirectional(tf.keras.layer.GRU(Units))&#x20;
*

    <figure><img src="../.gitbook/assets/image (3) (2).png" alt=""><figcaption></figcaption></figure>
* Can be used inside encoder-decoder architecture
* And also for NMT
* Encoder -> Embeddings -> LSTM -> Dense
* Masking means adding passing like EOS, BOS etc
* Libraries to explore:

1. Ktrain
2. Pytorch lighning
3. Hugging face

&#x20;
