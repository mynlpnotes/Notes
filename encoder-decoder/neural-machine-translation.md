# Neural Machine Translation

**Language translation:**

* English -> Hindi or Kannada or any language
* In this case, English is also information, and hindi is also information
* But their meaning is same
* For this we need encoder and decoder architecture
* Encode the English into some numbers/vectors
* And then decode it into some other language
* One to one mapping between the languages is not possible
*

    <figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
* In English it is 3 words, If we decode then this will be 4 words in French
* Similarly for hindi as well
*

    <figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
* Embedding layer will convert numbers into vectors
* This word vectors we will feed to RNN
* We have reversed the input sequence here
* We are not using any output here, we will be using last value here and passing it to decoder
* We have embedding lookup for target language
* 1st character is \<sos> and at end we use \<eos>
* This target language embeddings are passed to decoder
* The outputs will be passed to softmax layer
* Softmax will give probability of sentence
* In the prediction there was 1 wrong value
* Encoding for English and hindi will be different
*

    <figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
* At x(0) there is no previous input, its output will go as hidden state to x(1)
* Embedding of drink and hidden state will go to 2nd RNN
* Its hidden state will go to next RNN and so on
* This encoded information will be in the form of array and this will go to decoder
* We should decode the 1st value of the encoder so that it becomes the 1st decoded value, that’s why we have reversed the input
* In decoder, the encoded value of I will be passed and it will be decoded
* This decoded value will be passed to the next RNN along with the next information
* \<sos> and encoded value of I, will give decoded value as main
* Embedding lookup will be randomly generated
*

    <figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
* (in this diagram it is not group of RNN, it is rolled over time)
* We compared target and predicted
* There are only 2 mistakes
* So weights of this RNNs will be updated, and the embedding lookup will also be updated and it will backpropagate all the previous RNN and then weights and embedding lookup of encoder as well
* Embedding layer for English as well as hindi will be updated
* RNNs of encoder and decoder will learn the sequence
* In encoder as well  \<eos> and \<sos> will be there
* This is used for model to understand when to start prediction and when to stop it

&#x20;

Sequence length:

\-        Sentences can be of different lengths

Today we going to learn NMT

After this we will be learning attention mechanism tomorrow

\-        While feeding to RNN, we need to specify sequence length

\-        For shorter sentence we can add padding

\-        For longer sentence we can split into 2

&#x20;

Softmax layer:

\-        ![](<../.gitbook/assets/image (4).png>)

\-        It will predict the probability of the word

&#x20;

\-        ![](<../.gitbook/assets/image (5).png>)

\-        Since machine does not understand text we will encode text into numbers

\-        Numbers are not appropriate representation of text

\-        So we embed them

\-        Which generate v1, v2, v3

\-        Encoder will take information v1 then v2 and then v3 and give embedded info

\-        Similarly decoder will take embedded info and embedded layer info of target and it will give output

\-        Softmax layer will give probability at each instance

\-        If softmax says that v1 is having the highest probability, then we will come to know that v1 is 1, so the 1st word is main

\-        If softmax does not give correct prediction, then it will be an error and the error will be back propagated

&#x20;

\-        ![](<../.gitbook/assets/image (6).png>)

\-        Here in decoder we wont pass any X now, we were passing earlier only for training

\-        Decoder will give some value at first instance, which will go to softmax, which will give maximum probability, which will be passed to embedding layer, from which we will get numeric value from which we will get the word

\-        At next instance, the output and the embedded info will be passed to the RNN and so on

&#x20;

\-        Pre-trained embedding layers are available

\-        That’s why transfer learning came into picture

\-        If we have a trained embedding layer of science fiction novel, then we can directly use it

\-        This is not used now

&#x20;

&#x20;

&#x20;
