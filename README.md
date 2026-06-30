# Research Report Orchestrator

A reusable Codex Skill for producing source-backed Chinese industry and company research reports through a staged, auditable, multi-role workflow.

This project is positioned as an AI-assisted investment research workflow and industry research productivity tool. It is not a one-shot report generator. The core idea is to keep the final report concise and readable while preserving the research process through evidence books, risk registers, claim-source maps, and quality-control gates.

## What It Solves

Chinese industry and company research reports usually fail when AI is used as a single drafting step:

- sources are summarized but not hardened
- key numbers lose their data scope
- conclusions are stronger than the evidence
- risks become generic boilerplate
- the final report is readable but hard to audit

Research Report Orchestrator addresses this by separating the research workflow into roles and files. The final report is the polished output; the supporting artifacts preserve the reasoning trail.

## Differentiation

- **Multi-role research workflow**: master agent, researcher, evidence manager, analyst, risk reviewer, logic reviewer, editor, QC, final rewriter, and sell-side polisher.
- **Evidence book**: each important claim or data point can be linked to source IDs, scope, reasoning, limitations, conflicts, and confidence.
- **Claim-source map**: the final report can ship with an audit companion that maps material claims back to evidence.
- **Risk and counterargument register**: risks are tied to thesis failure conditions, trigger signals, likely impact, and monitoring indicators.
- **Optional source library and vector index**: large source sets can be organized for retrieval without making RAG a mandatory dependency.
- **Sell-side-style final rewrite**: the report is reorganized around industry or company logic, not source-reading order.

## Use Cases

- Chinese industry research reports
- Chinese company research reports
- Secondary-market investment research support
- Sell-side-style report drafts
- Internship or portfolio projects showing AI-assisted research workflow design
- Converting public sources into structured research output
- Auditing and rewriting existing research drafts

The default language is Chinese. The default final artifact is an editable Markdown or Word report, with PPT/PDF conversion as a later step if needed.

## Workflow

```text
Master Agent
→ Researcher
→ Evidence Manager
→ Analyst
→ Risk & Counterargument Reviewer
→ Logic Reviewer
→ Editor
→ Quality Controller
→ Final Report Rewriter
→ Sell-side Polisher
```

The final deliverable should read like a complete industry or company research report, not a research memo, evidence audit, workflow log, or literature review.

## Output Structure

For a serious research project, the workflow can create or reuse:

```text
AGENTS.md
tasks/current-task.md
sources/
outputs/01-research.md
outputs/02-evidence-book.md
outputs/03-analysis.md
outputs/04-risk-register.md
outputs/05-logic-review.md
outputs/06-edited-draft.md
outputs/07-quality-check.md
final/report.md
final/claim-source-map.md
final/report.docx
```

The key design choice is to separate the report from the audit trail:

- `final/report.md`: concise, publishable report
- `outputs/02-evidence-book.md`: fuller evidence and reasoning ledger
- `outputs/04-risk-register.md`: risk, counterargument, and failure-condition register
- `final/claim-source-map.md`: final claim-to-source audit table

## Optional Source Library

For larger projects, source materials can be organized as:

```text
sources/
├── raw/
├── processed/
└── source-index.csv
```

If the source set is large, a vector retrieval layer can be added:

```text
vectors/
├── chunks.jsonl
└── index/
```

Vector retrieval is treated as an optional source-finding aid. It does not replace source hierarchy, citation review, or logic checking.

## Quality Control

The QC gate scores work out of 100:

- accuracy: 30
- evidence completeness: 25
- logic: 20
- readability: 15
- fit-to-brief: 10

Below 85 is not publishable. The quality controller can pass or return targeted rework instructions, but should not secretly repair earlier-role defects.

## Repository Structure

```text
research-report-orchestrator/
├── AGENTS.md
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── evidence-and-risk.md
│   ├── role-prompts.md
│   ├── sell-side-polish.md
│   └── workflow-files.md
└── templates/
    ├── claim-source-map.template.md
    ├── current-task.template.md
    ├── evidence-book.template.md
    ├── final-report.template.md
    └── risk-register.template.md
```

## Installation

Copy or clone this folder into your Codex skills directory:

```bash
~/.codex/skills/research-report-orchestrator
```

Then invoke it in Codex with:

```text
Use $research-report-orchestrator to create a complete Chinese industry research report.
```

## Example Prompts

```text
Use $research-report-orchestrator to help me produce a Chinese industry research report on XX industry, with an evidence book and claim-source map.
```

```text
Use $research-report-orchestrator to convert these public sources into a complete company research report, with logic review, risk register, QC, and sell-side-style polishing.
```

```text
Use $research-report-orchestrator to organize this project as a master-agent workflow with separate researcher, evidence manager, analyst, risk reviewer, editor, and QC outputs.
```

## Compliance Boundary

Use public, authorized, and citeable materials. Do not use this project to process confidential internship materials, client information, unpublished financials, inside information, or anything that may violate NDA, compliance, or professional ethics.

The project is intended to demonstrate research workflow design and quality-control thinking. It should not be represented as regulated investment advice or as a replacement for professional analyst judgment.
