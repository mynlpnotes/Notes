# Introduction

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

\-        Cannot use proximity to understand/gain info from the sentence

\-        We may think Roopali is a person, but she is a cow

\-        We can think annoying is related to rooplai, can, be , but, she, is

\-        Our focus is needs to be in roopali, she, cow, annoying

\-        If we pass this to normal RNN, then it will be difficult to understand where to focus more

\-        We convert text into tokens, t1 t2…..

\-        Then we convert them into vectors

\-        If we want to give importance to any vector, then we can come up with some mechanism of weight w1, w2…..

\-        This will result into new vector y1, y2….

\-        This will be trainable weights

\-        This y1, y2.. will be able to give more contextual information

\-        We need to train in such a way that w1, w4, w6 and w10 should be more

\-        ![](<../.gitbook/assets/image (1).png>)

\-        In both the sentences, both the bank are having different meaning, which we get after reading the entire sentence

\-        If sentence has bank and river then it means we are talking about a water body

\-        If sentence has state, bank, india then it means we are talking about a financial institution

\-        Since both the banks have different meaning, so it should be encoded differently

\-        Also attention should be given differently

\-        So we multiply it with attention weights – W1, W2….

\-        This weights are trainable

\-        ![](<../.gitbook/assets/image (2).png>)

\-        We first encode the sentence – V1

\-        Then apply re-weigh mechanism

\-        This will contain better context information

\-        We do dot product

\-        ![](<../.gitbook/assets/image (3).png>)

\-        When we do dot product of 2 vectors, we get scalar – W1, W2….

\-        After that we normalize them

\-        Similarly we do for V2.V1 also….

Key-points:

1\.      We have not trained any weights

2\.      Order will not have any influence

3\.      Proximity has no influence

4\.      Shape independent

\-        This process of doing re-weighing is knows as self-attention

\-        ![](<../.gitbook/assets/image (4).png>)

1\.      DOT PRODUCT

2\.      This fives some scores, which is passed to normalization

3\.      After having this weights, we multiply it with their respective vectors

4\.      Similarly we do for all vector – V1, V2, V3, V4

\-        This are called attention blocks

\-        There are no trainable weights here

\-        If we call V3 as QUERY

\-        V1, V2, V3, V4 as KEYS

\-        V1, V2, V3, V4 when multiplying is known as VALUES

\-        To introduce weights, there will be a vector MQ which can be multiplied with QUERY

\-        Similarly MK can be multiplied with KEYS

\-        MV can be multiplied with VALUES

\-        They are randomly initialized

\-        The dimension after multiplication should not change

\-        So if Vi is 1XK then M will be KXK so output will be 1Xk

\-        Representing the same in a different manner

\-        ![](<../.gitbook/assets/image (5).png>)

\-        We are doing linear transformation by multiplying vector with matrices

\-        DOT product of query and keys is done after that

\-        This will give some scores(which are vectors)

\-        After that we do normalization

\-        This will give some weights Wij

\-        After that we do matrix multiplication by multiplying weight with values

\-        This is known as attention blocks

\-        We can also stack attention blocks

\-        In operations like NER,

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

To extract information like this to get name, place, org we need attention mechanism

\-        In backpropagation, the context Y1… will not be correct, so it backpropagate and the randomly initialized matrices will be updated

\-        Here it is not sequential approach, we are not passing sequentially

\-        Some times one matrix might not be enough, so we can have multi attention mechanism (AM1 for name, AM2 for place, AM3 for Org)

\-        ![](<../.gitbook/assets/image (7).png>)

\-        This are called heads

\-        If we have 3 different matrices

\-        Then we will get 3 different scores and 3 different weight matrixes

\-        After that we concatenate and dense

\-        This is known as muti head attention

\-        This multi head attention blocks can also be stacked

\-        ![](<../.gitbook/assets/image (8).png>)

\-        In his way, we can get more context

&#x20;

Attention is all you need – Paper:

\-        ![](<../.gitbook/assets/image (10).png>)

Scaled dot product:

\-        ![](<../.gitbook/assets/image (11).png>)

\-        Scaling done to avoid vanishing gradient

\-        d = length of the embedding

\-        Masking is optional

\-        Scores will be passed to softmax, which when done matrix multiplication with V we get Y1, Y2….

\-        Masking is for adding noise, its like forcing to learn is something is missing, like even if am is missing then also it learns

\-        ![](<../.gitbook/assets/image (12).png>)

\-        It is having encoder and decoder, here instead of RNN we are using attention blocks
