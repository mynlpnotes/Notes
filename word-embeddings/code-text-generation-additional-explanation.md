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

