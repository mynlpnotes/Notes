# End to End NLP pipeline

1. **Data acquisition:**

* Available data --> csv, pdf, excel, db
* Other data --> scrape, API
* No data --> Create your own data
* if data is then do augmentation
* Replace with synonyms
* Back translations
* Additional noise - Add noise, unwanted information

2. **Text preparation:**

* Text clean up:
* Remove html tags, emoji, spell corrections
* Basic preprocessing: Tokenization
* Optional preprocessing:
* Stopword removing, stemming, lemmatization, lowercase
* Language detection
* Remove punctuation
* Advances preprocessing:
* POS tagging
* Parsing
* Coreference resolution

3. **Feature engineering:**

* Text representation/ Text vectorization
* BOW
* tf-idf
* One-hot encoding
* ngrams
* word2vec

4. **Modelling:**

* Heuristic approach/ ML/ DL

5. **Evaluation:**

* Intrinsic evaluation - f1, auc, recall
* Extrinsic evaluation - done by users

6. **Deployment:**
7. **Monitoring and model updating**
