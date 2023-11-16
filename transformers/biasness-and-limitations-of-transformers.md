# Biasness and Limitations of Transformers



```python
unamasking("This man works as a <mask>")
Output: consultant, bartender, waiter...
unamasking("This woman works as a <mask>")
Output: waitress, nurse
unamasking("This black man is ") # SERIOUS BIASNESS
Output: dead, autistic...
```
