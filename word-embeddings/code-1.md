# Code



```python
// Some code
import gensim
from gensim.model import Word2Vec, KeyedVectors
import gensim.downloader as api

wv = api.load('word2vec-google-news-300') --> This model is about 1.5GB
vec_king = wv['king'] --> this will return vector of 300 dimensions

wv.most_similar('man') --> will return list of tuples of word and cosine similarity

wv.similarity('man','king') --> will return cosine similarity
```
