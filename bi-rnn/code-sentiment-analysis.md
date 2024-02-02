# Code - Sentiment Analysis

```python
# This will download dataset as tf
dataset, info = tfds.load(dataset_name, with_info=True, as_supervised=True)
# info can be used to get info about the data

dataset.keys()
#Output: dict_keys(['test', 'train', 'unsupervised'])

# Form train and test set
train_ds, test_ds = dataset["train"], dataset["test"]

# To show the 1st 3 records
for example, label in train_ds.take(3):
  print(f"sample text:\n{example.numpy()}\n")
  print(f"label:\n{label.numpy()}\n")

train_ds = train_ds.shuffle(Config.BUFFER_SIZE).batch(Config.BATCH_SIZE).prefetch(tf.data.AUTOTUNE)
test_ds = test_ds.batch(Config.BATCH_SIZE).prefetch(tf.data.AUTOTUNE)

encoder = tf.keras.layers.TextVectorization(max_tokens=Config.VOCAB_SIZE)
encoder.adapt(train_ds.map(lambda text, label: text))




```
