---
name: research-report-orchestrator
description: Use for Chinese industry research reports, company research reports, sell-side-style research drafts, investment research support, or portfolio-style AI research workflow projects that need a reusable master-agent process with staged source collection, evidence books, claim-source mapping, risk and counterargument review, analysis, logic review, editing, quality control, and final Word/PPT/PDF-ready polishing.
---

# Research Report Orchestrator

Use this skill to run a repeatable “1 master agent + specialist roles” workflow for industry or company research reports. The default output language is Chinese; default deliverables are editable Markdown/Word first, then PPT/PDF if requested.

This skill is designed for research workflow orchestration, not one-shot report generation. Keep the final report concise while preserving a traceable research base through evidence books, risk registers, and claim-source maps.

## Operating Principle

Act as the master agent unless the user explicitly asks to create separate conversations. Keep the process practical: do not force every role to run if the task is small, but preserve the role gates for serious deliverables.

The workflow is:

1. Confirm objective and reader
2. Create or update task files
3. Research and source hardening
4. Evidence book and source mapping
5. Analysis
6. Risk and counterargument review
7. Logic review
8. Editing and humanization
9. Quality control
10. Final report rewrite
11. Sell-side-style polish
12. Deliver editable document, audit companion, and next-step options

## Default Workspace Structure

When starting a substantial report, create or reuse:

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

If the user already has a project structure, adapt to it instead of overwriting it. Keep each role’s output in its own file.

See `references/workflow-files.md` for file contracts.

## Role Gates

Use these role gates, either as separate Codex conversations or as internal stages:

- Master Agent: clarify scope, manage task files, decide rework, produce final handoff.
- Researcher: collect facts and sources; do not make final industry judgments.
- Evidence Manager: create the evidence book, source index, and claim-source map; verify that key claims remain traceable.
- Analyst: explain industry/company logic using verified facts.
- Risk & Counterargument Reviewer: identify risks, skeptical views, failure conditions, and monitoring indicators.
- Logic Reviewer: check whether conclusions follow from evidence.
- Editor: improve structure, language, readability, and human voice without inventing facts.
- Quality Controller: score and decide pass/rework; do not secretly repair prior-role defects.
- Final Report Rewriter: convert process outputs into a publishable report, not a process log.
- Sell-side Polisher: add report flavor: viewpoint-led headings, chapter takeaways, diagrams, concise frameworks, and “why” logic.

See `references/role-prompts.md` for reusable role prompts. See `references/evidence-and-risk.md` when the task needs evidence books, risk registers, source libraries, claim-source maps, or optional vector retrieval.

## Report Standards

For industry/company research:

- Lead with the central judgment, not the evidence trail.
- Organize by industry/company logic, not by source-reading order.
- Treat “complete research report” as the default final form. The final deliverable must not read like a research memo, evidence audit, workflow log, or literature review.
- Use “why” headings where possible: e.g. “为什么渠道效率决定商用清洁机器人的盈利弹性？”
- Move caveats, source limitations, and “cannot extrapolate” warnings into methods, risks, or limitations unless they are material to the current argument.
- Use cases as case boxes that support the argument; do not let cases become the main structure.
- Add chapter takeaways for serious reports.
- Prefer clear diagrams, short comparison tables, and summary boxes over wide prose-heavy tables.
- Keep source traceability intact: no unsupported key facts in the final report.
- For serious reports, deliver an audit companion: `final/claim-source-map.md` plus an evidence book or risk register when useful.

See `references/sell-side-polish.md` for the final polishing checklist.

## Evidence and Risk Companions

For serious industry or company reports, separate the readable report from the research audit trail:

- `outputs/02-evidence-book.md`: full evidence ledger with claim IDs, source IDs, reasoning, limitations, conflicts, and confidence.
- `outputs/04-risk-register.md`: risks, counterarguments, failure conditions, trigger signals, and monitoring indicators.
- `final/claim-source-map.md`: concise audit table covering the material claims that appear in the final report.

Use `templates/` as starting points when creating these files. If there are many long PDFs, filings, policy documents, or web pages, optionally create a source library and vector index:

```text
sources/raw/
sources/processed/
sources/source-index.csv
vectors/chunks.jsonl
vectors/index/
```

Treat vector retrieval as an optional source-finding aid. It does not replace citation review, source hierarchy, or logic checking.

## Mandatory Final Rewrite Gate

Before creating the final Word/PPT/PDF, run a final rewrite gate:

- If the draft mainly says “what sources say,” rewrite it so it answers “why the industry/company is changing.”
- If the structure follows evidence collection order, reorganize it around industry/company development logic.
- If the same topic appears in multiple chapters, merge or move it.
- If a section explains “what X is,” rewrite it as “why X matters.”
- If caveats interrupt the main narrative, move them to risks, limitations, methods, or footnotes.
- If cases dominate the spine, convert them to case boxes.
- If there is no core framework chart, propose or create one before delivery.
- If material claims lack entries in the evidence book or claim-source map, update the audit companion before delivery.
- If the report lacks credible downside or counterargument discussion, run the Risk & Counterargument Reviewer gate before delivery.

## Rework Rules

Quality control below 85/100 means do not publish. Run targeted rework:

- Source gap → Researcher
- Missing source mapping or weak evidence traceability → Evidence Manager
- Unsupported conclusion → Analyst
- Missing downside, one-sided thesis, or unclear failure condition → Risk & Counterargument Reviewer
- Contradiction or causality problem → Logic Reviewer
- Robotic prose or poor readability → Editor / Humanize pass
- Report still reads like process notes → Final Report Rewriter / Sell-side Polisher

After two rework rounds, stop and present a human decision list.

## Deliverable Guidance

For Word deliverables, use the document tooling/skill when available and verify layout structurally. Avoid wide tables with long Chinese prose; convert them into diagrams, bullets, case boxes, or short tables.

For PPT deliverables, first finalize the report logic, then convert to a slide outline:

1. Core thesis
2. Industry context
3. Framework/chain map
4. Key drivers
5. Segment analysis
6. Cases
7. Risks
8. Conclusion / implications

## Compliance Boundary

Use public, authorized, and citeable materials. Do not process confidential internship materials, client information, unpublished financials, inside information, or anything that may violate NDA, compliance, or professional ethics. Do not present the output as regulated investment advice unless the user explicitly provides an appropriate authorized context and the report still keeps assumptions, sources, and limitations visible.

## Minimal Trigger Examples

- “用这套模式帮我做 XX 行业研究报告。”
- “把这个行业研究做成主控 + 资料 + 证据底稿 + 分析 + 风险 + 审核 + 编辑 + QC 流程。”
- “这份公司研究报告帮我按券商研报风格重写，并补充论点来源映射。”
- “我想把研究流程封装成可复用的多 Agent 投研工作流。”
