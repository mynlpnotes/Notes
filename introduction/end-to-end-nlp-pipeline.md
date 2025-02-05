---
hidden: true
---

# End to End NLP pipeline

1. **Data acquisition:**

* Available data -> csv, pdf, excel, db
* Other data -> scrape, API
* No data -> Create your own data
* if data is then do <mark style="color:purple;background-color:purple;">**augmentation**</mark>
* <mark style="color:purple;background-color:purple;">**Replace with synonyms**</mark>
* <mark style="color:purple;background-color:purple;">**Back translations**</mark>
* Additional noise - Add noise, unwanted information

2. **Text preparation:**

* <mark style="color:purple;background-color:purple;">**Text clean up:**</mark>
* <mark style="color:purple;background-color:purple;">**Remove html tags, emoji, spell corrections**</mark>
* <mark style="color:purple;background-color:purple;">**Basic preprocessing: Tokenization**</mark>
* <mark style="color:purple;background-color:purple;">**Optional preprocessing:**</mark>
* <mark style="color:purple;background-color:purple;">**Stopword removing, stemming, lemmatization, lowercase**</mark>
* <mark style="color:purple;background-color:purple;">**Language detection**</mark>
* <mark style="color:purple;background-color:purple;">**Remove punctuation**</mark>
* Advances preprocessing:
* POS tagging
* Parsing
* Coreference resolution

3. **Feature engineering:**

* <mark style="color:purple;background-color:purple;">**Text representation/ Text vectorization**</mark>
* <mark style="color:purple;background-color:purple;">**BOW**</mark>
* <mark style="color:purple;background-color:purple;">**tf-idf**</mark>
* <mark style="color:purple;background-color:purple;">**One-hot encoding**</mark>
* <mark style="color:purple;background-color:purple;">**ngrams**</mark>
* <mark style="color:purple;background-color:purple;">**word2vec**</mark>

4. **Modelling:**

* Heuristic approach/ ML/ DL

5. **Evaluation:**

* Intrinsic evaluation - f1, auc, recall
* Extrinsic evaluation - done by users

6. **Deployment:**
7. **Monitoring and model updating**
