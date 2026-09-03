# CoDRBench release checklist

This checklist is for maintainers. A checked item should be backed by a
versioned artifact or review record.

## Dataset and paper

- [ ] Finish the complete 248-case review.
- [ ] Resolve or quarantine every rejected and borderline case.
- [ ] Complete human review of all rewrites and a sample of unchanged cases.
- [ ] Freeze the train/test split and stable case identifiers.
- [ ] Document the mapping between the paper's experimental subset and the
      repository corpus.
- [ ] Align repository terminology and counts with manuscript version 2.

## Quality and reproducibility

- [ ] Pass schema, language, template, duplicate, and cross-split checks.
- [ ] Pass the semantic quality gate and independent blind validation.
- [ ] Record model names, prompt versions, parameters, thresholds, and input
      hashes.
- [ ] Add a release manifest, audit summary, and SHA-256 checksums.
- [ ] Test the validation scripts from a clean environment.

## Safety and legal review

- [ ] Confirm that no secret, API key, private notebook, raw model output,
      personal data, or manuscript draft is tracked by Git.
- [ ] Complete ethics and limitations documentation.
- [ ] Select and add separate dataset and code licenses.
- [ ] Complete the final internal authorization to release.

## Publication

- [ ] Add `CITATION.cff`, changelog, dataset card, and contribution guidance.
- [ ] Create an immutable version tag and GitHub release.
- [ ] Verify the release checksums from a fresh download.
- [x] Make the GitHub repository public (documentation placeholder only; the
      dataset itself is not uploaded).
- [ ] Add the immutable repository/release URL to the revised paper and arXiv.
