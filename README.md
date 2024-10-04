# MedNLLB-200

## Overview

The **medical-nllb-200-zh2en** project designed specifically for translating medical texts from Chinese to English. Built on the No Language Left Behind (NLLB) framework, this model aims to enhance the accuracy and fluency of translations in the medical domain, facilitating better communication and understanding in healthcare settings.

## Features

- **High Accuracy**: Utilizes advanced NLLB technology for precise translations.
- **Medical Focus**: Specific for translating medical literature, patient records, and related documents.
- **User-Friendly**: Easy integration into existing workflows and applications.

## Installation

To use the model, you need to have the `transformers` library installed. You can install it via pip:

```bash
pip install transformers
```

## Usage

Here’s a simple example demonstrating how to use the [**medical-nllb-200-zh2en**](https://huggingface.co/6yuru99/medical-nllb-200-zh2en/tree/main) model for translation:

```python
from transformers import AutoTokenizer, AutoModelForSeq2SeqLM

# Load the tokenizer and model
model_name = "6yuru99/medical-nllb-200-en2zh_hant"
model = AutoModelForSeq2SeqLM.from_pretrained(model_name)
tokenizer = AutoTokenizer.from_pretrained(model_name, src_lang="zho_Hant")

# Example Chinese medical text
input_text = "患者有高血壓病史，需定期檢查血壓。"

# Tokenize the input text
inputs = tokenizer(input_text, return_tensors="pt")

# Generate translation
translated_tokens = model.generate(**inputs, forced_bos_token_id=tokenizer.convert_tokens_to_ids("eng_Latn"))

# Decode the translated text
outputs = tokenizer.batch_decode(translated_tokens, skip_special_tokens=True)[0]

print("Translated Text:", outputs)
```

## Contributing

Welcome contributions to improve this project! If you have suggestions or improvements, please feel free to submit a pull request or open an issue.

## Contact

For any inquiries or feedback, please contact the project maintainer at [6yuru99@gmail.com].
