# Research Portfolio Handbook

> **Version:** 1.1.0 | **Category:** Governance  
> **Author:** DJORO Yoboukoua Lionel Arnaud  
> **Last Updated:** July 2026  
> **Status:** Canonical Reference

---

## Purpose

This handbook is the authoritative reference for the organisation, governance, and maintenance of the *Data Governance for Intelligent Justice Systems* research portfolio. It defines the documentary architecture, quality standards, file naming conventions, versioning rules, and publication workflows that govern all repository contributions.

Every document, dataset, and software artifact in this repository should be able to trace its existence and organisation back to this handbook.

---

## Repository Architecture

### Root Level — Governance and Identity Files

| File | Category | Purpose |
|---|---|---|
| `README.md` | Governance | Primary landing page and programme overview |
| `LICENSE` | Governance | Legal terms (CC BY 4.0) |
| `CITATION.cff` | Governance | Machine-readable citation metadata |
| `CHANGELOG.md` | Governance | Version history of the repository |
| `ROADMAP.md` | Governance | Strategic development timeline |
| `CODE_OF_CONDUCT.md` | Governance | Community and contribution norms |
| `CONTRIBUTING.md` | Governance | Contribution guidelines |
| `SECURITY.md` | Governance | Security and responsible disclosure |
| `RESEARCH_MANIFESTO.md` | Governance | Research vision and values |
| `LAB_CHARTER.md` | Governance | Research programme charter |

### Root Level — Research Programme Documents

| File | Category | Purpose |
|---|---|---|
| `RESEARCH_AGENDA.md` | Research | Active research question register |
| `RESEARCH_STRATEGY_2026-2035.md` | Research | Long-term strategic plan |
| `DOCTORAL_RESEARCH_PLAN.md` | Research | PhD preparation roadmap |
| `RESEARCH_ETHICS.md` | Research | Ethics principles and commitments |
| `DATA_GOVERNANCE_PRINCIPLES.md` | Framework | Core data governance principles |
| `AI_GOVERNANCE_PRINCIPLES.md` | Framework | Core AI governance principles |
| `OPEN_SCIENCE_POLICY.md` | Research | Open science commitment |
| `PUBLICATION_POLICY.md` | Research | Publication standards |

### Root Level — Repository Management

| File | Category | Purpose |
|---|---|---|
| `AUDIT_REPORT.md` | Administration | Repository audit findings |
| `REPOSITORY_AUDIT.md` | Administration | Detailed audit documentation |
| `REPOSITORY_IMPROVEMENT_PLAN.md` | Administration | Improvement roadmap |
| `GAP_ANALYSIS.md` | Administration | Documentation gap analysis |
| `IMPROVEMENT_PLAN.md` | Administration | Implementation plan |

### `docs/` — Research Artifacts by Type

```
docs/
├── frameworks/              # Research frameworks (JDGF, etc.)
│   └── JDGF/
├── working_papers/          # Working paper series
│   └── WP01/
├── journal_articles/        # Peer-reviewed publications
├── conference_papers/       # Conference papers and abstracts
├── datasets/                # FAIR research datasets
├── software/                # Research software and tools
├── bibliography/            # Curated bibliography
├── research_notes/          # Working notes (not peer-reviewed)
├── presentations/           # Slides and posters
├── academic_profiles/       # Researcher profiles and identifiers
├── assets/                  # Logos, diagrams, figures
├── archive/                 # Superseded documents
└── RESEARCH_PORTFOLIO_HANDBOOK.md  (this file)
```

---

## Document Categories

| Category | Description | Examples |
|---|---|---|
| **Governance** | Repository management and community norms | README, LICENSE, CODE_OF_CONDUCT |
| **Research** | Active research documents | Research agenda, ethics, strategy |
| **Publication** | Scholarly outputs | Working papers, journal articles, conference papers |
| **Framework** | Conceptual and methodological frameworks | JDGF, governance principles |
| **Dataset** | Research data | Judicial statistics, regulatory indices |
| **Software** | Computational tools | Diagnostic tools, analytical scripts |
| **Documentation** | Technical and organisational documentation | This handbook, bibliography |
| **Administration** | Repository maintenance | Audit reports, improvement plans |

---

## File Naming Conventions

### Root-Level Files
- SCREAMING_SNAKE_CASE for governance files: `CODE_OF_CONDUCT.md`
- Year suffixed for dated strategies: `RESEARCH_STRATEGY_2026-2035.md`

### `docs/` Artifacts
- **Working papers:** `WP[NN]/` directory with `README.md` and `WP[NN]_DRAFT.md`
- **Journal articles:** `JA[NN]/` directory with `README.md` and manuscript files
- **Conference papers:** `CP[NN]/` directory with `README.md` and paper files
- **Datasets:** `DS[NN]/` directory with `README.md`, data files, and codebook
- **Software:** `SW[NN]/` directory with `README.md` and source code

### Asset Files
```
[category]_[description]_[version].[ext]
Example: diagram_jdgf_architecture_v1.svg
         figure_judicial_stats_trends_2024.png
```

---

## Versioning

This repository uses [Semantic Versioning](https://semver.org/):

| Change Type | Version Increment | Example |
|---|---|---|
| Breaking structural reorganisation | MAJOR | 1.x.x → 2.0.0 |
| New documents or significant improvements | MINOR | x.1.x → x.2.0 |
| Editorial corrections, broken links, metadata fixes | PATCH | x.x.1 → x.x.2 |

All version changes must be documented in `CHANGELOG.md` using the [Keep a Changelog](https://keepachangelog.com/) format.

---

## Document Lifecycle

```
Draft → Under Review → Active → Superseded → Archived
```

| Status | Meaning |
|---|---|
| **Draft** | Under active development, not for citation |
| **Under Review** | Submitted for peer review or editorial review |
| **Active** | Current authoritative version |
| **Superseded** | Replaced by a newer version (old version archived) |
| **Archived** | Moved to `docs/archive/` — no longer updated |

---

## Quality Standards

### Scientific Quality
- Academic writing style throughout
- Claims supported by references or labelled as the author's position
- Methodology made explicit and reproducible
- Consistent terminology (a glossary will be maintained)

### Technical Quality
- Valid Markdown (renders correctly on GitHub and GitHub Pages)
- No broken internal links
- Relative links preferred over absolute links for internal navigation
- File sizes reasonable (large assets in `docs/assets/`)

### Open Science Quality
- FAIR principles applied to all datasets
- Persistent identifiers for all formal outputs
- Citation metadata maintained in `CITATION.cff`
- ORCID profile linked from all publications

---

## External Platform Integration

| Platform | Purpose | Status |
|---|---|---|
| **GitHub Pages** | Public web interface for the portfolio | Configured |
| **Zenodo** | Dataset and preprint archiving with DOI | Pending first deposit |
| **ORCID** | Researcher persistent identifier | Active |
| **SSRN** | Social science preprint server | Pending account creation |
| **OpenAIRE** | European open science infrastructure | Linked via ORCID |
| **DataCite** | Dataset metadata registry | Via Zenodo |

---

## Maintenance Schedule

| Task | Frequency | Responsible |
|---|---|---|
| Review and update CHANGELOG | On every significant commit | Author |
| Review internal links | Quarterly | Author |
| Update CITATION.cff | On each publication | Author |
| Full repository audit | Annually | Author |
| Review and update ROADMAP | Semi-annually | Author |
| Archive superseded documents | As needed | Author |
