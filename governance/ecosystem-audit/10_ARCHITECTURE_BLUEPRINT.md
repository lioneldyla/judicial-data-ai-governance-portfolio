# 10 — Final Architecture Blueprint

> The target end-state of the GitHub ecosystem after the mission is
> complete. This document is the single canonical description that any
> future AI coding agent should read alongside `README.md` and
> `02_CLASSIFICATION_MATRIX.md` to continue the work without prior
> conversation context.

---

## Design principles (from the mission brief, re-anchored)

1. **One repository = one mission.**
2. **Research and software are separated** — the Portfolio holds no production code.
3. **Documentation is not duplicated** — one source of truth per topic.
4. **Git history is preserved** wherever possible; migrations use `git subtree` / `git filter-repo`, never re-uploads.
5. **Archive before delete** — every archive has a README explaining the decision.
6. **Every architectural decision is documented** — this file, and per-repo `AGENTS.md` files.
7. **AI-friendly** — every repo self-describes so an agent can continue work cold.
8. **Long-term maintainability** — kebab-case, `main` branch, ORCID-linked CITATION.cff, Zenodo DOIs.

---

## Target-state topology

Fifteen or so active repositories, grouped by category. The Le Wagon Archive
is one repository (post-consolidation), not 87.

```
Core Research (1)
└── judicial-data-ai-governance-portfolio     ← DAG root

Frameworks (1)
└── jdgf-toolkit                              (renamed from jdgf-framework)

Platforms (1)
└── living-digital-governance-platform

Software Products (3)
├── cs-greffe-os                              (renamed from cs-greffe-os-v2, after v1 archived)
├── cs-greffe-os-cloud
└── judicial-statistics

Artificial Intelligence (1)
└── judicial-ai-agents                        (renamed from data-agents)

Demonstrations (1)
└── monitor-the-reactor

Profile (1)
└── lioneldyla

Archives (3)
├── personal-archive
├── le-wagon-archive                          (new — consolidation of 87 exercises + taxifare-website)
└── legacy-projects                           (new — desktop-tutorial, skills-introduction-to-github, blank-app-1)

Sandbox (1)
└── playground                                (renamed from Playground)

Retired / Absorbed
├── jdgf-framework           → renamed to jdgf-toolkit
├── JDGF-LAB-FRAMEWORK       → renamed to jdgf-lab OR archived (open question 1)
├── cs-greffe-os (v1)        → archived after v2 becomes canonical
├── cs-greffe-os-v2          → renamed to cs-greffe-os
├── data-agents              → renamed to judicial-ai-agents
├── working-papers           → merged into Portfolio; source archived
├── personal-branding        → merged into personal-archive or profile; source archived (open question 6)
├── Playground               → renamed to playground
├── Leken.ci                 → depends on user decision (open question 4)
├── blank-app-1              → merged into playground or deleted
├── ~87 data-* Le Wagon      → consolidated into le-wagon-archive
├── taxifare-website         → included in le-wagon-archive
├── desktop-tutorial         → deleted (zero unique value)
└── skills-introduction-to-github → archived under legacy-projects
```

---

## Repository responsibility charter

Every active repo answers these five questions in its `AGENTS.md`.

| # | Question | Where it lives |
|---|---|---|
| 1 | What is this repository's single mission? | Header of `AGENTS.md` |
| 2 | What is *in scope* and *out of scope*? | Section 2 |
| 3 | What other repos does it depend on / feed into? | Section 3 (mirrors `03_DEPENDENCY_MAP.md`) |
| 4 | Who owns it? What is the license? | Section 4 |
| 5 | What are the next 3 milestones? | Section 5 (mirrors `PROJECT_STATUS.md`) |

---

## Per-repository single-mission statements

Extract-ready for each repo's future `AGENTS.md`:

| Repo | Single-mission statement |
|---|---|
| `judicial-data-ai-governance-portfolio` | Central research portfolio for the Data Governance for Intelligent Justice Systems programme. Holds only research artefacts. |
| `jdgf-toolkit` | Software toolkit implementing the Judicial Data Governance Framework — maturity models, assessment scripts, indicator calculators. |
| `jdgf-lab` (if kept) | Internal R&D lab for advanced JDGF experiments (RAG, multi-agent) that are not yet stable enough for the toolkit. |
| `living-digital-governance-platform` | Public governance framework and (eventually) deployed application supporting digital-transformation governance in African public institutions. |
| `judicial-statistics` | Data pipelines, notebooks, and BI methodology for the Judicial Statistics Yearbooks of the Ministry of Justice, Côte d'Ivoire. |
| `cs-greffe-os` | Open-source court registry operating system for African judiciaries — records, workflows, integration with court services. |
| `cs-greffe-os-cloud` | E-learning companion for CS GREFFE OS — training judiciary staff to operate the registry OS. |
| `judicial-ai-agents` | Multi-agent AI toolkit assisting judicial data governance research — data ingestion, RAG, synthesis, drafting, evaluation. |
| `monitor-the-reactor` | Industrial anomaly-detection ML pipeline — capstone demonstration piece (Le Wagon 2149). |
| `lioneldyla` | GitHub profile page. Public identity of the researcher. |
| `personal-archive` | Private digital archive — long-term memory of documents, notes, and reference materials. |
| `le-wagon-archive` | Read-only consolidation of the Le Wagon Data Science bootcamp exercises (Batch 2149). Preserved for personal history and citation. |
| `legacy-projects` | Read-only holder for pre-programme experiments and GitHub tutorial residue. |
| `playground` | Public sandbox for one-off experiments and template scaffolds. |

---

## What "done" looks like

The mission's success criteria, restated as observable end-state:

- [ ] Every active repository has exactly one mission (14–16 repos total, down from 110).
- [ ] `judicial-data-ai-governance-portfolio` contains no production software; only research artefacts.
- [ ] Every software repository is independent of the Portfolio (no code lives in both).
- [ ] No two repositories host the same documentation on the same subject.
- [ ] No two repositories host the same production code.
- [ ] Every active repo has: `README.md`, `AGENTS.md`, `PROJECT_STATUS.md`, `ROADMAP.md`, `ARCHITECTURE.md`, `CHANGELOG.md`, `CITATION.cff`, `LICENSE`.
- [ ] Every archived repo has the archival-README banner.
- [ ] Zenodo DOI is issued for the Portfolio, WP01, and JDGF Toolkit v1.0.
- [ ] The Portfolio's `README.md` contains an *Ecosystem* section linking to every sibling repo.
- [ ] Any future AI coding agent can pick up the ecosystem cold using only:
  - the Portfolio's `README.md`,
  - `governance/ecosystem-audit/README.md`,
  - this blueprint,
  - each repo's own `AGENTS.md`.

---

## Open questions requiring user decision

These block Phase 3 execution. Recommendations follow each question.

### Q1 — JDGF canonicality

Which repository is the canonical JDGF Toolkit?

- (a) `jdgf-framework` — older, no open issues, mission-aligned description.
- (b) `JDGF-LAB-FRAMEWORK` — younger, has 4 open issues, RAG/multi-agent scope.

**Recommendation:** (a) is the canonical `jdgf-toolkit`. Rename (b) to `jdgf-lab` and keep as R&D sandbox — or fold its RAG/multi-agent work into `judicial-ai-agents` and archive.

### Q2 — CS GREFFE OS canonicality

Which repository is the canonical `cs-greffe-os`?

- (a) `cs-greffe-os` (private, older, no description) — v1.
- (b) `cs-greffe-os-v2` (public, newer) — v2.

**Recommendation:** (b) becomes canonical `cs-greffe-os` after (a) is archived as `cs-greffe-os-v1`. Keep `cs-greffe-os-cloud` distinct.

### Q3 — `working-papers` standalone repo

Is the standalone `working-papers` repository still needed, given that the Portfolio hosts `working_papers/`?

**Recommendation:** No. Verify no unique content (Phase 1), then merge into Portfolio via `git subtree` and archive the source with a redirect README.

### Q4 — `Leken.ci`

What is `Leken.ci`? A domain project? A website? A joke? A dormant idea?

**Recommendation:** User to clarify. Default action if no answer within Phase-1 window: rename to `leken-ci` and archive under `legacy-projects` with a placeholder note.

### Q5 — Le Wagon archival strategy

Three choices:

- (a) GitHub `archived: true` flag on all 87 repos (cheap, leaves clutter).
- (b) Consolidate into `le-wagon-archive` monorepo (one-time cost, tidy end-state). **Recommended.**
- (c) Delete after Zenodo capture (permanent, cheapest end-state, no history).

**Recommendation:** (b). Preserves history, cleans the account.

### Q6 — `personal-branding` vs `lioneldyla` profile

Does the account want a separate `personal-branding` workspace alongside the profile repo?

**Recommendation:** Either (i) make `personal-branding` private and keep as a strategy workspace, or (ii) fold its content into `personal-archive/branding/` and archive the source. Not-recommended: leaving both public with overlapping content.

### Q7 — `judicial-ai-agents` naming

The proposed rename disambiguates from Le Wagon `data-*` repos. Two candidates:

- (a) `judicial-ai-agents` — thematic, aligned with the programme.
- (b) `data-agents-toolkit` — preserves the current name with a suffix.

**Recommendation:** (a). Thematic naming is more discoverable and more honest about the scope.

---

## Governance of this blueprint

- **Owner:** DJORO Yoboukoua Lionel Arnaud.
- **Review cadence:** at every major architectural decision.
- **Change log:** every substantive edit gets a bullet in the audit
  README's *Change log* section.
- **Storage:** this file lives at
  `governance/ecosystem-audit/10_ARCHITECTURE_BLUEPRINT.md` in the
  Portfolio. Never duplicated.

---

## After user approval

The next session should:

1. Update this document to reflect user decisions on Q1–Q7.
2. Execute Phase 1 (verification): add each active programme repo to session
   scope, clone, run the pre-migration checklist from
   `05_MIGRATION_PLAN.md`, and file per-repo verification notes under
   `governance/ecosystem-audit/verification/`.
3. Only then proceed to Phase 2 (metadata standardization) and Phase 3
   (documentation standardization).

Every subsequent phase is opened by re-reading this blueprint and closes by
updating this blueprint if any decision changed.
