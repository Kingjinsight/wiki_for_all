# Hugging Face Transformers

It is a popular open-source python library. It provides easy access to thousands of pre-trained models to do inference and training.

## Pipeline

It is the most convenient way to inference with a pretrained model

```python
from transformers import pipeline, infer_device

device = infer_device() # infer_device() can automatically detect an available accelerator for inference

text_generator = pipeline("text-generation", model="meta-llama/Llama-2-7b-hf", device=device)
```
