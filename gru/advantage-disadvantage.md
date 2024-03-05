# Advantage/Disadvantage

* They still have hard time learning long term patterns in sequences of 100+ timesteps

**Solution:**

* Use conv1D to shorten the sequences
* Here it’s just a 1D array over which we need to convolve
*   If sequence is of 100, filter = 4, padding = 0, then it will be 49 timestamps

    <figure><img src="../.gitbook/assets/image (7) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

GRU has fewer activation functions as well as FC units, hence it is faster than LSTM

<figure><img src="../.gitbook/assets/image (8) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
