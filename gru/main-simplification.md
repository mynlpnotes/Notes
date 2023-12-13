# Main Simplification

1\.      Both states vectors merged into a single vector

2\.      Single gate controller z(t) controls – input gate and forget gate

If z(t) -> 1            forget gate = 1

&#x20;                             Input gate = 1 – 1 = 0      Closed

If z(t) -> 0            forget gate = 0

&#x20;                             Input gate = 1 – 0 = 1      Open

Whenever a new information is written in memory, erase that location or erase previous memory

<figure><img src="../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

3\.      Full state vector h(t) is the output at every time stamp

4\.      Reset gate R(t) controls which part of the previous state will be shown to g(t) main layer

If r(t) = 0, we don’t want to pass any previous information, we want to pass only fresh information

If r(t) = 1, we pass previous + fresh

\-       &#x20;

<figure><img src="../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>
