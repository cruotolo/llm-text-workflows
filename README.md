# LLM Text Workflows

An open repository of reusable prompts, reproducible workflow records, and benchmark results for Large Language Models (LLMs) applied to text recognition, transcription, and encoding.

The goal of this project is to help researchers, librarians, archivists, and digital humanists discover, compare, and improve AI-assisted workflows for tasks such as:

- OCR correction
- Handwritten Text Recognition (HTR)
- Diplomatic transcription
- TEI encoding
- Named Entity Recognition (NER)
- Metadata extraction
- Translation
- Other text processing workflows

Unlike a traditional prompt library, this repository captures complete workflow information, making experiments reproducible and enabling meaningful comparisons across models.

---

# Project Goals

- Preserve prompts as reusable scholarly artifacts.
- Document how prompts perform on real source materials.
- Encourage reproducible AI-assisted workflows.
- Compare the performance of different models.
- Develop community best practices.
- Support long-term preservation and citation.

---

# Repository Structure

```
Prompt
    │
    ▼
Run
    │
    ├────────► Output
    │
    ▼
Evaluation

Corpus
    ▲
    │
Run
```

The repository is organized into five primary components.

## Prompts

A Prompt is a reusable instruction for an LLM.

Examples include:

- OCR correction
- TEI generation
- Metadata extraction
- Named entity recognition

A prompt should describe **how** to perform a task, not the result of a particular experiment.

Each prompt receives a permanent identifier.

Example:

```
TEI-001
```

---

## Corpora

A Corpus describes the source material used during testing.

Examples include:

- nineteenth-century printed books
- newspapers
- manuscripts
- archival documents

A corpus may contain:

- page images
- ground-truth transcriptions
- documentation
- metadata

Corpora are shared resources used for benchmarking.

---

## Runs

A Run records a single execution of a prompt.

A run documents:

- Prompt used
- Corpus used
- Model
- Model version
- Date
- Output produced

A run represents one reproducible experiment.

---

## Outputs

Outputs are the files generated during a run.

Examples include:

- TEI XML
- Plain text
- JSON
- CSV

Outputs are stored separately from run metadata.

---

## Evaluations

Evaluations describe the quality of a run.

Possible evaluation criteria include:

- transcription accuracy
- XML validity
- preservation of formatting
- manual editing required
- known failure modes

Evaluations may be qualitative, quantitative, or both.

---

## Benchmarks

Benchmarks compare multiple runs performed on the same corpus.

For example:

| Prompt | Model | Corpus | Result |
|---------|-------|--------|--------|
| TEI-001 | GPT-5.5 | Daisy Miller | 2 corrections |
| TEI-001 | Claude 3.5 Haiku | Daisy Miller | 6 corrections |
| TEI-001 | Gemini 2.5 Pro | Daisy Miller | 4 corrections |

Benchmarks allow the community to identify strengths and weaknesses across models and workflows.

---

# Data Model

The repository uses a simple relational model.

```
Prompt
   │
   ▼
Run
   │
   ├────────► Output
   │
   ▼
Evaluation

Corpus
```

A prompt may have many runs.

A corpus may be used by many runs.

Each run produces one or more outputs.

Each run may have one or more evaluations.

---

# Contributing

Community contributions are encouraged.

Typical contributions include:

- new prompts
- new corpora
- new workflow runs
- evaluations
- benchmark reports
- documentation improvements

See `CONTRIBUTING.md` for details.

---

# Design Principles

This repository emphasizes:

- openness
- reproducibility
- transparency
- interoperability
- long-term preservation

Prompt records should be reusable.

Run records should be reproducible.

Evaluation records should be evidence-based.

---

# Scope

This repository is intended for scholarly and cultural heritage applications, including:

- Digital Humanities
- Libraries
- Archives
- Museums
- Scholarly Editing
- Digital Editions
- Computational Linguistics

Although examples focus on text recognition and TEI, the repository is intentionally model-agnostic and workflow-agnostic.

---

# Citation

If you use prompts, workflows, or benchmark data from this repository in publications, please cite both the repository and the individual prompt or benchmark where appropriate.

---

# License

Unless otherwise noted, repository contents are released under the license specified in `LICENSE`.
