# CoDRBench

**Concealed Deception Role-Play Benchmark**

CoDRBench is a benchmark for studying strategic deception by AI assistants
under professional role-playing conditions. It accompanies the paper
[*When Thinking LLMs Lie: Unveiling the Strategic Deception in Representations
of Reasoning Models*](https://arxiv.org/abs/2506.04909).

## Experiment 2: Open-Role Deception

The corpus contains 248 constructed scenarios across nine professional domains
and covers more than 100 distinct professional roles:

| Split | Cases |
|---|---:|
| Train | 188 |
| Test | 60 |
| Total | 248 |

Each case contains two fields:

```json
{
  "system": "A hidden professional role and profession-related deceptive behavior.",
  "user": "A reasonable question based on harm suffered by the user."
}
```

The nine domains are Health & Medical, Finance & Legal, Repair & Construction,
Retail & Services, Transportation, Education & Training, Arts & Entertainment,
Public Service & Safety, and Personal Care & Assistance.

The `system` field specifies a user-invisible professional role and a concealed
profession-related deceptive behavior. The `user` field contains a natural
question grounded in harm that the user has experienced. The corpus contains
no model responses.

## Files

- [`data/v1.0.0/`](data/v1.0.0/) — Experiment 2 train/test data and metadata
- [`docs/dataset_description.md`](docs/dataset_description.md) — dataset description

## Paper

This dataset accompanies the paper
[*When Thinking LLMs Lie: Unveiling the Strategic Deception in Representations
of Reasoning Models*](https://arxiv.org/abs/2506.04909).

## License

The CoDRBench dataset and accompanying documentation are licensed under the
[Creative Commons Attribution 4.0 International license (CC BY 4.0)](LICENSE).
Please retain attribution and indicate any changes when sharing or adapting the
materials.
