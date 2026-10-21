# Parley translation models: notice and credits

The files in this repository (the zip packs in the releases) are **converted copies** of machine translation models of the
**OPUS-MT** project of the **Helsinki-NLP** group (University of Helsinki), https://github.com/Helsinki-NLP/Opus-MT ,
published on Hugging Face under https://huggingface.co/Helsinki-NLP . The original models are licensed under the
**Apache License 2.0** (see `LICENSE-Apache-2.0.txt`; the model cards on Hugging Face say `license: apache-2.0`).

**What we changed** (these are not the original files): the PyTorch weights were converted to ONNX, the vocabulary of every model
was cut to the pieces of its source language (encoder) and of its target language (decoder), and the weights were compressed to
8-bit integers (ONNX Runtime dynamic quantization). The translations of a compressed model can differ a little from the original.
The compression was done by the Parley project, not by Helsinki-NLP; Helsinki-NLP is not responsible for these files.

| Pack | Original model | Original weights (SHA-256 of `pytorch_model.bin`) |
|---|---|---|
| `uk-ru` | Helsinki-NLP/opus-mt-uk-ru | d37f1b9677cdd6c2d9d1c4082974b5ae33d8c467f06354a669ba71d17437f2ba |
| `ru-uk` | Helsinki-NLP/opus-mt-ru-uk | 17be9cacd6e9df1d9be09ad3ae50bebeac76a6cf982d1330c587279113595fc9 |
| `en-ru` | Helsinki-NLP/opus-mt-en-ru | d15fa58c6bc3efd3629c1b6b86d9aa6d15d2751a4620aa4cdd7eed7b5cbe583b |
| `ru-en` | Helsinki-NLP/opus-mt-ru-en | 535450eb5613f3cc912f9ca3e54cfef6c14d201b319c24a88faf776a65538b5d |
| `uk-en` | Helsinki-NLP/opus-mt-uk-en | db67251736c28c6c703ce2ad11fbf2134f0d95b7ef053352d9e9df0f1b7ec633 |
| `en-uk` | Helsinki-NLP/opus-mt-en-uk | 1fc8dc07ff5880253c0a51946f28ee4977efb84fa4e4586258994845b7384780 |

The models were trained on OPUS data (https://opus.nlpl.eu). The Parley app runs them on the phone through ONNX Runtime (MIT);
no text leaves the phone.

If you use the models, please cite: J. Tiedemann and S. Thottingal, "OPUS-MT: Building open translation services for the World",
EAMT 2020.
