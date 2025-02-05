---
hidden: true
---

# Bag of words

**Corpus:**

* D1: He is a good good boy
* D2: She is a good girl
* D3: Boy and girl are good

After removing stopwords:

* good good boy
* good girl
* boy girl good

**Vocabulary:**

* Good: 4
* Boy: 2
* Girl: 2

The order of the features will be based on the frequency



| Good | Boy | Girl |
| ---- | --- | ---- |
| 2    | 1   | 0    |
| 1    | 0   | 1    |
| 1    | 1   | 1    |

**Binary bag of words:**&#x20;

* if words if present then make it 1 irrespective of count



| Advantage | Disadvantage                         |
| --------- | ------------------------------------ |
| Simple    | Sparse                               |
|           | OOV                                  |
|           | Ordering of the words gets changed   |
|           | Not able to capture semantic meaning |



* The food is good
* The food is not good
* If we remove stopwords and then do BOW then if we calculate the distance between the matrix for the 2 sentences then it will be almost same
* So there is no semantic value
* Since there is no semantic value, each word is given equal importance
