# Research Themes

> Permanent themes organizing every output of the *Judicial Data & AI
> Governance Lab*. Themes are stable across years; questions and outputs
> come and go, but every output belongs to one primary theme.

| Field | Value |
|---|---|
| Version | 1.0 |
| Date | 2026-07-07 |
| Number of themes | 8 |

---

## How themes are used

- **One primary theme per output.** Every Working Paper, framework,
  dataset, software project, and case study is tagged with exactly one
  primary theme. Secondary themes are permitted but should be sparse.
- **Themes do not overlap on definition.** Two themes may share vocabulary,
  but each has a distinct centre of gravity.
- **Themes are indexing keys.** GitHub topics, Zenodo keywords, ORCID
  work descriptions, LinkedIn posts, and search-engine metadata should
  align with these themes.
- **Themes are stable.** Adding a theme requires a substantive review;
  removing a theme requires migration of all outputs tagged with it.

---

## T1 — Judicial Data Governance

**Definition.** Institutional, legal, and technical arrangements
governing the lifecycle of data produced, held, and used by judicial
institutions — from acquisition through publication or archiving.

**Scope.** Data quality, metadata, interoperability, stewardship,
lifecycle management, FAIR principles applied to judicial data.

**Primary outputs:** WP01, WP03, JDGF, DS01 (Judicial Statistics
Dataset).

**Excludes.** Judicial *decisions* as a category (that's Case Law
Analytics — not currently in scope). AI governance (T3).

---

## T2 — Digital Justice

**Definition.** Digital transformation of judicial institutions — court
administration, e-justice, registry modernisation, legal tech — with
attention to institutional change, capacity, and citizen outcomes.

**Scope.** e-Justice platforms, court digitisation, e-registry, case
management systems, digital access to justice.

**Primary outputs:** WP04, CS GREFFE OS, CS03, CS05.

**Excludes.** Governance of the *data* those systems produce (T1). AI
components (T3).

---

## T3 — Responsible Artificial Intelligence

**Definition.** Design, deployment, and oversight of AI systems in ways
that preserve human dignity, human rights, and institutional accountability.

**Scope.** AI ethics; transparency; explainability; human oversight; bias
detection and mitigation; algorithmic auditing; safeguards specific to
judicial contexts.

**Primary outputs:** WP02, WP04, JA02, JA03, Data Agents (as an AI
system this Lab itself operates and studies).

**Excludes.** Broader AI *policy* (that's T4). Non-judicial AI applications.

---

## T4 — AI Governance

**Definition.** Regulatory, legal, and policy frameworks — international,
regional, national, institutional — that govern the adoption and use of
AI systems in the public sector, with an emphasis on judicial contexts.

**Scope.** EU AI Act; UNESCO AI Ethics Recommendation; AU Data Policy
Framework; OHADA developments; national AI strategies; procurement
policy; oversight arrangements.

**Primary outputs:** WP02, JA02, Policy Briefs, regulatory-mapping
datasets.

**Excludes.** The *technology* of AI itself (T3). Judicial data
lifecycle (T1).

---

## T5 — Judicial Analytics

**Definition.** Application of quantitative and computational methods to
judicial data for descriptive, diagnostic, or predictive purposes,
including judicial statistics, performance measurement, and analytical
reporting.

**Scope.** Judicial statistics production; performance indicators;
composite indices (e.g., SPJEJ); data pipelines; dashboards; comparative
analytics.

**Primary outputs:** SPJEJ, DS01, CS01, CS04, WP03.

**Excludes.** *Governance* of the underlying data (T1). Predictive tools
in adjudication (T3 — Responsible AI).

---

## T6 — Public Sector Data Governance

**Definition.** Broader public-sector data governance frameworks, digital
public infrastructure, and open data policy — the context within which
judicial data governance operates.

**Scope.** Government open data; whole-of-government data governance;
data-sharing arrangements between institutions; public-sector data
ethics; national statistical systems.

**Primary outputs:** Comparative studies; policy briefs; teaching
material.

**Excludes.** Judicial-specific analyses (T1). AI systems in other
sectors (T3 or T4).

---

## T7 — Intelligent Justice Systems

**Definition.** The programme's synthesizing concept — justice systems
that combine responsible data governance, digital infrastructure, and
accountable AI to deliver justice in ways that are trustworthy, human-
centred, and evidence-based.

**Scope.** Synthesis across T1–T4; long-term visions of judicial
institutions; conceptual frameworks; the doctoral thesis.

**Primary outputs:** WP01 (as the foundational paper of the programme);
doctoral thesis; book manuscript.

**Excludes.** Narrow single-theme outputs — this theme is by definition
integrative.

---

## T8 — Digital Public Infrastructure

**Definition.** Foundational digital systems — identity, payment,
data-exchange platforms, interoperability layers — on top of which
sector-specific applications (including judicial) are built.

**Scope.** ID systems; interoperability layers; data-exchange
platforms; national digital-transformation strategies as they relate to
justice.

**Primary outputs:** WP04; CS05; policy briefs; software
interoperability specifications.

**Excludes.** Sector-specific implementations (T2 covers the judicial
sector).

---

## Theme × Track matrix

Themes are indexing labels. Tracks (from
[`RESEARCH_QUESTIONS.md`](RESEARCH_QUESTIONS.md)) are research
programmes. Each track maps to one primary theme.

| Track (question set) | Primary theme | Secondary themes |
|---|---|---|
| Track 1 — Judicial Data Governance | T1 | T5, T7 |
| Track 2 — AI in Justice Systems | T3 | T4, T7 |
| Track 3 — Judicial Statistics and Open Data | T5 | T1, T6 |
| Track 4 — Digital Transformation Governance | T2 | T4, T6, T8 |
| Track 5 — Framework validation | T1 | T5, T7 |

## Theme × Pillar matrix

Pillars (from [`RESEARCH_ARCHITECTURE.md`](RESEARCH_ARCHITECTURE.md)) are
the three programme horizons.

| Theme | Pillar I (Data) | Pillar II (Digital) | Pillar III (AI) |
|---|:---:|:---:|:---:|
| T1 Judicial Data Governance | ● | ○ | ○ |
| T2 Digital Justice | ○ | ● | ○ |
| T3 Responsible AI | ○ | ○ | ● |
| T4 AI Governance | ○ | ○ | ● |
| T5 Judicial Analytics | ● | ○ | ○ |
| T6 Public Sector Data Governance | ● | ○ | ○ |
| T7 Intelligent Justice Systems | ● | ● | ● |
| T8 Digital Public Infrastructure | ○ | ● | ○ |

Legend: ● primary · ○ contributing

---

## Output-to-theme index

| Output | Primary theme | Secondary themes |
|---|---|---|
| WP01 | T7 Intelligent Justice Systems | T1, T3 |
| WP02 (planned) | T4 AI Governance | T3, T7 |
| WP03 (planned) | T1 Judicial Data Governance | T5, T7 |
| WP04 (planned) | T2 Digital Justice | T4, T8 |
| JDGF | T1 Judicial Data Governance | T5, T7 |
| SPJEJ (planned) | T5 Judicial Analytics | T1 |
| CS GREFFE OS (planned) | T2 Digital Justice | T8 |
| Data Agents (planned) | T3 Responsible AI | (research infrastructure) |
| CS01 (SPJEJ) | T5 Judicial Analytics | T1 |
| CS02 (SIS-MJDH) | T1 Judicial Data Governance | T2 |
| CS03 (CS GREFFE OS) | T2 Digital Justice | T8 |
| CS04 (Judicial Statistics) | T5 Judicial Analytics | T1, T6 |
| CS05 (Court Digital Transformation) | T2 Digital Justice | T4, T8 |

---

*Review annually and after any substantive addition to the output
register. If any output cannot be classified under a primary theme,
either the theme catalogue is incomplete or the output is off-programme;
resolve before publication.*
