---
name: research-report-orchestrator
description: Use for Chinese industry research reports, company research reports, sell-side-style research drafts, internship/portfolio research deliverables, or any task that needs a reusable master-agent workflow with staged research, analysis, logic review, editing, quality control, and final Word/PPT/PDF-ready polishing.
---

# Research Report Orchestrator

Use this skill to run a repeatable “1 master agent + specialist roles” workflow for industry or company research reports. The default output language is Chinese; default deliverables are editable Markdown/Word first, then PPT/PDF if requested.

## Operating Principle

Act as the master agent unless the user explicitly asks to create separate conversations. Keep the process practical: do not force every role to run if the task is small, but preserve the role gates for serious deliverables.

The workflow is:

1. Confirm objective and reader
2. Create or update task files
3. Research and source hardening
4. Analysis
5. Logic review
6. Editing and humanization
7. Quality control
8. Final report rewrite
9. Sell-side-style polish
10. Deliver editable document and next-step options

## Default Workspace Structure

When starting a substantial report, create or reuse:

```text
AGENTS.md
tasks/current-task.md
outputs/01-research.md
outputs/02-analysis.md
outputs/03-logic-review.md
outputs/04-edited-draft.md
outputs/05-quality-check.md
final/report.md
final/report.docx
```

If the user already has a project structure, adapt to it instead of overwriting it. Keep each role’s output in its own file.

See `references/workflow-files.md` for file contracts.

## Role Gates

Use these role gates, either as separate Codex conversations or as internal stages:

- Master Agent: clarify scope, manage task files, decide rework, produce final handoff.
- Researcher: collect facts and sources; do not make final industry judgments.
- Analyst: explain industry/company logic using verified facts.
- Logic Reviewer: check whether conclusions follow from evidence.
- Editor: improve structure, language, readability, and human voice without inventing facts.
- Quality Controller: score and decide pass/rework; do not secretly repair prior-role defects.
- Final Report Rewriter: convert process outputs into a publishable report, not a process log.
- Sell-side Polisher: add report flavor: viewpoint-led headings, chapter takeaways, diagrams, concise frameworks, and “why” logic.

See `references/role-prompts.md` for reusable role prompts.

## Report Standards

For industry/company research:

- Lead with the central judgment, not the evidence trail.
- Organize by industry/company logic, not by “which documents were read.”
- Treat “complete research report” as the default final form. The final deliverable must not read like a research memo, evidence audit, workflow log, or literature review.
- Use “why” headings where possible: e.g. “为什么支付决定创新药真正赚钱？”
- Move caveats, source limitations, and “cannot extrapolate” warnings into methods, risks, or limitations unless they are material to the current argument.
- Use cases as case boxes that support the argument; do not let cases become the main structure.
- Add chapter takeaways for serious reports.
- Prefer clear diagrams, short comparison tables, and summary boxes over wide prose-heavy tables.
- Keep source traceability intact: no unsupported key facts in the final report.

See `references/sell-side-polish.md` for the final polishing checklist.

## Mandatory Final Rewrite Gate

Before creating the final Word/PPT/PDF, run a final rewrite gate:

- If the draft mainly says “what sources say,” rewrite it so it answers “why the industry/company is changing.”
- If the structure follows evidence collection order, reorganize it around industry/company development logic.
- If the same topic appears in multiple chapters, merge or move it.
- If a section explains “what X is,” rewrite it as “why X matters.”
- If caveats interrupt the main narrative, move them to risks, limitations, methods, or footnotes.
- If cases dominate the spine, convert them to case boxes.
- If there is no core framework chart, propose or create one before delivery.

## Rework Rules

Quality control below 85/100 means do not publish. Run targeted rework:

- Source gap → Researcher
- Unsupported conclusion → Analyst
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

## Minimal Trigger Examples

- “用这套模式帮我做 XX 行业研究报告。”
- “把这个行业研究做成主控 + 资料 + 分析 + 审核 + 编辑 + QC 流程。”
- “这份公司研究报告帮我按券商研报风格重写。”
- “我想把研究流程封装成可复用的多 Agent 工作流。”
