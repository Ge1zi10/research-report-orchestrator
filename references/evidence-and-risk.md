# Evidence and Risk Workflow

Use this reference when the report needs auditability beyond the condensed final narrative.

## Why This Exists

The final report should be concise and judgment-led. It should not carry every source note, data caveat, and reasoning step in the main body. Serious research projects therefore need supporting artifacts:

- `outputs/02-evidence-book.md`: evidence base and reasoning ledger
- `outputs/04-risk-register.md`: risk, counterargument, and failure-condition register
- `final/claim-source-map.md`: final claim-to-source map for audit and review

These files make the workflow more useful for investment research because the final report can stay readable while every important fact, data point, and inference remains traceable.

## Source Library

For larger projects, create a project-level source library:

```text
sources/
├── raw/
├── processed/
└── source-index.csv
```

`source-index.csv` should include:

```text
source_id,title,source_name,source_type,link_or_path,publication_date,access_date,geography,period,credibility,notes
```

Use source IDs consistently across research notes, evidence book, risk register, and final claim-source map.

## Optional Vector Index

Treat vectorization as an optional retrieval enhancement, not as a required workflow gate.

Use it when there are many long PDFs, annual reports, policy documents, broker reports, or web pages. The recommended structure is:

```text
vectors/
├── chunks.jsonl
└── index/
```

Each chunk should preserve:

- `chunk_id`
- `source_id`
- source title
- source type
- publication date
- page / section / URL anchor when available
- extracted text
- embedding metadata if used

The vector index helps retrieve relevant evidence during drafting and checking. It does not replace source reading, citation review, or human judgment.

## Evidence Book Rules

Create one evidence entry for each important claim, data point, or analytical bridge. Include:

- claim ID
- claim text
- claim type: fact, data, inference, assumption, judgment, recommendation
- supporting evidence
- source IDs
- source reliability
- data scope: geography, period, unit, currency, statistical definition
- reasoning: why the evidence supports the claim
- limitations
- conflicts
- confidence: high, medium, low
- final report location or exclusion reason

Do not let unsupported claims enter the final report. If a claim is useful but not sufficiently supported, mark it as pending or exclude it.

## Claim-Source Map Rules

The final claim-source map is a condensed audit table for the published report. It should only include claims that appear in `final/report.md`.

Recommended columns:

```markdown
| Claim ID | Final Report Location | Claim | Type | Evidence Summary | Source IDs | Reasoning | Limitations | Confidence |
|---|---|---|---|---|---|---|---|---|
```

Every material number, causal claim, market judgment, and recommendation-like statement should appear in the map.

## Risk Register Rules

Create risk entries that explain how the central thesis could fail. Cover at least:

- policy and regulation
- demand
- supply and capacity
- technology route
- competition
- cost and pricing
- financing and capital expenditure
- overseas expansion
- data quality and definition risk
- conclusion extrapolation risk

Each risk should include:

- risk description
- affected thesis or chapter
- mechanism
- trigger signal
- likely impact
- evidence
- monitoring indicator
- mitigation or report treatment
- severity
- probability

## Counterargument Rules

For each central thesis, list at least one serious counterargument:

- What would a skeptical analyst say?
- What evidence would support the skeptical view?
- What evidence weakens the skeptical view?
- What data should be monitored next?

Counterarguments should improve the report, not paralyze it. Move unresolved but material issues to risks, limitations, or follow-up research.

## Final Integration

Use supporting artifacts this way:

- `final/report.md`: concise, readable, judgment-led report
- `final/claim-source-map.md`: audit companion for every important claim in the final report
- `outputs/02-evidence-book.md`: fuller evidence and reasoning ledger
- `outputs/04-risk-register.md`: risk and counterargument basis for the risk section

If the final report changes materially, update `final/claim-source-map.md` before delivery.
