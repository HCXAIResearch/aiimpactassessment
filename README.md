# AI Impact Assessment Tool (ISO42001 | ISO42005)

**Self-contained HTML tool for conducting AI system impact assessments aligned to ISO/IEC 42001:2023 (Annex A.5) and structured on ISO/IEC 42005:2025 - with risk register, Annex A control mapping, and branded PDF/Markdown/HTML exports. No backend, no build step.**

Built by [HCXAIResearch](https://hcxairesearch.org)

---

## Why this exists

Most AI impact assessment tooling assumes you built the model. This tool takes the **deployer perspective**: it captures what a deploying organization can realistically observe, document, and evidence — vendor-declared limitations, context of use, affected parties, oversight measures — rather than internal development details you'll never have.

It is a single HTML file. Email it, drop it on SharePoint, open it from a file share. No installation, no IT ticket, no data leaving the browser.

## Features

- **Eight-stage guided wizard** — system profile, purpose & context, impacts on individuals & groups, societal impacts, foreseeable misuse & failure, risk register, control mapping, outcome & sign-off
- **Dual-standard citations** — every stage shows a "standards spine" citing the governing ISO/IEC 42001 clauses/controls *and* the corresponding ISO/IEC 42005:2025 clauses (Cl. 5–6) and annexes
- **Live risk scoring** — likelihood × severity matrix with colour-coded ratings and an auto-derived outcome gate: *proceed / proceed with controls / escalate*
- **Annex A control mapping** — full deployer-relevant ISO/IEC 42001 control catalogue (A.2–A.10) as a checklist, feeding your Statement of Applicability
- **Four export formats**
  - `JSON` — versioned snapshots for storage and re-loading (your audit trail)
  - `PDF` — brand-styled, paginated report via jsPDF (instant, consistent)
  - `Markdown` — YAML front matter, pipe tables, inline provision codes (wiki/repo ready)
  - `HTML` — standalone print-ready report with its own print button (best typography for board packs)
- **No persistence by design** — nothing is stored in the browser; state lives in memory and in the JSON files you export

## Quick start

1. Download `HCXAI_Impact_Assessment_Tool.html`
2. Open it in any modern browser (Chrome, Edge, Firefox, Safari)
3. Work through the eight stages — the stepper lets you move freely
4. **Save JSON snapshot** early and often; each export is a dated version
5. Export your report in PDF, Markdown, or HTML when done

> An internet connection is only needed for fonts (Google Fonts) and the PDF library (cdnjs). Everything else, including all assessment logic, runs locally. If the PDF library is unreachable, the tool degrades gracefully and points you to the HTML report path.

## Standards alignment

| Layer | Standard | Role |
|---|---|---|
| Requirements | `ISO/IEC 42001:2023` | Certifiable AIMS requirements — Annex A.5 (impact assessment controls), Cl. 6.1 (risk), Cl. 9 (evaluation) |
| Guidance | `ISO/IEC 42005:2025` | Impact assessment process (Cl. 5.1–5.12) and documentation structure (Cl. 6.1–6.9); Annexes A–C, E |

Note: ISO/IEC 42005 is **guidance, not a certifiable standard**. This tool structures assessments on 42005 while anchoring auditable claims to 42001 — the exports phrase it exactly that way.

## Versioning workflow (no backend, on purpose)

```
fill in assessment → Save JSON snapshot → store in controlled library (e.g. SharePoint)
                                        ↘ re-load JSON later → update → new snapshot
```

Each JSON export is stamped with an ISO timestamp and named
`HCXAI_ImpactAssessment_<SystemName>_<YYYY-MM-DD>.json`. Your document library's
version history and permissions provide the access control and audit trail.

## Repository contents

| File | Purpose |
|---|---|
| `HCXAI_Impact_Assessment_Tool.html` | The tool — single file, everything included |
| `README.md` | This file |
| `MANUAL.md` | Full user guide: stage-by-stage walkthrough, scoring model, standards mapping, troubleshooting |

## Limitations (read before relying on it)

- Single-user, client-side only: no concurrent editing, no real sign-off workflow, no automated reminders — use your document library and calendar for those
- The Annex A catalogue is the deployer-relevant selection; verify against your licensed copy of the standard
- This tool supports, but does not constitute, conformity with ISO/IEC 42001 — assessments are only as good as the entries and the governance around them

## License & attribution

© HCXAIResearch.org Brand assets (logomark, wordmark, palette) are proprietary.
ISO/IEC standard titles and clause numbers are referenced for interoperability;
the standards themselves are available from [iso.org](https://www.iso.org).

---

*HCXAIResearch — Human-at-centre AI governance.*
