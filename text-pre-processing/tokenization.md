---
hidden: true
---

# Tokenization

### Tokenization:

* <mark style="color:purple;background-color:purple;">**Break sentence into words**</mark>
* If we are building a spam classifier
* Dataset:

| Email Body         | Email Subject | Output |
| ------------------ | ------------- | ------ |
| You won $1000000   | Billionaire   | Spam   |
| Hi, How are you    | Hello         | HAM    |
| Credit cards worth | Winner        | Spam   |

* We cannot feed this text directly to Algo
* So we need to use:
* Tokenization, Stemming, Stopwords, Lemmatization

