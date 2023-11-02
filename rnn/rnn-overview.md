# RNN Overview

* Till now for converting text to vectors, the most efficient way till now was word2vec and avgword2vec(Word embedding)
* For chatbot, we ask Q and we get A
* In such case sequence of words is very important
* Same applies for language translate, here also sequence and grammar is very important
* Text generation, for completion of sentence&#x20;
* For such tasks we need DL techniques like RNN, LSTM , RNN, Transformers and BERT

**Basic architecture of RNN:**

* Output is sent back to NN
*

    <figure><img src="../.gitbook/assets/image.png" alt="" width="327"><figcaption></figcaption></figure>
*

    <figure><img src="../.gitbook/assets/image (1).png" alt="" width="375"><figcaption></figcaption></figure>
* Output is given to the next timestamp of NN
*

    <figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
