# 07 — Metadata Audit

> Standardization of the GitHub-level metadata: description, topics,
> homepage, license, default branch, badges. Metadata changes are cheap and
> reversible, and materially improve discoverability (SEO on GitHub, ORCID,
> and Zenodo indexing).

---

## Standards

### Description

- **Length:** ≤160 characters (fits GitHub's card preview).
- **Style:** sentence case, ends without period; names the mission, not the tech.
- **Language:** English (primary); avoid Franglais.
- **Signals to include:** *what* + *for whom* + *geographic/thematic scope*.

### Topics

4–8 topics per repo. Reserve these:

| Category | Topics |
|---|---|
| Geography | `africa`, `cote-divoire`, `sub-saharan-africa`, `west-africa`, `ohada`, `ecowas` |
| Domain | `judicial-data-governance`, `digital-justice`, `justice`, `public-sector`, `rule-of-law` |
| AI theme | `responsible-ai`, `ai-governance`, `algorithmic-accountability` |
| Data theme | `data-governance`, `open-data`, `fair-data`, `judicial-statistics` |
| Method | `research`, `framework`, `maturity-model`, `open-science`, `working-paper` |
| Tech | `python`, `fastapi`, `streamlit`, `docker`, `power-bi`, `postgresql` |

Rules: every research repo must include at least one *Geography* + one
*Domain* + one *Method*. Software repos add *Tech*.

### Homepage

| Repo type | Homepage value |
|---|---|
| Core Research (Portfolio) | GitHub Pages URL (`https://lioneldyla.github.io/judicial-data-ai-governance-portfolio/`) |
| Framework | GitHub Pages URL if the framework has a docs site; else Portfolio URL |
| Software Product | Deployed app URL or docs URL |
| Platform | Live platform URL or Portfolio |
| Demonstration | Live demo URL (Streamlit / HF Space / GCP) |
| Profile | `linkedin.com/in/lioneldyla` (public identity) |
| Archive | Blank |

### License

| Repo type | License |
|---|---|
| Research / documentation | CC-BY-4.0 |
| Software product | MIT (default) or Apache-2.0 (if patents matter) |
| Datasets | CC-BY-4.0 (unless ethical constraints require otherwise) |
| Profile / Archive | CC-BY-4.0 or no license (private) |

### Default branch

All active repos → `main`. Rename `master` → `main` and update remote HEAD
and any GitHub Actions references.

Any repo with a non-`main` non-`master` default (e.g.,
`JDGF-LAB-FRAMEWORK` on `codex/advanced-rag-contracts`) must have its
default branch corrected to a real trunk before any other work.

### README badge row (top of README, one line)

Order (left → right):

`Portfolio · ORCID · License · Programme · DOI (if applicable) · Build/CI`

Reference implementation from the Portfolio's own README (already good):

```
[![ORCID]…] [![License: CC BY 4.0]…] [![DOI]…] [![GitHub Pages]…]
[![Open Science]…] [![RDI]…]
```

Software repos add `[![CI]…]` from GitHub Actions once a workflow exists.

---

## Per-repo diagnosis and prescription

### judicial-data-ai-governance-portfolio (Portfolio)

| Field | Current | Prescribed |
|---|---|---|
| Description | "Research portfolio on Judicial Data Governance, Digital Justice, Responsible AI and Public Sector Transformation in Africa." | ✅ Keep |
| Topics | (none) | Add: `judicial-data-governance`, `digital-justice`, `responsible-ai`, `africa`, `cote-divoire`, `research`, `open-science`, `working-paper` |
| Homepage | (not set) | `https://lioneldyla.github.io/judicial-data-ai-governance-portfolio/` |
| License | CC-BY-4.0 | ✅ Keep |
| Default branch | `main` | ✅ Keep |
| DOI | Pending | Zenodo release → back-fill badge |

### jdgf-framework

| Field | Current | Prescribed |
|---|---|---|
| Description | "Judicial Data Governance Framework — Tools, methodology and maturity model for governing data in African judicial institutions" | ✅ Keep; drop the phrase "Tools" if the code has no tooling yet |
| Topics | africa, data-governance, digital-transformation, judicial-systems, justice, public-sector, python, responsible-ai | ✅ Keep; add `framework`, `maturity-model`, `open-science` |
| Homepage | (not set) | Portfolio URL |
| License | ? | Verify LICENSE file; if missing add MIT (code) + CC-BY-4.0 (docs) |
| DOI | — | Zenodo when v1.0 is tagged |

### JDGF-LAB-FRAMEWORK

| Field | Current | Prescribed |
|---|---|---|
| Description | "A modular governed framework for AI-assisted projects knowledge systems and data-governance research" | Replace: name distinct mission (RAG + agents lab) if kept as active |
| Topics | ai-governance, data-governance, judicial-data, knowledge-systems, multi-agent, python, rag | ✅ Keep if repo survives; else clear on archive |
| Default branch | `codex/advanced-rag-contracts` | **Fix immediately → `main`** |
| Name | Uppercase, hyphenated | Rename → `jdgf-lab` (kebab-case) |

### living-digital-governance-platform

| Field | Current | Prescribed |
|---|---|---|
| Description | "A public governance framework for digital transformation, data governance, AI governance and digital justice." | Sharpen: say what makes it a "platform" — is it a deployed application or a set of documents? |
| Topics | (none) | Add: `platform`, `data-governance`, `ai-governance`, `digital-justice`, `public-sector`, `africa`, `governance-framework` |
| Homepage | (not set) | Portfolio or deployed URL |
| License | ? | Verify |

### judicial-statistics

| Field | Current | Prescribed |
|---|---|---|
| Description | "Data pipelines and methodology for the Judicial Statistics Yearbooks — Ministry of Justice, Côte d'Ivoire (2019 & 2023)" | ✅ Keep |
| Topics | africa, data-analysis, judicial-statistics, justice, power-bi, public-sector, python, statistics | ✅ Keep; add `open-data`, `cote-divoire`, `data-pipeline` |
| Homepage | (not set) | Portfolio URL or the yearbook publication URL if public |
| License | ? | Verify; MIT for pipelines |

### cs-greffe-os / cs-greffe-os-v2 / cs-greffe-os-cloud

| Field | v1 | v2 | cloud |
|---|---|---|---|
| Description | (none) | (none) | "CS GREFFE OS Learn - prototype cloud e-learning" |
| Prescribed description (canonical) | — | "Open-source court registry operating system for African judiciaries" | "E-learning companion for CS GREFFE OS — training judiciary staff on the registry OS" |
| Topics | — | `court-registry`, `judicial-systems`, `open-source`, `africa`, `justice`, `python`, `ohada` | `e-learning`, `training`, `court-registry`, `judicial-systems`, `africa` |
| Homepage | — | Live demo URL when available | Live training platform URL |
| License | — | MIT or Apache-2.0 | MIT or CC-BY-SA for course content |
| Visibility | Private | Public (canonical) | Private (until launch) |

### data-agents

| Field | Current | Prescribed |
|---|---|---|
| Description | (none) | "Multi-agent AI toolkit assisting doctoral research in judicial data governance — data ingestion, RAG, synthesis, drafting" |
| Topics | (none) | Add: `ai-agents`, `multi-agent`, `research-assistant`, `rag`, `python`, `doctoral-research`, `open-science` |
| Name | `data-agents` (collides with Le Wagon prefix) | Rename → `judicial-ai-agents` or `data-agents-toolkit` |

### monitor-the-reactor

| Field | Current | Prescribed |
|---|---|---|
| Description | ✅ Detailed | ✅ Keep |
| Topics | ✅ Complete | Add `demo`, `portfolio` |
| Homepage | (not set) | Streamlit / GCP demo URL |
| License | ? | Verify — likely MIT |

### working-papers

| Field | Current | Prescribed |
|---|---|---|
| Description | "Working Papers on Judicial Data Governance & Responsible AI — Lionel Dyla" | If kept: sharpen to name the vehicle (SSRN series?). If archived: change to "Superseded by judicial-data-ai-governance-portfolio/working_papers/" |
| Homepage | (not set) | If archived: Portfolio URL |
| License | ? | CC-BY-4.0 |

### lioneldyla (profile)

| Field | Current | Prescribed |
|---|---|---|
| Description | "Judicial Data & AI Governance Architect \| Data Governance · Digital Justice · Responsible AI" | ✅ Keep |
| Homepage | (not set) | LinkedIn URL |
| Special | This is a GitHub-magic repo — README renders as profile page | Only edit README; no LICENSE, CITATION, or docs/ needed |

### personal-branding

| Field | Current | Prescribed |
|---|---|---|
| Description | "Building an international academic and professional identity in Judicial Data Governance, Digital Justice and Responsible AI." | If kept public: keep. If merged/archived: change to "Superseded — see lioneldyla profile + personal-archive" |
| Visibility | Public | **Consider making private** — branding strategy is not intended public content |

### personal-archive

| Field | Current | Prescribed |
|---|---|---|
| Description | ✅ | ✅ Keep |
| Visibility | Private | ✅ Keep |
| License | — | Not required (private) |

### Playground

| Field | Current | Prescribed |
|---|---|---|
| Description | (none) | "Public sandbox for one-off experiments and template scaffolds" |
| Topics | (none) | `sandbox`, `experiments` |
| Name | `Playground` | Rename → `playground` (kebab-case) |

### blank-app-1

Recommend deletion (empty template) or fold into `playground/`.

### Leken.ci

Blocker — user decision. Rename in any case (drop the `.` in the repo name;
GitHub allows dots but they break some tooling).

### Le Wagon exercises (~87)

For every `data-*` repo, before archival:

- Fix default branch to `main`.
- Add topic `le-wagon`, `bootcamp-exercise`, `data-science`.
- Leave description unchanged (Le Wagon repos have none anyway).
- Homepage: none.
- License: MIT (educational).

If consolidating into `le-wagon-archive`, the individual metadata changes
become moot.

---

## Metadata "before / after" audit script

Once user approves, this can be executed programmatically. Rough sketch
(not to be run without approval):

```bash
# For each repo: set description, topics, homepage via gh CLI
gh repo edit lioneldyla/jdgf-framework \
  --description "Judicial Data Governance Framework — methodology and maturity model for governing data in African judicial institutions" \
  --homepage "https://lioneldyla.github.io/judicial-data-ai-governance-portfolio/" \
  --add-topic framework,maturity-model,open-science
```

Any bulk operation must be preceded by a `--dry-run` capture so we have a
before/after diff on record.
