# 06 — Documentation Audit

> Per-repository documentation gaps against the **Documentation Standard**
> defined in the mission brief. Documentation of *archived* and *Le Wagon
> exercise* repos is out of scope — only active programme repos are audited
> here. The Portfolio itself is audited separately at the end.

---

## Documentation Standard (reference)

Every active repository should contain, where appropriate:

`README.md` · `AGENTS.md` · `PROJECT_STATUS.md` · `ROADMAP.md` ·
`ARCHITECTURE.md` · `CHANGELOG.md` · `CONTRIBUTING.md` · `CODE_OF_CONDUCT.md`
· `SECURITY.md` · `LICENSE` · `CITATION.cff` · `docs/` · `assets/`

`AGENTS.md`, `PROJECT_STATUS.md`, and `ARCHITECTURE.md` are the three
files that the mission brief singles out as required deliverables per
repository. This audit weights them heavily.

---

## Gap matrix (active programme repos)

Legend: ✔ present · ✘ missing · ? unknown (needs Phase-1 clone) ·
— not applicable

| Repo | README | AGENTS | STATUS | ROADMAP | ARCH | CHANGELOG | CONTRIB | COC | SECURITY | LICENSE | CITATION | docs/ | assets/ |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| judicial-data-ai-governance-portfolio | ✔ | ✘ | ✘ | ✔ | ✘ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ | ✔ |
| jdgf-framework | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? |
| JDGF-LAB-FRAMEWORK | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? |
| living-digital-governance-platform | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? |
| judicial-statistics | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? |
| cs-greffe-os / v2 / cloud | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? |
| data-agents | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? |
| monitor-the-reactor | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? |
| working-papers | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? |
| lioneldyla (profile) | ✔ | — | — | — | — | — | — | — | — | — | — | — | — |
| personal-branding | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? | ? |

The `?` cells are the Phase-1 verification checklist. Rather than guess,
Phase 1 clones each repo and fills this table in as a single-source-of-truth
audit CSV that lives in `governance/ecosystem-audit/verification/`.

---

## Portfolio-specific gaps (confirmed)

The Portfolio has strong governance documentation but is missing three of
the mission-mandated files:

### `AGENTS.md` — **MISSING**

A template scoped to this repository is proposed:

```markdown
# AGENTS.md — Judicial Data & AI Governance Portfolio

## Repository mission
Central research portfolio for the Data Governance for Intelligent Justice
Systems programme. Contains only research artefacts — working papers, white
papers, framework documentation, research notes, publications, datasets,
citation assets, roadmaps, and strategic documentation.

## Repository scope
IN: research documents; framework conceptual docs; publication pipelines
(Zenodo, SSRN); GitHub Pages site; academic profile metadata.
OUT: production software; deployable services; live datasets under
transformation. Those live in sibling repos.

## Coding standards
Not applicable — this repo is documentation-first. When drive-by scripts are
needed (e.g., release automation), they go in `.scripts/` with Bash or
Python, style enforced by `shellcheck` / `ruff`.

## Documentation rules
- Every top-level `.md` at root is either governance, administration, or a
  research policy — see RESEARCH_PORTFOLIO_HANDBOOK.md.
- Publication artefacts live under `working_papers/`, `journal_articles/`,
  `conference_papers/`, `frameworks/`, `datasets/`, `presentations/`,
  `bibliography/`.
- `docs/` mirrors the GitHub Pages site.
- Never place production code here.

## Branching strategy
Default: `main`. Feature work: `claude/*`, `feature/*`, `docs/*`, `fix/*`.
Never commit directly to `main` from an agent session; always via PR.

## Commit conventions
Conventional Commits: `feat:`, `fix:`, `docs:`, `chore:`, `refactor:`.

## Release policy
Semantic versioning at repository level. Every release triggers Zenodo
snapshot + DOI + CHANGELOG entry.

## Prohibited actions
- Never introduce production software into this repository.
- Never delete governance documents; supersede via CHANGELOG + `docs/archive/`.
- Never rewrite public Git history on `main`.
- Never push to a repository not listed in the session's authorized scope.

## Development priorities
1. Complete WP01 publication pipeline (Zenodo DOI).
2. Draft WP02.
3. Standardize CITATION.cff across all programme repos.
4. Land the ecosystem-audit deliverables.

## Repository relationships
This repo cites: `jdgf-toolkit`, `judicial-statistics`,
`living-digital-governance-platform`, `cs-greffe-os`, `data-agents`,
`monitor-the-reactor`. See `governance/ecosystem-audit/03_DEPENDENCY_MAP.md`.
```

### `PROJECT_STATUS.md` — **MISSING**

Template:

```markdown
# PROJECT_STATUS.md — Judicial Data & AI Governance Portfolio

Last updated: YYYY-MM-DD

## Completed
- RDI v2.0 governance stack (README, LICENSE, CITATION, ROADMAP, policies)
- WP01 scaffold and abstract
- WP02 scaffold
- frameworks/JDGF/ conceptual scaffold
- Prior audits (REPOSITORY_AUDIT, AUDIT_REPORT, IMPROVEMENT_PLAN, GAP_ANALYSIS)
- Ecosystem audit (this branch)

## Current
- Ecosystem reorganization (branch: claude/github-ecosystem-audit-117kak)

## Open issues
- Zenodo DOI pending
- SSRN account pending
- Portfolio README lacks explicit ecosystem section listing sibling repos

## Technical debt
- Two audit reports duplicated (AUDIT_REPORT + REPOSITORY_AUDIT)
- Two improvement plans duplicated (IMPROVEMENT_PLAN + REPOSITORY_IMPROVEMENT_PLAN)
- Missing AGENTS.md, PROJECT_STATUS.md, ARCHITECTURE.md at root

## Pending migrations
- `working-papers` repo → this repo's `working_papers/` (pending user decision)

## Next milestones
- Land ecosystem-audit deliverables (this PR).
- WP01 → Zenodo + SSRN (Q3 2026).
- WP02 first draft (Q3 2026).
- JDGF Toolkit v1.0 methodology chapter (Q3 2026).
```

### `ARCHITECTURE.md` — **MISSING**

Template:

```markdown
# ARCHITECTURE.md — Judicial Data & AI Governance Portfolio

## Repository organization
Five-layer research infrastructure per RESEARCH_PORTFOLIO_HANDBOOK.md:
governance / production / assets / knowledge / identity.

## Repository dependencies
This repo is the DAG root of the ecosystem. It has no inbound code deps.
It has outbound citations to `jdgf-toolkit`, `judicial-statistics`,
`living-digital-governance-platform`, `cs-greffe-os`, `data-agents`,
`monitor-the-reactor`.

## Software architecture
None — this repository does not host production software.

## Research architecture
Programme "Data Governance for Intelligent Justice Systems", three pillars:
Data Governance, Digital Justice, AI Governance. Ten-year strategy
2026–2035. See RESEARCH_STRATEGY_2026-2035.md.

## Future evolution
- 2026–2027: Working papers WP01–WP04 + JDGF v1.0.
- 2027–2028: Doctoral research begins.
- 2028+: Framework validation, journal articles, doctoral thesis.
```

---

## Consolidation of duplicated Portfolio audit files

See Duplication Report §5. Recommended target-state under the Portfolio:

```
governance/
├── ecosystem-audit/   ← this audit
├── history/           ← prior audits, preserved
│   ├── REPOSITORY_AUDIT.md
│   ├── REPOSITORY_IMPROVEMENT_PLAN.md
│   ├── AUDIT_REPORT.md
│   ├── IMPROVEMENT_PLAN.md
│   └── GAP_ANALYSIS.md
└── standards/         ← templates, checklists
    ├── AGENTS.template.md
    ├── PROJECT_STATUS.template.md
    ├── ARCHITECTURE.template.md
    └── ARCHIVAL_README.template.md
```

Root of the repository stays clean; the historical audits are preserved but
out of the way; the templates are reusable across the ecosystem.

---

## Portfolio's `_config.yml` (GitHub Pages)

Present. Not audited in depth in this pass — Phase-1 verification should
confirm the Jekyll theme, that the docs/ Markdown builds, and that
`docs/index.md` is the entry.

---

## Cross-repo README template (for programme software repos)

Every software repo should have a README following this skeleton (details
per-repo in a per-repo `AGENTS.md`):

```markdown
# <Repo Name>

> One-line tagline naming the mission.

[![Portfolio](https://img.shields.io/badge/Portfolio-Judicial%20Data%20%26%20AI-blue)](https://github.com/lioneldyla/judicial-data-ai-governance-portfolio)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0007--3762--9792-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0007-3762-9792)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## What is this
2-3 sentences: mission, scope, and who it's for.

## Ecosystem
This repository is part of the Data Governance for Intelligent Justice
Systems research programme. Related work:
- Research portfolio: `judicial-data-ai-governance-portfolio`
- Framework: `jdgf-toolkit`
- (add other sibling repos)

## Quickstart
Install + one working command that demonstrates the repo.

## Documentation
See `docs/` and the Portfolio.

## Citation
See `CITATION.cff`.

## License
See `LICENSE`.
```
