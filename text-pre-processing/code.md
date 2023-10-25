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
X = cv.fit_transform(corpus)
cv.vocabulary_ --> to see all the words and their occurences
X[0].toarray() --> to see the BOW for the 1st sentence
```

{% @github-files/github-code-block url="https://github.com/hiteshbwankhede/NLPCodes/blob/main/Text%20Preprocessing.ipynb" %}
