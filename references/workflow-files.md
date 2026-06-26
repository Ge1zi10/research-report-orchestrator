# Workflow File Contracts

Use these files for serious research reports. Adapt names when the user already has a structure.

## `tasks/current-task.md`

Include:

- report type: industry research or company research
- topic
- reader/use case
- final format
- research boundary: geography, period, sectors, exclusions
- required sources
- investment judgment requirement: yes/no
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

## `outputs/02-analysis.md`

Analyst output:

- central thesis
- industry/company logic
- evidence supporting each conclusion
- assumptions
- counterarguments
- risks
- implications

Clearly separate facts, inference, assumptions, and recommendations.

## `outputs/03-logic-review.md`

Logic reviewer output:

- unsupported conclusions
- causality mistakes
- inconsistent definitions or periods
- missing links in argument chain
- severity: pass / revise / blocking
- targeted rework instructions

## `outputs/04-edited-draft.md`

Editor output:

- readable draft
- improved structure
- no new unsupported facts
- explicit unresolved issues

## `outputs/05-quality-check.md`

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
