# CoDRBench v1.0.0

This directory contains the Experiment 2 (Open-Role Deception) corpus.

| File | Cases |
|---|---:|
| `train.json` | 188 |
| `test.json` | 60 |

Both files are JSON arrays. Every item contains exactly two English string
fields:

- `system`: the hidden professional role and concealed deceptive behavior;
- `user`: a question based on harm experienced by the user.

The files do not contain model responses.

## License

The dataset is licensed under the [Creative Commons Attribution 4.0
International license (CC BY 4.0)](../../LICENSE).
