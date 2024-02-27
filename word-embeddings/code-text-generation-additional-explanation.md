# Code - Text Generation - Additional Explanation



**Buffer Size:**

* If we keep buffer size = 10000, it will keep 10000 records in memory(RAM), for training it will pick randomly 10000, and after record is picked up, it will be replaced with data from local
* This increases speed

**Embedding Dimension:**

* Each letter will be represented into a vector of size 256
* There will be a embedding loop up table and for each letter there will be a embedding of 256

**Return Sequence:**

* If return sequence = True, it will take input and give output
* If return sequence = False, then it will take all the inputs and give output at the end
*

    <figure><img src="../.gitbook/assets/image (4) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

**Stateful RNN:**

* One epoch to next epoch, if we are passing the hidden state values that is known as stateful RNN = True
* One epoch to next epoch, you will reset the hidden state with stateful = False
* Advantage of stateful RNN is it will try to rememver the long sequences

**Logits:**

* We are taking the raw output here, without any output function, not using softmax function here

**Epoch 1/32:**

* 172/172
* This number comes from batch size / (sequence length + 1)

When we save the checkpoints, we are not saving the architecture, we are saving only the weights

**Temperature:**

* \[0.75, 0.2, 0.3]
* It divides by temperature to reduce the values
* It's kind of normalization
* If low temperature, then it means more predictable
* If high temperature, then more surprising text



* &#x20;predicted\_id = tf.random.categorical(predictions, num\_samples=1) -> \[\[3]] \[\[3]]
* &#x20;predicted\_id = tf.random.categorical(predictions, num\_samples=1)\[-1] -> \[3] \[3]
* &#x20;predicted\_id = tf.random.categorical(predictions, num\_samples=1)\[-1,0].numpy()
* If prediction = \[1,2,3,4] -> Output mostly 1,2,3,4
* If prediction = \[1,2,3,4,55] -> Output mostly 4th index
* If prediction = \[1,2,3,4,55,56] -> Output mostly 4th or 5th index
* If prediction = \[1,2,3,4,55,100] -> Output mostly 6th index
* If prediction = \[1,2,3,4,55,100,101] -> Output mostly 6th and 7th index
* If prediction = \[1,2,3,4,55,100,101,200] -> Output mostly 8th index
* if we use softmax then it will give output with the highest probability but sometimes even the nearby values can be right, so we use this code



*

    <figure><img src="../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
* Lets say start sequence is ROMEO
* Our model takes 1 character input and gives the probability of 65 values
* We 1st convert input into array of index of characters of the input
* In 2nd line we are expanding the dimension, because we normally pass batch, but here we will be passing single values
* We dividing logit values by temperature, and so the difference between the values will reduce
* So if we apply random.categorical then chance of probabily distribution of values will increase
* It will give surprising text
* If we use temp = 0.5 then difference will increase



* Encoder/Decoder can be used for translation/ summarization
