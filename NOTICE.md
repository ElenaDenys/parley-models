# Parley translation models: notice and credits

The files in this repository (the zip packs in the releases) are **converted copies** of machine translation models of the
**OPUS-MT** project of the **Helsinki-NLP** group (University of Helsinki), https://github.com/Helsinki-NLP/Opus-MT ,
published on Hugging Face under https://huggingface.co/Helsinki-NLP . The original models are licensed under the
**Apache License 2.0** (see `LICENSE-Apache-2.0.txt`; the model cards on Hugging Face say `license: apache-2.0`), with ONE exception:
the model **English to German (`en-de`, Helsinki-NLP/opus-mt-en-de) is licensed under CC BY 4.0** (https://creativecommons.org/licenses/by/4.0/),
author: Helsinki-NLP. The pack `en-de` is a changed copy of that model (see below) and is shared under the same licence, CC BY 4.0.

**What we changed** (these are not the original files): the PyTorch weights were converted to ONNX, the vocabulary of every model
was cut to the pieces of its source language (encoder) and of its target language (decoder), and the weights were compressed to
8-bit integers (ONNX Runtime dynamic quantization). The translations of a compressed model can differ a little from the original.
The compression was done by the Parley project, not by Helsinki-NLP; Helsinki-NLP is not responsible for these files.

| Pack | Original model | Licence of the original | Original weights (SHA-256 of the weight file) |
|---|---|---|---|
| `uk-ru` | Helsinki-NLP/opus-mt-uk-ru | Apache-2.0 | d37f1b9677cdd6c2d9d1c4082974b5ae33d8c467f06354a669ba71d17437f2ba |
| `ru-uk` | Helsinki-NLP/opus-mt-ru-uk | Apache-2.0 | 17be9cacd6e9df1d9be09ad3ae50bebeac76a6cf982d1330c587279113595fc9 |
| `en-ru` | Helsinki-NLP/opus-mt-en-ru | Apache-2.0 | d15fa58c6bc3efd3629c1b6b86d9aa6d15d2751a4620aa4cdd7eed7b5cbe583b |
| `ru-en` | Helsinki-NLP/opus-mt-ru-en | Apache-2.0 | 535450eb5613f3cc912f9ca3e54cfef6c14d201b319c24a88faf776a65538b5d |
| `uk-en` | Helsinki-NLP/opus-mt-uk-en | Apache-2.0 | db67251736c28c6c703ce2ad11fbf2134f0d95b7ef053352d9e9df0f1b7ec633 |
| `en-uk` | Helsinki-NLP/opus-mt-en-uk | Apache-2.0 | 1fc8dc07ff5880253c0a51946f28ee4977efb84fa4e4586258994845b7384780 |
| `ar-en` | Helsinki-NLP/opus-mt-ar-en | Apache-2.0 | e937a8dd33fa352c278029f190b1d077deb8c637152ff4039c202b72683935fb |
| `en-ar` | Helsinki-NLP/opus-mt-en-ar | Apache-2.0 | d6d0270434540ec1e54c387206b27ea916831a8ccaff3ab04c7b63a03313b3cc |
| `ru-ar` | Helsinki-NLP/opus-mt-ru-ar | Apache-2.0 | adec67b562d9ee855ebc14f5dd9727e0fa20cfd2d681ed56fdc56841d8b04a92 |
| `ar-ru` | Helsinki-NLP/opus-mt-ar-ru | Apache-2.0 | cec23d60aff35d57f8fb758c49f93bd8e98c25e5df6a84244e1cdfe7459c1976 |
| `zh-en` | Helsinki-NLP/opus-mt-zh-en | Apache-2.0 | 9d8ceb91d103ef89400c9d9d62328b4858743cf8924878aee3b8afc594242ce0 |
| `en-zh` | Helsinki-NLP/opus-mt-en-zh | Apache-2.0 | 69a1d6ec829cee349360b3b677ac0aa99a7d88822d1a6578370029efffdca3f5 |
| `el-en` | Helsinki-NLP/opus-mt_tiny_ell-eng | Apache-2.0 | 15fe617eac2acb5d924f809bbcdf627dd31f75850928c1ae260a5934876d9837 |
| `en-el` | Helsinki-NLP/opus-mt_tiny_eng-ell | Apache-2.0 | 133584b8e1d178c731e56a0c6884a5e421e906aec7da316758a23f079f2c258b |
| `es-en` | Helsinki-NLP/opus-mt-es-en | Apache-2.0 | 586a4e69e0804459ac7c176a5dc76852652100d9af1ee0db796de719899a5deb |
| `en-es` | Helsinki-NLP/opus-mt-en-es | Apache-2.0 | befce0f620e8e63f83bbb7f0818eb51d541cba28057a7cc14b00466d85c4994c |
| `fr-en` | Helsinki-NLP/opus-mt-fr-en | Apache-2.0 | 6e3837f34b903802c3d0d670362b997cee6e87584a1108eb3fa89e4625e4424a |
| `en-fr` | Helsinki-NLP/opus-mt-en-fr | Apache-2.0 | cc1de10b49342ad2f33e06bc4474ddd6eaca278474903c4a8636ce15680d64de |
| `de-en` | Helsinki-NLP/opus-mt-de-en | Apache-2.0 | e743c3070f61f477cb62fe95ef2c9be2e77f3e488cb6b8030ff8a19e8295c87d |
| `en-de` | Helsinki-NLP/opus-mt-en-de | CC BY 4.0 | da068344b1b0c20e6d4a8f77f48e06646b90d679029006b18579e68977206bdd |

The Greek packs (`el-en`, `en-el`) come from the small models `opus-mt_tiny_ell-eng` and `opus-mt_tiny_eng-ell` (`model.safetensors`); the others from
`pytorch_model.bin` (`opus-mt-fr-en`: `model.safetensors`). Models with several target languages (`en-ar`, `ru-ar`: `>>ara<<`, `en-zh`: `>>cmn_Hans<<`)
get the target-language token in front of the text by the app.

The models were trained on OPUS data (https://opus.nlpl.eu). The Parley app runs them on the phone through ONNX Runtime (MIT);
no text leaves the phone.

If you use the models, please cite: J. Tiedemann and S. Thottingal, "OPUS-MT: Building open translation services for the World",
EAMT 2020.
