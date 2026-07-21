# HCXAI Impact Assessment Tool — User Manual

**Version 1.0 · HCXAIResearch - Human Centered AI governance**
Aligned to `ISO/IEC 42001:2023` (Annex A.5) · structured on `ISO/IEC 42005:2025`

## Contents

1. [What this tool is](#1-what-this-tool-is)
2. [Getting started](#2-getting-started)
3. [The interface at a glance](#3-the-interface-at-a-glance)
4. [Stage-by-stage walkthrough](#4-stage-by-stage-walkthrough)
5. [The risk scoring model](#5-the-risk-scoring-model)
6. [Control mapping and your Statement of Applicability](#6-control-mapping-and-your-statement-of-applicability)
7. [Saving, versioning and re-loading assessments](#7-saving-versioning-and-re-loading-assessments)
8. [Export formats and when to use each](#8-export-formats-and-when-to-use-each)
9. [Standards mapping reference](#9-standards-mapping-reference)
10. [Recommended operating procedure](#10-recommended-operating-procedure)
11. [Troubleshooting](#11-troubleshooting)
12. [FAQ](#12-faq)

---

## 1. What this tool is

The HCXAI Impact Assessment Tool is a single-file HTML application for performing and documenting **AI system impact assessments** from the **deployer perspective** — that is, from the standpoint of an organization putting an AI system into operation, working from vendor documentation, contractual information, and its own operational context.

It implements:

- the impact assessment **controls** of `ISO/IEC 42001:2023` Annex A.5 (A.5.2 process, A.5.3 documentation, A.5.4 individuals/groups, A.5.5 society), and
- the assessment **structure** of `ISO/IEC 42005:2025` — the dedicated AI system impact assessment guidance standard (process clauses 5.1–5.12, documentation clauses 6.1–6.9, and Annexes A–C, E).

One assessment = one AI system in one context of use. Under ISO/IEC 42001, the same model deployed in a different context is a separate assessment trigger — treat it as one.

**What it is not:** a certification, a legal opinion, or a substitute for the licensed standards. It is a structured documentation instrument that makes your assessments consistent, citable, and audit-ready.

---

## 2. Getting started

**Requirements:** any modern browser (Chrome, Edge, Firefox, Safari). Internet access is needed only for fonts and the PDF export library; all assessment logic and data stay on your machine.

**Open it:** double-click `HCXAI_Impact_Assessment_Tool.html`, or host it on an intranet/SharePoint page. Nothing is installed and nothing is transmitted.

**Important — no auto-save:** the tool holds your work in browser memory only. Closing or refreshing the tab discards unsaved entries. Use **Save JSON snapshot** regularly (see Section 7). This is deliberate: it keeps the tool deployable anywhere and keeps your records in *your* controlled document store, not a browser cache.

---

## 3. The interface at a glance

| Element | What it does |
|---|---|
| **Header** | HCXAIResearch identity and the standards the assessment is aligned to |
| **Toolbar** | `New assessment` · `Load JSON` · `Save JSON snapshot` · `Export MD` · `Export PDF` · `Export report (HTML)` |
| **Stepper** | Eight numbered stages; sticky at the top; click any stage to jump — completed stages fill navy |
| **Standards spine** | The banner at the top of each stage citing the governing provisions in two rows: teal chips for `ISO/IEC 42001:2023`, steel-blue chips for `ISO/IEC 42005:2025` |
| **Cards** | The working area — form fields, tables, checklists |
| **Outcome gate** | The colour-coded banner showing the assessment decision derived from the risk register |

Fields marked `*` are the minimum expected for a defensible record. The tool does not block progress on empty fields — governance judgement stays with you — but empty required fields will show as "Not documented" in exports, which is itself information an auditor will read.

---

## 4. Stage-by-stage walkthrough

### Stage 1 — System profile
*Spine: 42001 Cl. 4.1, 4.2, A.9.4 · 42005 Cl. 5.4, 5.6, 6.2, 6.3*

Identify what is being assessed and why now.

- **AI system name / version / provider** — pin the exact system and release. If the vendor ships a material model update, that is a new version and potentially a new assessment.
- **Lifecycle stage** — where the system sits: design/procurement, pre-deployment, in operation, significant change, or decommissioning.
- **Assessment trigger** — the reason this assessment exists (new system, significant change, new use case, scheduled review, incident-driven). This operationalizes 42005 Cl. 5.4 (timing) and 42001's "planned and at defined intervals" expectation.
- **Business owner** — the accountable person, not the assessor. Accountability and assessment are different roles (42005 Cl. 5.6).

### Stage 2 — Purpose & context of use
*Spine: 42001 A.9.4, A.6.2.2, A.9.2 · 42005 Cl. 6.3, 6.6*

Document the intended purpose exactly as your organization deploys it, plus:

- **Context of use** — sector, geography, deployment environment, languages. This is 42005 Cl. 6.6 and the reason context changes re-trigger assessment.
- **Intended users and competence** — who operates it and what they need to know.
- **Declared limitations** — what the *provider* says the system must not be used for. Copy these from vendor documentation; they anchor your misuse analysis in Stage 5.

### Stage 3 — Impacts on individuals and groups
*Spine: 42001 A.5.4 · 42005 Cl. 6.7, 6.8, Annex C*

Control A.5.4 requires impacts on **individuals and groups** to be assessed in their own right, separately from society-level effects.

- **Affected individuals** — the people about whom, or for whom, the system produces outputs (applicants, employees, patients, customers).
- **Affected groups** — populations who may experience the system *differently*: protected characteristics, vulnerable groups, minority-language users. Naming groups explicitly is what makes disparate impact discoverable later.
- **Potential harms** — think across the 42005 Annex C taxonomy: rights, safety, economic, psychological, autonomy.
- **Transparency and redress** — can affected people know a machine was involved, contest an outcome, reach a human?

### Stage 4 — Societal impacts
*Spine: 42001 A.5.5 · 42005 Cl. 6.8, Annex C*

A deliberately separate stage because A.5.5 is a separate control. Consider environment, labour markets, information ecosystem, equity of access — and record **scale and reversibility**: a small, reversible societal effect and a large, irreversible one demand very different treatments.

### Stage 5 — Foreseeable misuse & failure
*Spine: 42001 A.5.4, A.6.2.4, A.6.2.6 · 42005 Cl. 6.8*

- **Reasonably foreseeable misuse** — not exotic attacks; the predictable ways real users will stretch the system beyond the declared limitations from Stage 2.
- **Failure modes** — what happens when output is wrong, and who absorbs the consequence.
- **Human oversight** — the measures actually in place (review steps, thresholds, kill-switches), not aspirations.

### Stage 6 — Risk register
*Spine: 42001 Cl. 6.1.2, 6.1.3, A.5.2 · 42005 Cl. 5.8, 5.9, Annex B*

Convert documented impacts from Stages 3–5 into discrete, scoreable risks. Each row: description, affected parties, likelihood (1–5), severity (1–5). Ratings compute live; the **outcome gate** updates as you type. See Section 5 for the model.

Good register discipline: one risk per row; write risks as *event → consequence* ("model under-scores applications from group X → unequal access to service"), not as topics ("bias").

### Stage 7 — Control mapping
*Spine: 42001 Annex A · 42005 Cl. 6.9, Annex A*

Select the ISO/IEC 42001 Annex A controls that treat the identified risks, grouped A.2–A.10. Selections appear in every export and feed your **Statement of Applicability** (see Section 6). This is 42005 Cl. 6.9 — measures to address harms and maximize benefits — expressed in 42001's control vocabulary.

### Stage 8 — Outcome & sign-off
*Spine: 42001 A.5.3, Cl. 9.1 · 42005 Cl. 5.10–5.12, Annex E*

- **Assessor / Reviewer / Approver** — the three roles of 42005's recording (5.10) and approval (5.11) clauses. For a *high* outcome, the approver should be your AI governance authority, not the project team.
- **Next review date** — operationalizes monitoring and review (5.12). Set it now; the exported record carries it.
- **Decision rationale and conditions** — the paragraph an auditor reads first. State *why* the outcome is acceptable and *under what conditions* (e.g., "proceed with controls, conditional on A.6.2.6 monitoring being live before go-live").

The summary card shows the whole assessment at a glance before export.

---

## 5. The risk scoring model

**Rating = Likelihood (1–5) × Severity (1–5)**

| Score | Band | Outcome |
|---|---|---|
| 1–6 | 🟢 Low | **Proceed** |
| 8–12 | 🟠 Medium | **Proceed with controls** |
| 15–25 | 🔴 High | **Escalate to governance authority** |

- The **assessment outcome** is derived from the *highest-rated* risk in the register — a single high risk gates the whole assessment, which mirrors how approval authority should work.
- Scales are anchored: likelihood from *Rare* to *Almost certain*; severity from *Negligible* to *Severe*. Calibrate these anchors to your organization's risk criteria (42001 Cl. 6.1.2 requires defined criteria) and document that calibration in your AIMS.
- Scoring is **inherent by default**: score the risk before treatment, then let Stage 7's control selections and Stage 8's conditions describe the treatment. If your methodology scores residual risk instead, keep it consistent across all assessments and say so in the decision rationale.

---

## 6. Control mapping and your Statement of Applicability

The Stage 7 checklist is the bridge between the assessment and your AI management system:

1. Each selected control asserts *"this control is applicable to this system and treats an identified risk."*
2. Aggregating selections across all assessments tells you which Annex A controls are live across your AI estate — this is raw material for the **SoA** required by 42001 Cl. 6.1.3.
3. Gaps are equally informative: a high-rated risk with *no* mapped control should be impossible to sign off without an explicit justification in the decision rationale.

The catalogue included is the deployer-relevant selection of Annex A. Verify wording against your licensed copy of the standard; the tool cites control numbers and titles only.

---

## 7. Saving, versioning and re-loading assessments

The tool deliberately has **no database**. Persistence is file-based:

| Action | Result |
|---|---|
| **Save JSON snapshot** | Downloads `HCXAI_ImpactAssessment_<System>_<date>.json` — the complete state, including your position in the wizard |
| **Load JSON** | Restores a snapshot exactly as saved |
| **New assessment** | Clears everything (with confirmation) |

**Recommended pattern:**

```
Draft   → snapshot → SharePoint /AI-Governance/Assessments/<System>/
Review  → load → amend → snapshot (new dated file)
Approve → snapshot + PDF export filed together = the approved record
Re-assess (per next-review date or trigger) → load latest → update → repeat
```

Your document library provides version history, permissions, and retention — the audit-trail functions a static HTML file cannot. Never edit a filed JSON in place; every change is a new dated snapshot. That discipline *is* your immutable trail.

---

## 8. Export formats and when to use each

| Format | Button | Best for | Notes |
|---|---|---|---|
| **JSON** | Save JSON snapshot | The system of record; re-loading; version history | The only format the tool can re-open |
| **PDF** | Export PDF | Register storage, audit evidence, email attachments | Generated in-browser via jsPDF; brand-styled; colour-coded ratings; paginated with footer |
| **Markdown** | Export MD | Wikis, repos, static sites, pipelines | YAML front matter (`title`, `standard`, `guidance`, `generated`, `outcome`), pipe tables, inline `code` provision spans, `---` footer |
| **HTML report** | Export report (HTML) | Board packs and anything presentation-grade | Standalone file with its own **Print / Save as PDF** button; browser-native Poppins/Inter typography |

Why two PDF paths? **Export PDF** is instant and byte-consistent — ideal for evidence. **HTML report → print** renders with full web fonts — ideal when the document will be *read by people who decide things*. Keep both.

All exports carry the dual-standard citations on every section header, in the form:
`42001: A.5.4 · 42005: Cl. 6.7, 6.8, Annex C`

---

## 9. Standards mapping reference

### Per-stage citations

| # | Stage | ISO/IEC 42001:2023 | ISO/IEC 42005:2025 |
|---|---|---|---|
| 1 | System profile | Cl. 4.1, 4.2, A.9.4 | Cl. 5.4, 5.6, 6.2, 6.3 |
| 2 | Purpose & context | A.9.4, A.6.2.2, A.9.2 | Cl. 6.3, 6.6 |
| 3 | Individuals & groups | A.5.4 | Cl. 6.7, 6.8, Annex C |
| 4 | Societal impacts | A.5.5 | Cl. 6.8, Annex C |
| 5 | Misuse & failure | A.5.4, A.6.2.4, A.6.2.6 | Cl. 6.8 |
| 6 | Risk register | Cl. 6.1.2, 6.1.3, A.5.2 | Cl. 5.8, 5.9, Annex B |
| 7 | Control mapping | Annex A (SoA: Cl. 6.1.3) | Cl. 6.9, Annex A |
| 8 | Outcome & sign-off | A.5.3, Cl. 9.1 | Cl. 5.10, 5.11, 5.12, Annex E |

### ISO/IEC 42005:2025 orientation

- **Clause 5 (5.1–5.12)** — the *process*: establishing, documenting, integrating, timing, scoping, responsibilities, thresholds, performing, analysing, recording, approval, monitoring
- **Clause 6 (6.1–6.9)** — the *record*: scope, system information, data, algorithms/models, deployment environment, interested parties, impacts, and measures
- **Annex A** — integrating 42005 assessments into a 42001 AIMS (avoids duplication)
- **Annex B** — relationship to ISO/IEC 23894 (AI risk management)
- **Annex C** — harms and benefits taxonomy (use it as a completeness check in Stages 3–5)
- **Annex E** — example assessment template (this tool is a working implementation of that idea)

Remember: 42001 is certifiable; 42005 is guidance. The tool's language — *aligned to 42001, structured on 42005* — is the defensible framing.

---

## 10. Recommended operating procedure

1. **Trigger** — new system, significant change, new context, scheduled date, or incident (Stage 1 captures which).
2. **Assess** — assessor completes Stages 1–7 with the business owner; use vendor documentation for Stage 2 and the Annex C taxonomy as a completeness check.
3. **Score & gate** — register review with the owner; the gate outcome determines the approval path.
4. **Approve** — low: owner sign-off; medium: owner + reviewer; high: governance authority. Record all three roles in Stage 8.
5. **File** — JSON snapshot + PDF into the controlled library, same folder, same date.
6. **Monitor** — diarize the next review date; any Stage 1 trigger event before that date brings the assessment forward.

---

## 11. Troubleshooting

| Symptom | Cause | Fix |
|---|---|---|
| Work lost after closing tab | No auto-save by design | Save JSON snapshots as you go |
| "PDF library not loaded" toast | cdnjs unreachable (offline/blocked) | Use **Export report (HTML)** and its print button, or retry online |
| Fonts look different | Google Fonts unreachable | Cosmetic only — system fonts substitute; exports still work |
| Loaded file rejected | Not a snapshot from this tool, or corrupted | Only load JSONs produced by **Save JSON snapshot**; re-export from a good copy |
| Print dialog doesn't open in an embedded/preview pane | `window.print()` is blocked in sandboxed iframes | By design the tool never calls it directly — download the HTML report and open it as a normal file; its print button will work |
| Rating shows "—" | Likelihood or severity not set | Both dropdowns must be selected for a score |

---

## 12. FAQ

**Does any data leave my machine?**
No. There is no backend, no analytics, no storage API use. Data exists in the open tab and in the files you export.

**Can several people work on one assessment?**
Not simultaneously. Pass the JSON snapshot between people, or screen-share. The sign-off fields record the roles regardless of who typed.

**Can I add or edit the Annex A control list or risk anchors?**
Yes — the file is plain HTML/JS. The control catalogue is a single `CONTROLS` array and the scales are `LIKELIHOOD`/`SEVERITY` arrays near the top of the script. Keep a changelog if you customize, so exported records remain interpretable.

**Is completing this tool enough for ISO/IEC 42001 conformity?**
No single artefact is. It produces the documented impact assessments that controls A.5.2–A.5.5 require, in a form an auditor can trace — the surrounding AIMS (policy, roles, risk criteria, monitoring) still has to exist.

**Why does one high risk gate the whole assessment?**
Because approval authority should escalate with worst-case exposure, not average exposure. If you disagree for a given system, override in the decision rationale — visibly.

---

*© HCXAIResearch — Human-at-centre AI governance. This manual accompanies the HCXAI Impact Assessment Tool v1.0. ISO/IEC clause references are provided for interoperability; consult the licensed standards for authoritative text.*
