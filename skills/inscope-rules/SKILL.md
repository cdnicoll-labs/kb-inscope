---
name: inscope-rules
description: InScope's boundaries and quality bar for the InScope knowledge base (kb-inscope). Apply before drafting or saving anything to kb-inscope, with any kb skill, and when checking a draft for InScope.
---

# InScope rules

These add to the rules in `kb-save`. Check every draft for `kb-inscope` against them before showing it. If a draft breaks one, remove the part that breaks it and say what was removed.

## Never save

- **Client data of any kind.** No supplier lists, spend figures, supplier contacts, or anything taken from a client's or prospect's systems. Describe logic and decisions; never the data they run on.
- **Health or patient information,** even in passing.
- **Commercial terms.** No pricing, contract or amendment terms, grant applications, or how revenue is split between the people on the team.
- **Vendors, keys, and code in product documents.** No vendor, database or model names, credentials, or code and file paths in an assessment, concept or overview. A `system` document may name technologies.

## Quality

InScope's knowledge base is read by people deciding what to build and sell. A short, sourced document beats a long, plausible one. Before showing any draft:

- **No source, no save.** Every factual claim traces to a call, a document, or a decision in `sources`. A claim with no source is cut, or the draft stays a local note.
- **Length by kind.** `overview`: one screen. `decision`: about 15 lines. `concept`: about 20 lines. `assessment`: its own sections and nothing else. Over the limit means something is repeated or unsourced; cut that, do not compress it.
- **Cut filler.** Delete restated points, introductions and summaries of the document itself, and any sentence that would be true of any product ("drives value", "holistic", "leverages", "robust"). Write the specific thing or nothing.
- **Update, do not duplicate.** `search` first. If a document on the subject exists, change it and show only what changed.
- **Approved documents change only with a yes.** If a document's `metadata.review` says approved, show the diff and get an explicit yes for that change, not a general one.

## Kinds

| Kind | For | Skill |
|---|---|---|
| `assessment` | one scoring assessment, as a contract | `inscope-assessment` |
| `decision` | one product decision and why | `kb-decision` |
| `concept` | a shared noun, such as the score shape | `kb-save` |
| `system` | the abstract architecture | `kb-save` |
| `overview` | what InScope is, for someone new | `kb-save` |
