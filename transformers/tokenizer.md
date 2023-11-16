# Tokenizer

{% embed url="https://colab.research.google.com/drive/1Z2I-LDfMjPmbqq_kWYHTcWF_dFs6WimT?authuser=1" %}

```python
from transformers import BertTokenizer, AutoTokenizer
model_name = "bert-base-cased"
tokenizer = BertTokenizer.from_pretrained(model_name)
auto_tokenizer = AutoTokenizer.from_pretrained(model_name)

example = "Transformer is an interesting library"
tokenizer(example)
auto_tokenizer(example)
# Results of both the tokenizer will be same, as same model is used in both

# Save and load the tokenizer
tokenizer.save_pretrained("./sample_tokenizer")
loaded_tokenizer = AutoTokenizer.from_pretrained("./sample_tokenizer")

# Get tokens
tokens = tokenizer.tokenize(example)
Output: ['Trans', '##former', 'is', 'an', 'interesting', 'library']

# Get ids from token
ids = tokenizer.convert_tokens_to_ids(tokens)
Output: [13809, 23763, 1110, 1126, 5426, 3340]

# Ids to token
tokenizer.convert_ids_to_tokens(updated_ids) 
tokenizer.decode(ids) --> Transformer is an interesting library

# Handling multiple sequences
ckpt = "distilbert-base-uncased-finetuned-sst-2-english"
tokenizer = AutoTokenizer.from_pretrained(ckpt)
model = AutoModelForSequenceClassification.from_pretrained(ckpt)

tokens = tokenizer.tokenize(example)
ids = tokenizer.convert_tokens_to_ids(tokens)
input_ids = torch.tensor(ids)
tensor([ 1045,  1005,  2310,  2042, 11131, 19081,  2005,  3019,  2653,  6364])

model(input_ids) --> This will give error

# When we unsequeeze it becomes, 
# tensor([[ 1045,  1005,  2310,  2042, 11131, 19081,  2005,  3019,  2653,  6364]])
model(torch.unsqueeze(input_ids, dim=0))

# Inputs of different lenght
batch_id = [id_1,id_2] # Lenght of id1 and id2 is different
model(torch.tensor(batch_id)).logits --> This will give error

# Make the inputs same lenght by using padding
max_len = 11
while  len(id_2)!= max_len:
  id_2.append(tokenizer.pad_token_id)
# Now if we pass to the model, we will get result however the example for which we 
# added paddding wont give correct result, as unnecessary attention is being
# given to padding, so we need to pass attention mask also to the model
attention_mask = [[1]*11,[1]*7 + [0]*4]
model(
    torch.tensor(batch_id), 
    attention_mask=torch.tensor(attention_mask)
    ).logits
```
