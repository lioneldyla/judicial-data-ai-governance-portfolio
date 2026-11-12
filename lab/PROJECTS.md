# Projects

> Active and planned projects of the *Judicial Data & AI Governance Lab*.
> Each project has: an objective, a scientific contribution, current
> status, and its cross-links to publications, software, and datasets.

| Field | Value |
|---|---|
| Version | 1.0 |
| Date | 2026-07-07 |
| Review | On material status change or per doctoral milestone review |

---

## P01 — WP01 (Data Governance as Foundational Infrastructure)

| Field | Value |
|---|---|
| Type | Publication project (working paper) |
| Primary theme | T7 Intelligent Justice Systems |
| Research questions | RQ1.1, RQ1.2, RQ1.3 |
| Status | Publication package landed; manuscript body in preparation |
| Target milestone | Manuscript v1.0 by Q4 2026 |

**Objectives.**

- Articulate a conceptual framework for judicial data governance in
  African justice systems.
- Provide the empirical and theoretical grounding for the JDGF.
- Establish the programme's foundational publication.

**Scientific contribution.**

- Original conceptualization of *judicial data* as a distinct category
  of public data.
- Institutional-analysis framing of the governance conditions for
  intelligent justice systems in Africa.
- Argument that data governance is foundational to AI readiness, not
  ancillary.

**Cross-links.**

- Publication: [`../working_papers/WP01/`](../working_papers/WP01/)
- Framework: [`../frameworks/JDGF/`](../frameworks/JDGF/) (WP01 §4 grounds JDGF)
- Case studies: CS01, CS02, CS04
- Datasets: DS01 (planned)
- Software: none directly; JDGF Toolkit derives from WP01 concepts

---

## P02 — JDGF (Judicial Data Governance Framework)

| Field | Value |
|---|---|
| Type | Methodological framework project |
| Primary theme | T1 Judicial Data Governance |
| Research questions | RQ1.5, RQ5.1, RQ5.3 |
| Status | Conceptual v1.0 (see [`../frameworks/JDGF/`](../frameworks/JDGF/)); full articulation planned |
| Target milestone | JDGF v1.0 (methodology chapter) by Q3 2026; v2.0 (validation study) 2027 |

**Objectives.**

- Design, validate, and disseminate a comprehensive governance framework
  for judicial data systems.
- Support judicial institutions with an actionable maturity and
  assessment model.

**Scientific contribution.**

- Eight-domain framework (Governance, Data, Technology, People,
  Processes, Ethics, Performance, Innovation) grounded in institutional
  theory and FAIR principles.
- Maturity model calibrated for resource-constrained institutions.
- Iterative validation via case studies (CS02 as primary case).

**Cross-links.**

- Framework: [`../frameworks/JDGF/`](../frameworks/JDGF/)
- Publications: WP01 (grounding), WP03 (full articulation), JA01
- Software: JDGF Toolkit (planned, separate repository)
- Case studies: CS02 (SIS-MJDH — validation site)

---

## P03 — SPJEJ (Statistical Performance Index for Justice Efficiency)

| Field | Value |
|---|---|
| Type | Framework + software project |
| Primary theme | T5 Judicial Analytics |
| Research questions | RQ3.1, RQ5.3 |
| Status | Planned |
| Target milestone | Methodology + pilot data collection by Q4 2026 |

**Objectives.**

- Design a composite statistical index measuring judicial performance in
  African court systems.
- Pilot the index on Côte d'Ivoire data (2019 & 2023 yearbooks).
- Publish the technical note and the underlying data pipeline.

**Scientific contribution.**

- Original composite index calibrated for African judicial statistics
  practice.
- Methodology paper documenting index construction, weighting choices,
  and sensitivity analysis.
- Open reference implementation.

**Cross-links.**

- Case study: CS01 (SPJEJ pilot)
- Publications: WP03 (statistics chapter), Technical Note
- Software: `judicial-statistics` repository (existing) + SPJEJ Platform (planned)
- Datasets: DS01 — judicial statistics yearbook data

---

## P04 — CS GREFFE OS (Open-Source Court Registry System)

| Field | Value |
|---|---|
| Type | Research software project |
| Primary theme | T2 Digital Justice |
| Research questions | RQ4.2 |
| Status | Requirements analysis planned; two repositories exist (`cs-greffe-os`, `cs-greffe-os-v2`) — canonicity to be resolved per the ecosystem audit |
| Target milestone | MVP by Q4 2026; v1.0 stable 2027 |

**Objectives.**

- Develop an open-source digital court registry platform designed for
  low-resource deployment in African judicial institutions.
- Companion e-learning platform: `cs-greffe-os-cloud`.
- Contribute a reference implementation that grounds the digital-justice
  research track empirically.

**Scientific contribution.**

- Reference architecture for registry systems under
  civil-law / OHADA constraints.
- Case study demonstrating the JDGF applied in a production-adjacent
  context.
- Software architecture paper (planned).

**Cross-links.**

- Software repositories: `cs-greffe-os`, `cs-greffe-os-v2`, `cs-greffe-os-cloud`
- Case study: CS03 (CS GREFFE OS implementation)
- Publications: WP04, technical/architecture paper
- Framework: JDGF (implementation reference)

---

## P05 — AI PhD Agent / Data Agents

| Field | Value |
|---|---|
| Type | Research software project (AI-assisted research) |
| Primary theme | T3 Responsible AI |
| Research questions | Research infrastructure — cross-cutting |
| Status | In design; existing repo `data-agents` per the ecosystem audit |
| Target milestone | Prototype by Q4 2026 |

**Objectives.**

- Build an AI-assisted research agent supporting the doctoral
  trajectory (data ingestion, RAG, synthesis, drafting, evaluation).
- Study the agent itself as a Responsible-AI case: transparency of
  provenance, prompt policies, guardrails against fabricated citations.

**Scientific contribution.**

- Reference architecture for AI-assisted doctoral research infrastructure.
- Contribution to the emerging literature on AI in scholarly workflows.
- Documented safeguards against fabricated evidence — a live
  demonstration of the programme's own ethical commitments.

**Cross-links.**

- Software repository: `data-agents` (to be renamed to
  `judicial-ai-agents` per the ecosystem audit)
- Publications: methodology note; JA (Responsible AI in scholarly work)
- Framework: JDGF (accountability principles applied to the agent)

---

## Project × research-question × theme matrix

| Project | Primary theme | Questions | Publications | Software | Datasets |
|---|---|---|---|---|---|
| P01 — WP01 | T7 | RQ1.1, RQ1.2, RQ1.3 | WP01 | — | DS01 (planned) |
| P02 — JDGF | T1 | RQ1.5, RQ5.1, RQ5.3 | WP01, WP03, JA01 | JDGF Toolkit | — |
| P03 — SPJEJ | T5 | RQ3.1, RQ5.3 | WP03, Technical Note | judicial-statistics, SPJEJ Platform | DS01 |
| P04 — CS GREFFE OS | T2 | RQ4.2 | WP04 | cs-greffe-os, cs-greffe-os-cloud | — |
| P05 — Data Agents | T3 | (cross-cutting) | Methodology note | data-agents | — |

---

## Governance of the project register

- **Added** when a project has: an objective, a scientific contribution
  statement, and at least one identified deliverable.
- **Retired** when the last deliverable is either published or has been
  reclassified as out of scope.
- **Never** listed if the project is a fantasy — this register is a
  commitment, not a wish list.

Update policy: any material change to project status is committed with
a `docs(lab): update project register` message, and if the change is
substantive it is also recorded in the CHANGELOG.

*Aspirational names, invented partnerships, or partnerships-in-negotiation
that have not been confirmed by the partner are NOT included here.*
