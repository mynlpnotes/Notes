---
hidden: true
---

# TF-IDF

* Term frequency - Inverse document frequency
* D1: good boy
* D2: good girl
* D3: good boy girl
* Good is present in all the sentences, so its importance should be less
* Rare words should be given more importance when creating vectors
* **TF = Number of repetitions of words in the sentence / No. of words in the sentence**
* **IDF = loge (No. of sentences / No. of sentences containing the word)**
* **Term Frequency:**

<table><thead><tr><th width="157"></th><th>D1</th><th>D2</th><th>D3</th></tr></thead><tbody><tr><td>Good</td><td>1/2</td><td>1/2</td><td>1/3</td></tr><tr><td>Boy</td><td>1/2</td><td>0</td><td>1/3</td></tr><tr><td>Girl</td><td>0</td><td>1/2</td><td>1/3</td></tr></tbody></table>

* **IDF:**

| Words | IDF          |
| ----- | ------------ |
| Good  | log(3/3) = 0 |
| Boy   | log(3/2)     |
| Girl  | log(3/2)     |

* **TF-IDF:**

<table><thead><tr><th width="132"></th><th>Good</th><th>Boy</th><th>Girl</th></tr></thead><tbody><tr><td>D1</td><td>1/2 * 0</td><td>1/2 * log(3/2)</td><td>0 * log(3/2)</td></tr><tr><td>D2</td><td>1/2 * 0</td><td>0 * log(3/2)</td><td>1/2 * log(3/2)</td></tr><tr><td>D3</td><td>0</td><td>1/3 * log(3/2)</td><td>1/3 * log(3/2)</td></tr></tbody></table>

* So some amount of semantic information in the captured in the form of importance of words



| Advantage                           | Disadvantage         |
| ----------------------------------- | -------------------- |
| Intuitive                           | Complex calculations |
| Word importance is getting captured | Sparse matrix        |
|                                     | OOV                  |
