# Login and Sharing

{% embed url="https://colab.research.google.com/drive/1YzOU41YKpwgCJBPShsvTJQlzU-YAUyb9?authuser=1" %}

```python
git config --global user.name "c17hawke"
git config --global user.email "sunny.c17hawke@gmail.com"
git lfs install

from huggingface_hub import notebook_login
notebook_login()

local_model = AutoModelForSequenceClassification.from_pretrained("./example_model")
local_model.push_to_hub("example-model-FSDS", use_auth_token="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")
```
