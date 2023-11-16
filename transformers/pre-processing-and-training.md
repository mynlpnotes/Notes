# Pre Processing and Training

{% embed url="https://colab.research.google.com/drive/1Z1KIfZHQP3jbLvlTC9oEYTnZO1LPRVxz?authuser=1#scrollTo=Mb8phzZv078U" %}

````python
```notebook-python
import torch
from transformers import AdamW, AutoTokenizer, AutoModelForSequenceClassification

ckpt = "bert-base-uncased"
tokenizer = AutoTokenizer.from_pretrained(ckpt)
model = AutoModelForSequenceClassification.from_pretrained(ckpt)
example = [
           "I've been exploring Transformers for Natural Language Processing",
           "I've been exploring Transformers"
          ]
batch = tokenizer(example, padding=True, truncation=True, return_tensors='pt')
batch["labels"] = torch.tensor([1,1])

optimizer = AdamW(model.parameters())
loss = model(**batch).loss
loss.backward() # Calculate the gradient
optimizer.step() # Update the weight

# Getting data from Hub
# Sentence 1 and 2 are equivalent or not
from datasets import load_dataset
raw_dataset = load_dataset("glue", "mrpc")
raw_dataset_train = raw_dataset["train"]
Dataset({
    features: ['sentence1', 'sentence2', 'label', 'idx'],    num_rows: 3668 })

raw_dataset_train.features
{'idx': Value(dtype='int32', id=None),
 'label': ClassLabel(num_classes=2, names=['not_equivalent', 'equivalent'], id=None),
 'sentence1': Value(dtype='string', id=None),
 'sentence2': Value(dtype='string', id=None)}
 
from transformers import AutoTokenizer
ckpt = "bert-base-uncased"
tokenizer = AutoTokenizer.from_pretrained(ckpt)

tokenized_sentence_1 = tokenizer(raw_dataset["train"]["sentence1"])
tokenized_sentence_2 = tokenizer(raw_dataset["train"]["sentence2"])

def tokenizer_func(example):
  return tokenizer(
    example["sentence1"],
    example["sentence2"],
    truncation=True)
tokenized_dataset = raw_dataset.map(tokenizer_func, batched=True)

# Dynamic mapping -- This will take care of the padding which we used to do earlier
from transformers import DataCollatorWithPadding
data_collator = DataCollatorWithPadding(tokenizer=tokenizer)

# Training
from transformers import TrainingArguments

training_args = TrainingArguments("test-trainer") 

from transformers import AutoModelForSequenceClassification
model = AutoModelForSequenceClassification.from_pretrained(ckpt, num_labels=2)

from transformers import Trainer
trainer = Trainer(
    model,
    training_args,
    train_dataset=tokenized_dataset["train"],
    eval_dataset=tokenized_dataset["validation"],
    data_collator=data_collator,
    tokenizer=tokenizer
)
trainer.train()
predictions = trainer.predict(tokenized_dataset["validation"])
preds = np.argmax(predictions.predictions, axis=-1) 
# We specify axis so that it is applied to all the rows

from datasets import load_metric
metric = load_metric("glue", "mrpc")
metric.compute(predictions=preds, references=predictions.label_ids)
{'accuracy': 0.8602941176470589, 'f1': 0.9018932874354562}

trainer.save_model("./example_model")
````
