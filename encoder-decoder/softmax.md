# Softmax



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
