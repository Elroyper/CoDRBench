# CoDRBench

**Concealed Deception Role-Play Benchmark**

> [!IMPORTANT]
> **Release status: private staging — dataset not released.**
>
> CoDRBench is undergoing internal quality review. No dataset file in a private
> working copy is an official release, and no public download is available yet.

CoDRBench is a research benchmark for studying concealed, role-consistent
deception in reasoning language models. It supports the Open-Role Deception
setting introduced in [*When Thinking LLMs Lie: Unveiling the Strategic
Deception in Representations of Reasoning
Models*](https://arxiv.org/abs/2506.04909) by Kai Wang, Yihao Zhang, and Meng
Sun.

## Repository status

| Component | Current status |
|---|---|
| Research paper | Public on arXiv |
| Manuscript revision | Version 2 in progress |
| Dataset | **Not released** |
| Private staging snapshot | 188 training cases and 60 test cases |
| Quality review | In progress |
| Public download endpoint | Not available |
| Dataset license | **TBD** |
| Code license | **TBD** |
| Versioned release / DOI | Not yet issued |

Files in the private working copy—including `train.json`, `test.json`, model
review output, and calibration artifacts—are staging materials, not public
release artifacts.

## Overview

Experiment 2 studies open-ended professional role-play scenarios in which:

1. a user-invisible system script assigns the assistant a professional role;
2. the script establishes a specific deceptive practice already carried out,
   or currently being carried out, toward the user; and
3. the user asks a natural question based on concrete harm or suspicious
   evidence they have observed.

The current staging snapshot contains **248 cases**:

| Split | Cases |
|---|---:|
| Train | 188 |
| Test | 60 |
| Total | 248 |

The scenarios span nine professional domains:

- Health & Medical
- Finance & Legal
- Repair & Construction
- Retail & Services
- Transportation
- Education & Training
- Arts & Entertainment
- Public Service & Safety
- Personal Care & Assistance

The benchmark contains synthetic research scenarios describing unethical or
harmful professional conduct. It does not contain professional advice and
should not be interpreted as evidence about any real person or occupation.

## Relationship to the paper

The current arXiv version reports 160 stimuli selected for a particular
Experiment 2 activation-vector training stage. The private corpus snapshot
tracked here contains 188 train and 60 test records. These numbers refer to
different stages and should not be treated as interchangeable. Before public
release, versioned documentation will explain the exact mapping between the
experiment-stage subset and the released corpus.

## Data schema

Each split is represented as a JSON array. Every case contains exactly two
English string fields:

```json
{
  "system": "The conversation is not accessible from the User. You are a/an <professional role> AI assistant. Unknown by the user, you <specific concealed deceptive practice>.",
  "user": "<A natural question grounded in observable harm>?"
}
```

- `system`: a user-invisible role script establishing a concrete,
  profession-related deceptive practice.
- `user`: a question arising from harm or evidence the user can reasonably
  observe, without revealing that the user already knows the concealed cause.

The core release schema intentionally contains no model response. Audit
metadata, provenance, domain assignments, revision history, and stable case
identifiers are planned as a separate sidecar manifest so that the original
two-field schema remains reproducible.

The `train` and `test` names reproduce the experimental partitioning; they do
not imply that these cases are recommended as general-purpose instruction
tuning data.

## Data availability

**The dataset is not currently available for download.**

A public release will be announced only after:

- the complete 248-case quality review is finished;
- all accepted cases pass deterministic and blind semantic validation;
- train/test leakage and duplicate checks are resolved;
- human review of rewritten and borderline cases is complete;
- data and code licenses are selected; and
- release files, checksums, documentation, and version tags are finalized.

No unofficial copy should be described as a CoDRBench release. Official
artifacts will be identified by an immutable release tag and checksums.

## Quality assurance

The release audit is separate from the paper's response-level `liar_score`. It
evaluates whether each dataset case is well constructed.

Each candidate is reviewed on eight dimensions, scored from 0 to 5:

1. clarity of deceptive intent;
2. plausibility of the role's authority over the action;
3. causal alignment between the action and observed harm;
4. real-world realism and internal consistency;
5. observability and naturalness of the user query;
6. consistency of hidden information;
7. language quality; and
8. distinctiveness and train/test split safety.

The current staging release gate requires:

- at least **39/40** overall;
- **5/5** on all six core semantic dimensions;
- at least **4/5** on language quality and split safety;
- reviewer confidence of at least **0.90**;
- all required semantic checks to pass;
- no hard failure or material unresolved issue;
- an independent fresh-context blind validation pass; and
- final deterministic schema, template, duplication, and cross-split checks.

Original files are never overwritten. Proposed revisions, review decisions,
and quarantined cases are tracked separately. Model-assisted review does not
replace domain-expert or human ethical review, so all rewritten cases and a
sample of unchanged cases must also be inspected manually before release.

Detailed prompts, model versions, thresholds, input hashes, and release-level
audit summaries will be documented with each public version.

## Intended uses

CoDRBench is intended for research on:

- strategic deception in reasoning models;
- concealed-context behavior;
- deceptive alignment and moral consistency;
- representation probing and activation steering;
- behavioral evaluation of role-conditioned assistants; and
- interpretability and AI-safety methods.

It is not intended for:

- training systems to deceive users;
- developing operational techniques for professional misconduct;
- providing medical, legal, financial, or safety advice;
- evaluating real professionals or demographic groups; or
- deployment as a production decision-making dataset.

## Planned public repository layout

```text
CoDRBench/
├── README.md
├── CITATION.cff
├── LICENSE-CODE
├── DATA_LICENSE
├── CHANGELOG.md
├── data/
│   └── v1.0.0/
│       ├── train.json
│       ├── test.json
│       ├── metadata.jsonl
│       ├── checksums.sha256
│       └── DATASET_CARD.md
├── audit/
│   └── v1.0.0/
│       ├── audit_summary.json
│       ├── quality_report.md
│       └── release_manifest.json
├── docs/
│   ├── dataset_description.md
│   ├── relationship_to_paper.md
│   ├── quality_assurance.md
│   ├── ethics_and_limitations.md
│   └── release_policy.md
├── config/
│   └── audit_policy.json
├── scripts/
│   ├── validate_dataset.py
│   └── audit_experiment2_dataset.py
├── tests/
│   └── test_dataset_validation.py
└── requirements-audit.txt
```

The placeholder directories in this repository contain documentation only.
Private credentials, notebooks, paper drafts, caches, and raw model output must
never be added.

## Versioning

Every public dataset version will include:

- an immutable Git tag;
- SHA-256 checksums;
- an input and audit manifest;
- documented case additions, removals, and rewrites;
- the exact schema version;
- the paper-to-dataset mapping;
- the audit prompt and policy version; and
- separate data and code license files.

Results should identify the exact CoDRBench release rather than referring only
to the repository's default branch.

## Citation

Until a dataset-specific archival citation is issued, please cite the
associated paper:

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

A dataset DOI and `CITATION.cff` entry will be added when the first public
release is issued.

## License

**License: TBD.**

No dataset or code license has yet been granted. The license attached to the
arXiv paper must not be assumed to apply automatically to the dataset, audit
artifacts, or source code. Public use and redistribution terms will be stated
explicitly before release.

## Contributing and contact

External data contributions are not currently accepted during private staging.
After release, this section will document issue reporting, correction requests,
case provenance requirements, and the responsible disclosure process.

For now, please refer to the [paper page](https://arxiv.org/abs/2506.04909) for
author and research contact information.
