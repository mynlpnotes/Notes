# Basics

{% embed url="https://colab.research.google.com/drive/1Z225POCS48821D5TrshjmXkal-bydKvJ?authuser=1" %}

```python
// Basics
!pip install datasets transformers[sentencepiece] -q
from transformers install pipeline

# This will download default model
classifier = pipeline("sentiment-analysis")
classifier("I love my country")
Output: [{'label': 'POSITIVE', 'score': 0.9998471736907959}]

# We can pass multiple sentences also, it will give 1 output for each sentence
classifier(["I love my country", "I didn't like the movie last night"])

# Zero shot classification
classifier_zero_shot = pipeline("zero-shot-classification")
classifier_zero_shot(
    "This course is about artificial intelligence, Here we will learn ",
    candidate_labels=["politics", "business", "education"],
)
{'labels': ['education', 'business', 'politics'],
 'scores': [0.49157801270484924, 0.3949519693851471, 0.11347001045942307]}
 
 # Text-generation
generator = pipeline("text-generation")
generator("This course is about artificial intelligence")[0]["generated_text"]

# Can also specify model to be used
generator = pipeline("text-generation", model="distilgpt2")
# This will return 3 outputs of lenght 40
generator("This course is about artificial intelligence",
          max_length=40,
          num_return_sequences=3)

# Unmasking
unamasking = pipeline("fill-mask")
unamasking("This course is about <mask> intelligence", top_k=3)
[{'score': 0.39746421575546265,
  'sequence': 'This course is about artificial intelligence',
  'token': 7350,  'token_str': ' artificial'},
 {'score': 0.046897199004888535,
  'sequence': 'This course is about gathering intelligence',
  'token': 5660,  'token_str': ' gathering'},
 {'score': 0.033793091773986816,
  'sequence': 'This course is about cyber intelligence',
  'token': 5381,  'token_str': ' cyber'}]

# Named entity recognition
NER = pipeline("ner", grouped_entities=True)
NER("I am Sunny and I work in iNeuron Intelligence. I live in Bangalore.")

# QA
QA = pipeline("question-answering")
QA(
    question="Wher do I work?",
    context="I am Sunny and I work in iNeuron Intelligence. I live in Bangalore."
)
{'answer': 'iNeuron Intelligence','end': 45,'score': 0.9462348222732544, 'start': 25}

# Summarization
summarization = pipeline("summarization")
summarization(in_text, max_length=56)[0]["summary_text"]

# Translation
translator = pipeline('translation', model="Helsinki-NLP/opus-mt-fr-en")
translator = pipeline('translation', model="Helsinki-NLP/opus-mt-hi-en")
translator("je bois du lait")
Output: [{'translation_text': 'I drink milk'}]


```

* **Pre-training:** Training from scratch
* **Transfer learning:** Fine tuning
