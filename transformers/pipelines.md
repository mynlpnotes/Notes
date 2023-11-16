# Pipelines

{% embed url="https://colab.research.google.com/drive/1Z2hcnP3jc8jUnbs3zV2EYU41gKj9uyXl?authuser=1" %}

**Behind the scene of Transformer(Pipeline):**

* Raw Text --> It goes into tokenizer --> IDs will be generated --> Model --> Outcome(In the form of logits) --> Post processing --> Prediction



```python
from transformers import AutoTokenizer
ckpt = "distilbert-base-uncased-finetuned-sst-2-english"
tokenizer=AutoTokenizer.from_pretrained(ckpt)
inputs = "I love my country"
tokenizer(inputs)
{'input_ids': [101, 1045, 2293, 2026, 2406, 102], 
'attention_mask': [1, 1, 1, 1, 1, 1]}
# Here we are getting output as 6 numbers, we getting BOS and EOS extra

# we can also pass in batch
out = tokenizer(batch_input, padding=True)
{'input_ids': [[101, 1045, 2293, 2026, 2406, 102, 0, 0, 0, 0, 0, 0], 
[101, 1045, 2572, 11559, 1998, 1045, 2147, 1999, 1999, 11236, 2239, 102]], 
'attention_mask': [[1, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0], 
[1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]]}
# here we see padding is given value as 0 and its attention mask is also 0

# if we want tensors as output
# pt - pytorch
# tf - tensor
out_pytorch_tensors = tokenizer(batch_input, padding=True, return_tensors="pt")
{'input_ids': 
tensor([[  101,  1045,  2293,  2026,  2406,   102,     0,     0,     0,     0,
             0,     0],
        [  101,  1045,  2572, 11559,  1998,  1045,  2147,  1999,  1999, 11236,
          2239,   102]]), 
          'attention_mask': tensor([[1, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0],
        [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]])}

# Lets pass this tensors to model
from transformers import AutoModel
model_ckpt = AutoModel.from_pretrained(ckpt)
model_ckpt # to view the model summary

logits = model_ckpt(**out_pytorch_tensors) # Output below
batch_size, sequence_len, Hidden_state= logits["last_hidden_state"].shape
Output: (2, 12, 768)

from transformers import AutoModelForSequenceClassification
model_2 = AutoModelForSequenceClassification.from_pretrained(ckpt)
pred = model_2(**out_pytorch_tensors)
Output:
SequenceClassifierOutput([('logits', tensor([[-4.2268,  4.5594],
                                   [-3.8146,  4.0510]], grad_fn=<AddmmBackward0>))])
pred_prob = torch.nn.functional.softmax(pred.logits, dim=1)
model_2.config.id2label
torch.argmax(pred_prob, dim=-1)
Output:
tensor([1, 1])
```

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption><p>Output of logits</p></figcaption></figure>
