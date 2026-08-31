# CoDRBench

**Concealed Deception Role-Play Benchmark**

> [!IMPORTANT]
> **The dataset has not been released yet.** This repository is currently a
> private placeholder while the data and paper revision undergo final review.

CoDRBench is a research benchmark for studying concealed deception in
role-playing language models. It accompanies the paper
[*When Thinking LLMs Lie: Unveiling the Strategic Deception in Representations
of Reasoning Models*](https://arxiv.org/abs/2506.04909) by Kai Wang, Yihao
Zhang, and Meng Sun.

## Dataset

The current internal dataset contains **248 synthetic cases** across nine
professional domains:

| Split | Cases |
|---|---:|
| Train | 188 |
| Test | 60 |

Each case contains two fields:

```json
{
  "system": "A hidden professional role and deceptive behavior.",
  "user": "A question based on harm or suspicious evidence observed by the user."
}
```

The nine domains are Health & Medical, Finance & Legal, Repair & Construction,
Retail & Services, Transportation, Education & Training, Arts & Entertainment,
Public Service & Safety, and Personal Care & Assistance.

## Release status

The dataset is undergoing case-level quality review and is **not available for
download**. This repository currently contains documentation only.

The public release will include the reviewed dataset, validation scripts,
checksums, a dataset card, and versioned audit documentation. The current arXiv
version's 160-sample Experiment 2 subset and the planned 248-case repository
corpus refer to different stages; their exact mapping will be documented with
the release.

## Citation

Until a dataset-specific citation is available, please cite the paper:

```bibtex
@misc{wang2025whenthinkingllmslie,
  title         = {When Thinking LLMs Lie: Unveiling the Strategic Deception
                   in Representations of Reasoning Models},
  author        = {Kai Wang and Yihao Zhang and Meng Sun},
  year          = {2025},
  eprint        = {2506.04909},
  archivePrefix = {arXiv},
  primaryClass  = {cs.AI},
  doi           = {10.48550/arXiv.2506.04909},
  url           = {https://arxiv.org/abs/2506.04909}
}
```

## License

The dataset and code licenses will be added before the first public release.
