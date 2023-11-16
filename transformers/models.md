# Models

{% embed url="https://colab.research.google.com/drive/1Z1HLgjDAMYUqr85b-8nN-Y6KnK7hJBFQ?authuser=1" %}

```python
from transformers import BertConfig, BertModel
config = BertConfig() # to get the config
# This will create a model architecture with newly init weights
# Model from scratch
model = BertModel(config) 

# Pre-trained
model_with_trained_wts = BertModel.from_pretrained("bert-base-cased")
# Save the model
model_with_trained_wts.save_pretrained("./model_dir")

# Pass sequence to model
# passing random sequence here
# we have to create sequence using tokenizer
encoded_sequences = [
    [101, 7592, 999, 102],
    [101, 4658, 1012, 102],
    [101, 3835, 999, 102],
]
model_ins = torch.tensor(encoded_sequences)
pred = model_with_trained_wts(model_ins)
```
