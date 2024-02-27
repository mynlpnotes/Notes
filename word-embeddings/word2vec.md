# Word2Vec

* Feature representation
*

    <figure><img src="../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
* if we compare the cosine similarity between King - Man + Woman and Queen then it will be similar
* In previous techniques, semantic meaning is not captured and sparse matrix was getting captured
* We want that for similar words the vectors should also be similar
* If we are creating vectors using word2vec we can represent using limited dimensions
* Also the vectors which gets generated will maintain the semantic meaning



* Represent in form of vector
* Each word here is represent as 4X1 vector
*

    <figure><img src="../.gitbook/assets/image (10) (1).png" alt=""><figcaption></figcaption></figure>
* We can also plot them and every word can be represented as a point in space
* Angle between words can be taken as their similarity (cosine similarity)
* We can also cluster similar words
* Dense and efficient representation in which similar words can have similar encoding
* Elements inside these embeddings are trainable parameters
* Usually for smaller dataset à 8 dimensional vector
* Huge dataset à 1024 dimensional vector
* Higher dimension capture more details about relationship but it will mean more elements to learn/update, which will lead to slow training
*

    <figure><img src="../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>
