# Workflow File Contracts

Use these files for serious research reports. Adapt names when the user already has a structure.

## Project Source Library

For larger projects, create or reuse:

```text
sources/raw/
sources/processed/
sources/source-index.csv
```

`source-index.csv` should include source ID, title, source name, source type, link/path, publication date, access date, geography, period, credibility, and notes. For many long materials, optionally add `vectors/chunks.jsonl` and `vectors/index/` as a retrieval aid.

## `tasks/current-task.md`

Include:

- report type: industry research or company research
- topic
- reader/use case
- final format
- research boundary: geography, period, sectors, exclusions
- required sources
- investment judgment requirement: yes/no
- evidence book requirement: yes/no
- claim-source map requirement: yes/no
- risk register requirement: yes/no
- open questions
- acceptance criteria

## `outputs/01-research.md`

Researcher output:

- fact list
- source name
- link/path
- publication date
- access date
- source type
- confidence
- conflicts
- gaps

Do not include final industry judgment.

## `outputs/02-evidence-book.md`

Evidence manager output:

- source index
- claim IDs
- claim text
- claim type: fact / data / inference / assumption / judgment / recommendation
- supporting evidence
- source IDs
- data scope: geography, period, unit, currency, definition
- reasoning: why the evidence supports the claim
- limitations
- conflicts
- confidence
- final report location or exclusion reason

Do not allow unsupported material claims to pass into the final report.

## `outputs/03-analysis.md`

Analyst output:

- central thesis
- industry/company logic
- evidence supporting each conclusion
- assumptions
- risks
- implications

Clearly separate facts, inference, assumptions, and recommendations.

## `outputs/04-risk-register.md`

Risk and counterargument reviewer output:

- risk type
- affected thesis or chapter
- risk description
- mechanism
- trigger signal
- likely impact
- evidence
- monitoring indicator
- severity
- probability
- report treatment
- counterarguments and what evidence would validate them

## `outputs/05-logic-review.md`

Logic reviewer output:

- unsupported conclusions
- causality mistakes
- inconsistent definitions or periods
- missing or weak evidence-book links
- missing links in argument chain
- severity: pass / revise / blocking
- targeted rework instructions

## `outputs/06-edited-draft.md`

Editor output:

- readable draft
- improved structure
- no new unsupported facts
- explicit unresolved issues

## `outputs/07-quality-check.md`

Quality controller output:

- score out of 100
- dimensions: accuracy 30, evidence 25, logic 20, readability 15, fit-to-brief 10
- pass/rework decision
- responsible role for each issue

## `final/report.md`

Final publishable report, not a process record. It should have:

- executive summary
- research scope and method
- central thesis
- evidence-backed analysis
- risks and limitations
- implications or conclusion
- sources

## `final/claim-source-map.md`

Final audit companion:

- claim ID
- final report location
- claim
- type
- evidence summary
- source IDs
- reasoning
- limitations
- confidence

Only include claims that appear in the final report. If the final report changes, update this map.
