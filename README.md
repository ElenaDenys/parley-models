# parley-models

Translation model packs for the Parley app (https://github.com/ElenaDenys/parley-models). Converted copies of the OPUS-MT models of the
Helsinki-NLP group (Apache License 2.0; English to German: CC BY 4.0), compressed for phones. See `NOTICE.md` for the credits and for what was changed.

Every release holds one zip per translation direction (`uk-ru`, `ru-uk`, `en-ru`, `ru-en`, `uk-en`, `en-uk`, `ar-en`, `en-ar`, `ru-ar`, `ar-ru`, `zh-en`, `en-zh`, `el-en`, `en-el`, `es-en`, `en-es`, `fr-en`, `en-fr`, `de-en`, `en-de`, each as `<id>.zip`) and
`manifest.json` (id, size and SHA-256 of every zip). The app reads `manifest.json` from
`https://github.com/ElenaDenys/parley-models/releases/latest/download/manifest.json` and downloads the packs the person asks for (Wi-Fi only),
checking the SHA-256 of every file.

A pack zip holds: `encoder.onnx`, `decoder.onnx` (ONNX Runtime 1.22, int8), `source.pieces`, `source.chars`, `target.pieces`, `charsmap.bin`,
`model.properties`. Made by `tools/mt/convert_marian.py` and `tools/mt/make_pack.py` of the Parley project.
