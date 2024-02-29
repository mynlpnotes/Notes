# CBOW

* Continuous BOW
* Corpus:

1. Krish channel is related to data science

Training steps:

* Decide window size
* Training data:
* if window size is 5, middle word will be output and the remaining will be context word, we will slide the window and continue
* Window size is hyper-parameter, the bigger the size the better the model



| Independent Feature         | Output  |
| --------------------------- | ------- |
| KRISH, CHANNEL, RELATED, TO | IS      |
| CHANNEL, IS, TO, DATA       | RELATED |
| IS, RELATED, DATA, SCIENCE  | TO      |

* Aim is to take the text and generate vectors
* The vectors should be such that sematic meaning should be captured
* BOW:



| Word    | Vectors        |
| ------- | -------------- |
| KRISH   | 1 0 0 0 0 0 0  |
| CHANNEL | 0 1 0 0 0 0 0  |
| IS      | 0 0 1 0 0 0 0  |

* This we will be giving to ANN
*

    <figure><img src="../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
* Softmax used for multi class classification
* During forward propagation loss will be calculated and in backward propagation weights will be updated
*

    <figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
* The weights of the nodes which are connecting from hidden layer to the output neuron will be the vectors of the word
* Window size = No. of neurons in hidden layer = No. of dimensions used for vectors
