# Overview

* Long short term memory
* This NN can remember the context
* If the sentence is long then RNN wont be able to remeber the context
* 4 main sections
*

    <figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>
* Cross is known as point-wise operation
* Plut means point-wise addition
* The cross between ct-1 and ft is known as memory cell
* Memory cell indicates need to remember something and need to forget something
* 2 lines joining(ht-1 and xt) is concatenation
* \+ means we are adding more info
* if the sentence is like: krish like YT. Yan lekun likes ML
* Here the NN need to forget about Krish and remember about Yan
* Once the information is added, we normalize it and pass it to output
