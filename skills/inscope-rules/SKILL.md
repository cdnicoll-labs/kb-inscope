---
name: inscope-rules
description: InScope's boundaries for the InScope knowledge base (kb-inscope). Apply before drafting or saving anything to kb-inscope, with any kb skill, and when checking a draft for InScope.
---

# InScope rules

These add to the rules in `kb-save`. Check every draft for `kb-inscope` against them before showing it. If a draft breaks one, remove the part that breaks it and say what was removed.

## Never save

- **Client data of any kind.** No supplier lists, spend figures, supplier contacts, or anything taken from a client's or prospect's systems. Describe logic and decisions; never the data they run on.
- **Health or patient information,** even in passing.
- **Commercial terms.** No pricing, contract or amendment terms, grant applications, or how revenue is split between the people on the team.
- **Vendors, keys, and code in product documents.** No vendor, database or model names, credentials, or code and file paths in an assessment, concept or overview. A `system` document may name technologies.

## Kinds

| Kind | For | Skill |
|---|---|---|
| `assessment` | one scoring assessment, as a contract | `inscope-assessment` |
| `decision` | one product decision and why | `kb-decision` |
| `concept` | a shared noun, such as the score shape | `kb-save` |
| `system` | the abstract architecture | `kb-save` |
| `overview` | what InScope is, for someone new | `kb-save` |
