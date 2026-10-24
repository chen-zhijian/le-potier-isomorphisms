# Le Potier isomorphisms for coherent sheaves on complex spaces

**Zhijian Chen, Zhuo Liu, and Chenghao Qing**

[Read the paper](papers/paper_v1.pdf) · [LaTeX source](papers/src/general-lepotier-isom.tex) · [Personal website](https://chen-zhijian.github.io/)

This repository contains the manuscript and LaTeX source for a weighted canonical Le Potier isomorphism for coherent sheaves on reduced irreducible complex spaces. The paper establishes higher-direct-image vanishing on the reduced main component of a projectivization, derives a symmetric-power formula under stronger positivity, and proves the classical unweighted differential-form isomorphism for locally free sheaves over arbitrary complex spaces, including nonreduced bases.

## Scope and limitations

- The weighted canonical theorem assumes a locally projective modification to a smooth space on which the torsion-free inverse image is locally free. Its metric extends as a singular Griffiths semipositive metric with determinant finite and positive almost everywhere, and the combined tautological metric must have plurisubharmonic local weights.
- This theorem concerns the **reduced main component** of the projectivization. The full symmetric-algebra projectivization may have vertical components or nilpotent structure and cannot be substituted without further argument. No normality or compactness of the base is assumed in the stated weighted theorem.
- The determinant-free symmetric-power formula requires strong Nakano semipositivity on the modification. Independence is asserted for choices admitting a common locally projective refinement with compatible pullbacks of the relevant line bundles and metrics.
- The unweighted differential-form theorem assumes a locally free sheaf of positive rank. It uses analytic Kähler differentials, without replacing them by reflexive differentials or a dualizing sheaf. Examples exhibit failures of comparison maps and higher-direct-image vanishing for general coherent sheaves.
- A weighted differential-form formula needs additional hypotheses. The manuscript gives a valid version when the ideal comes from the base, and a counterexample concerning Theorem 1.3(ii) in the specifically cited **arXiv:2405.07261v1**. That discussion does not contradict the canonical and symmetric-power formulas.

The manuscript states the precise hypotheses, conventions, comparison with Liu–Liu–Yang–Zhou, and examples. Its results should be read with those distinctions between canonical coefficients, differential forms, and the two projectivizations preserved.

## Repository layout

```text
.
├── README.md
├── LICENSE
├── papers/
│   ├── paper_v1.pdf
│   └── src/
│       └── general-lepotier-isom.tex
├── prompts_and_logs/
│   ├── system_prompt.txt
│   ├── conversation.json
│   └── cost_summary.md
├── verification/
│   ├── lean/
│   └── scripts/
│       └── build.ps1
└── .github/                  # Source/PDF pairing checks
```

## Build

Install a TeX distribution containing XeLaTeX and the standard AMS, Latin Modern, geometry, mathtools, microtype, enumitem, xcolor, and hyperref packages. From the repository root, run:

```powershell
powershell -NoProfile -File .\verification\scripts\build.ps1
```

The repository build script is configured for **XeLaTeX** and `papers/src/general-lepotier-isom.tex`. The bibliography is embedded in the source; no BibTeX database or external figures are required. The published PDF is [papers/paper_v1.pdf](papers/paper_v1.pdf).

## Provenance and verification

A selected export of 23 user-visible messages from four research and revision turns on October 24, 2026 is included in `prompts_and_logs/conversation.json`. It was recovered from the chat “Deduce classical isomorphisms.” The export preserves historical claims and corrections, with local paths and platform-supplied wrappers removed; it is not the complete development history. Original system prompts, exact model configuration, token usage, and costs remain unavailable. See [the provenance notes](prompts_and_logs/README.md) for coverage and exclusions.

No Lean formalization or other machine-checked proof is supplied. `verification/lean/` records that status. Compilation, reference checks, file checks, and PDF inspection are technical checks; they do not establish mathematical correctness. The mathematical arguments and cited inputs require scholarly review.

## Maintenance

The owner maintains the manuscript in its original local LaTeX file. Automatic syncing is configured to check for changes every 15 minutes while the owner's computer and synchronization service are available. A successful run publishes the packaged source, rebuilt `papers/paper_v1.pdf`, and `verification/build_manifest.json` together. Failed builds leave the last published manuscript in place. The PDF path stays stable, so the existing repository and [personal website](https://chen-zhijian.github.io/) links reach the updated manuscript.

When the manuscript changes, the maintenance agent reviews the title, author credits, summary, and scope statements in this README and on the website, and updates them where needed. Build and consistency checks do not establish mathematical correctness. Automatic syncing does not reconstruct or regenerate the historical AI conversation and usage records.

Other contributors can use the documented build procedure above: edit `papers/src/`, rebuild and inspect the PDF, run `python verification/scripts/verify.py`, and commit the source, PDF, and build manifest together. Coordinate manuscript revisions with the owner so the original source and repository remain consistent.

Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) and [NOTICE](NOTICE).
