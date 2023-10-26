# Code



```python
// Some code
nltk.sent_tokenize(corpus) --> to tokenize corpus into sentences

stemmer = PorterStemmer()
stemmer.stem('thinking') --> think

lemmatizer = WordNetLemmatizer()
lemmatizer.lemmatize('goes') --> go

# clean the data
loop the corpus sentence
re.sub('[^a-zA-Z]','',sentence)
append into a new list corpus

loop the corpus sentence
loop the words of sentence
if work is not a stopword
do stemming

# Bag of words
from sklearn.feature_extraction.text import CountVectorizer
cv = CountVectorizer()
# can add parameter ngram_range = (1,3)
X = cv.fit_transform(corpus)
cv.vocabulary_ --> to see all the words and their occurences
X[0].toarray() --> to see the BOW for the 1st sentence

# Tf-IDF:
from sklearn.feature_extraction import TfidfVectorizer
cv = TfidfVectorizer()
X = cv.fit_transform(corpus)
```

[https://github.com/hiteshbwankhede/NLPCodes/blob/main/Text%20Preprocessing.ipynb](https://github.com/hiteshbwankhede/NLPCodes/blob/main/Text%20Preprocessing.ipynb)
