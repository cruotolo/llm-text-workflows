# Prompt Record Specification

A Prompt Record describes a reusable Large Language Model (LLM) prompt for a specific text processing task.

Prompt Records are intended to document methods rather than experiments. They describe *how* to perform a task, independent of any particular document, model execution, or evaluation.

A Prompt Record should remain stable over time. Individual applications of a prompt are documented separately as Run Records.

---

# Purpose

Prompt Records exist to:

- document reusable LLM prompts
- promote reproducible workflows
- encourage sharing of best practices
- support comparison across models
- provide stable identifiers for citation

---

# Relationship to Other Records

```
Prompt
    │
    ├──────────────┐
    ▼              ▼
Run 1          Run 2
    │              │
    ▼              ▼
Output        Output
    │              │
    ▼              ▼
Evaluation   Evaluation
```

A single Prompt Record may be referenced by many Run Records.

Prompt Records do **not** contain:

- execution dates
- corpus-specific information
- generated output
- evaluation results

These belong in Run Records.

---

# Required Fields

Every Prompt Record must include the following metadata.

| Field | Description |
|--------|-------------|
| id | Unique identifier |
| title | Brief descriptive title |
| version | Prompt version |
| contributors | Author(s) or maintainer(s) |
| task | Primary task(s) performed |
| input_format | Expected input |
| output_format | Expected output |
| model | Model used during initial validation |
| license | Reuse license |
| status | Draft, Validated, Deprecated, etc. |

---

# Recommended Sections

## Purpose

Describe what the prompt is intended to accomplish.

Example:

> Produce a diplomatic TEI transcription of printed nineteenth-century texts while preserving original spelling and typography.

---

## Prompt

Include the complete prompt exactly as used.

Use Markdown code fences.

Example:

```
Please transcribe these pages...
```

---

## Success Criteria

Describe what constitutes a successful result.

Examples include:

- Preserve line breaks
- Preserve italics
- Generate valid TEI
- Preserve page numbering
- Do not modernize spelling

---

## Suitable For

Describe the kinds of materials for which the prompt is appropriate.

Examples:

- Printed books
- Newspapers
- Typescripts
- Early modern texts

---

## Not Suitable For

Document known limitations.

Examples:

- Handwritten manuscripts
- Musical notation
- Tables
- Complex page layouts

---

## Notes

Optional implementation notes or recommendations.

Examples:

- Best results obtained with high-resolution images.
- XML should be validated after generation.
- Requires page filenames to be known in advance.

---

# Metadata Example

```yaml
---
id: TEI-001

title: Printed Text to TEI XML

version: 1.0

contributors:
  - Jane Smith

task:
  - Transcription
  - TEI Encoding

input_format:
  - Page images

output_format:
  - TEI XML

model:
  provider: Anthropic
  name: claude-3-5-haiku
  version: claude-3-5-haiku-20241022

license: CC BY 4.0

status: Validated
---
```

---

# Versioning

Prompt Records should be versioned whenever the prompt text changes in a way that may affect output.

Minor edits:

- spelling
- formatting
- metadata corrections

may increment the minor version.

Substantive prompt revisions should increment the major version.

---

# Identifiers

Prompt identifiers should remain stable.

Suggested format:

```
OCR-001
HTR-003
TEI-014
NER-008
```

Identifiers should never be reused.

---

# Citation

Prompt Records are intended to be citable scholarly objects.

When publishing work based on a Prompt Record, cite both:

- the Prompt Record identifier
- the associated Run Record(s)

---

# Design Principles

Prompt Records should be:

- reusable
- concise
- self-contained
- model-agnostic whenever possible
- understandable without additional context

A reader should be able to understand and reuse the prompt without referring to a specific experiment.
