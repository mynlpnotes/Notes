# Architecture

*

    <figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>
*   **2 states:**

    i.                 C(t) – long term state – for remembering some info for longer duration

    ii.                H(t) – short term state – for remembering for shorter duration
* Idea behind 2 states: What to keep and what to discard
* **Components:**
*

    <figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>
* C(t-1) traverses the network from L to R, it forgets some memory or information with forget gate and adds new memory at input gate
* C(t-1) \* f(t), if f(t) = 0.5 then it means forgetting, f(t) can be between 0 and 1
* Short term information – h(t)
*   A copy of c(t) is transferred to tanh function to output state which produces short term memory, h(t) and output y(t)

    C(t) à tanh(-1,1) \* sigma(0,1) à h(t)
*

    <figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

**Types of gate:**

1. **Forget gate – f(t)**

* Controls which part of the long term state should be erased

2. **Input gate – I(t)**

* Controls which part of g(t) should be added to long term state

3. **Output gate – o(t)**

* Controls which part of the long term state c(t) should be kept
* Which part to be erased is done using FCC
*

    <figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>
* FCs are trained to learn what to forget and what to remember
