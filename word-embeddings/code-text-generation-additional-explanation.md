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
* \--------Add image from 41:00

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

