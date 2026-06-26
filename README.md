# Research Report Orchestrator

A reusable Codex skill for producing source-backed Chinese industry and company research reports through a staged, multi-role workflow.

This skill is designed for research tasks that need more than a one-shot draft: public-source research, evidence hardening, analysis, logic review, editing, quality control, final report rewriting, and sell-side-style polishing.

## What It Helps With

- Industry research reports
- Company research reports
- Internship or portfolio research deliverables
- Sell-side-style report drafts
- Source-backed research workflows
- Multi-agent / multi-role research coordination

The default output language is Chinese. The default final artifact is an editable report draft, usually Markdown or Word first, with PPT/PDF conversion as a later step if needed.

## Workflow

The skill follows a “master agent + specialist roles” structure:

1. Master Agent
2. Researcher
3. Analyst
4. Logic Reviewer
5. Editor
6. Quality Controller
7. Final Report Rewriter
8. Sell-side Polisher

The goal is not to create a process log. The final deliverable should read like a complete industry or company research report, not a research memo, evidence audit, or literature review.

## Key Principles

- Lead with the central judgment.
- Organize by industry or company logic, not source order.
- Use evidence, but do not let the evidence trail become the report structure.
- Use “why” headings where possible.
- Keep cases as supporting case boxes, not the main spine.
- Move caveats and source limitations into methods, risks, or limitations.
- Prefer clear diagrams, short tables, and chapter takeaways over dense prose-heavy tables.
- Do not invent facts, data, citations, institutions, people, or sources.

## Repository Structure

```text
research-report-orchestrator/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── role-prompts.md
    ├── sell-side-polish.md
    └── workflow-files.md
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
Use $research-report-orchestrator to help me produce a Chinese industry research report on XX industry.
```

```text
Use $research-report-orchestrator to convert these source materials into a complete company research report, with logic review, quality control, and sell-side-style polishing.
```

```text
Use $research-report-orchestrator to organize this project as a master-agent workflow with separate researcher, analyst, reviewer, editor, and QC outputs.
```

## Privacy Note

This repository contains only the reusable skill instructions and generic workflow templates. It should not contain private research materials, local file paths, personal documents, client information, or unpublished project content.

