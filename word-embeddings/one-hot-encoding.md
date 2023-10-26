# One Hot Encoding

**Corpus:**

* A man eat food
* Cat eat food
* People watch Krish YT

**Vocabulary:** 9

D1 --> \[\[1 0 0 0],\[0 1 0 0], \[0 0 1 0], \[0 0 0 1]]

D2 --> \[\[1 0 0], \[0 1 0], \[0 0 1]]



| Advantage           | Disadvantage                                              |
| ------------------- | --------------------------------------------------------- |
| Simple to implement | Creates sparse matrix                                     |
|                     | OOV - Out of vocabulary                                   |
|                     | Sentences are not of same size -- Model cannot be trained |
|                     | Semantic meaning is not captured                          |



{% embed url="https://docs.google.com/document/d/1TkWOcsqSMJSW_Tlv3lkXJs7ALvWHcPj4/edit?ouid=104987430602659401377&rtpof=true&sd=true&usp=drive_link" %}
