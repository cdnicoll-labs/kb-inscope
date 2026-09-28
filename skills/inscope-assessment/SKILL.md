---
name: inscope-assessment
description: Write or update an InScope assessment in the InScope knowledge base (kb-inscope), written as a contract so the assessment could be rebuilt from the page alone. Use when the user wants to document, define, design, or change how an InScope assessment works, what it takes in, what it produces, or how it is scored.
---

# InScope assessment

An assessment document is the contract for one scoring assessment: what goes in, what comes out, and the logic that is a product decision. It describes what InScope should do, not how today's code happens to do it. Anything true only of the current implementation goes under Known gaps.

Save to `kb-inscope` only. If `whoami` reports another client, stop and say so. Apply `inscope-rules` to the draft.

## Interview

Ask one question at a time. `search` for the assessment first; if a document exists, `get_document` it and work from it.

1. Which assessment, and what question does it answer for the enterprise, about whom?
2. Ownership: does the result belong to the supplier company itself (the same for every enterprise), or to one enterprise's relationship with that supplier? Why?
3. Inputs, one at a time: what the data means, unit or range, who supplies it (enterprise, supplier publications, interview, public reference data, InScope, or another assessment), whether it is required, and what happens when it is missing.
4. Outputs: each output's meaning and unit or range. Does it produce the shared score shape (normalized score, reasoning, confidence), a quantity, or both?
5. Scoring: the logic at the level a procurement lead could follow. Only choices someone made on purpose; not constants that fell out of one dataset or fallbacks.
6. What it serves: which initiatives it feeds (cost savings, decarbonization, Indigenous procurement). An assessment not serving the current initiative is `built-unused`, not wrong.
7. Known gaps: where the product today does not do what the contract says.
8. Sources: the calls, specs, or documents this comes from.

## Draft

- `kind`: `assessment`
- `slug`: the assessment name in kebab-case, for example `level-of-influence`
- Body sections, in order: **What it is**, **Ownership**, **Inputs** (table: Input, Meaning, Unit or range, Supplied by, Required, If missing), **Outputs** (table: Output, Meaning, Unit or range), **How it is scored**, **What it serves**, **Known gaps** (omit when none)
- `metadata`:
  ```json
  {
    "owner": "company | relationship",
    "status": "active | built-unused | proposed | archived",
    "inputs": ["..."],
    "outputs": ["..."],
    "serves": ["..."],
    "depends_on": ["<other assessment slugs>"]
  }
  ```
- No vendor, database, or model names, no references to code or file paths, and no client data (supplier lists, spend figures, contacts).

## Finish

Follow the `kb-save` skill from step 3 (check the draft) through step 8.
