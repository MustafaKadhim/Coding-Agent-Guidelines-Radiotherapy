![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Claude Code](https://img.shields.io/badge/Claude%20Code-compatible-6B46C1)
![Codex](https://img.shields.io/badge/Codex-compatible-10A37F)
![Medical Imaging](https://img.shields.io/badge/Medical%20Imaging-DICOM%20%7C%20NIfTI-blue)
![Radiotherapy](https://img.shields.io/badge/Domain-Radiotherapy-red)
![PyTorch](https://img.shields.io/badge/PyTorch-workflows-EE4C2C)


# Coding-Agents-Skills-for-Radiotherapy-Research
This is my personal coding guidelines optimized for radiotherapy research and inspired by Andrej Karpathy's work on Claude Code skills. 
I provided reusable `AGENTS.md (for Codex)` and `CLAUDE.md (for Claude Code)` guidelines designed to help you code using radiothreapy expert agents. These guidelines will enable safer, smaller, and more scientifically reliable agents when working with research code involving DICOM, NIfTI, CT, CBCT, MRI, dose grids, segmentation masks, PyTorch, MONAI, and model evaluation.

> If you find this is useful for your research, consider starring or forking
> the repository so others in the medical physics and radiotherapy AI community
> can find and improve it.

Hope you like it!🌟
---
---

## Why I created this?

Coding agents such as Claude Code, Codex, Cursor, Copilot-style tools, and other
AI development assistants are becoming increasingly useful for research software.

But radiotherapy and medical imaging code has risks that generic coding
instructions often miss:

- patient-level data leakage
- incorrect DICOM/NIfTI geometry handling
- wrong interpolation for masks, labels, or dose grids
- unsafe logging of patient identifiers
- slice-level train/test splitting
- preprocessing mismatch between training and inference
- weak or misleading model evaluation
- unverified claims about clinical validity

This repository provides domain-specific instructions to help coding agents work
more carefully in this context.

---

## What is included

| File | Purpose |
| --- | --- |
| `AGENTS.md` | General coding-agent instructions, suitable for Codex and other agentic coding tools |
| `CLAUDE.md` | Claude Code project instructions / memory file |
| `LICENSE` | MIT license for reuse and adaptation |

---

## Quick start

Copy one or both instruction files into the root of your own project.

```text
your-project/
├── AGENTS.md
├── CLAUDE.md
└── README.md
```

Then open the project in your coding-agent environment, for example VSCode,
Claude Code, Codex, Cursor, or similar tools.

### For Codex-style agents

Use:

```text
AGENTS.md
```

### For Claude Code

Use:

```text
CLAUDE.md
```
---

## Main principles

The guidelines emphasize:

- think before coding
- ask when scientific assumptions are ambiguous
- make minimal, surgical changes
- avoid unnecessary refactoring
- verify changes with tests or smoke checks
- protect patient privacy
- avoid data leakage
- respect medical image geometry and metadata
- use appropriate interpolation for images, masks, labels, and dose
- evaluate models with suitable metrics and confidence intervals
- avoid unsupported clinical claims

---

## Medical imaging and radiotherapy focus

The instructions include specific guardrails for workflows involving:

- CT, CBCT, MRI, PET, SPECT, X-ray, and surface imaging
- DICOM and NIfTI I/O
- image orientation, spacing, origin, direction cosines, and affine matrices
- segmentation masks and label maps
- dose distributions and dose-grid alignment
- image registration and resampling
- patient-level train/validation/test splitting
- segmentation, synthesis, reconstruction, classification, and uncertainty tasks
- PyTorch, PyTorch Lightning, MONAI, TorchIO, SimpleITK, nibabel, and pydicom

---

## Example use case

You can add these files to a repository containing a deep learning pipeline for
radiotherapy image analysis.

For example, before asking a coding agent to modify preprocessing or training
code, the agent will already have instructions to consider:

- whether train/validation/test splits are patient-level
- whether DICOM metadata and NIfTI affines are preserved
- whether masks are resampled with nearest-neighbour interpolation
- whether dose grids are aligned correctly with the image grid
- whether W&B or logs contain patient-identifying information
- whether results are verified with an appropriate check

---

## Recommended workflow for coding agents

For non-trivial changes, the agent should follow this loop:

```text
1. Understand the goal
2. Inspect the relevant files
3. Define success criteria
4. Make the smallest correct change
5. Verify with relevant tests or smoke checks
6. Summarize what changed, what was verified, and what remains uncertain
```

This is especially important in research code, where small implementation
details can strongly affect experimental validity.

---

## Not clinical software

These instructions are intended for research software development.

They are not:

- clinical validation
- regulatory documentation
- a guarantee of clinical safety
- a substitute for expert review
- a replacement for institutional data protection procedures

Always validate research pipelines carefully before using results for scientific
or clinical decision-making.

---

## Contributing

Contributions are very welcome, especially from:

- medical physicists
- radiation oncology researchers
- medical imaging scientists
- AI/ML researchers in healthcare
- research software engineers
- PhD students and postdocs working with clinical imaging data

Useful contributions could include:

- additional guardrails for radiotherapy workflows
- better instructions for dose evaluation
- improved privacy/data protection guidance
- examples for specific coding agents
- project-specific templates
- suggestions for evaluation metrics
- better wording or structure

If you find this useful, please consider:

1. Starring the repository
2. Forking it for your own research group
3. Opening an issue with suggestions
4. Sharing it with colleagues working on medical imaging AI

---

## Acknowledgements

This repository was inspired by the growing use of coding agents in research
software development and by public discussions around agent instruction files,
including examples from the broader AI coding community.

The goal is to adapt these ideas to radiotherapy, medical physics, and medical
imaging research.

---

## License

This project is released under the MIT License.

You are free to use, modify, and adapt these instructions in your own research
repositories.
