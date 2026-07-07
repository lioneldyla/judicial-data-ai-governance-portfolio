# Changelog

All notable changes to this research portfolio are documented in this file.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
Versioning follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

### Added — WP01 publication infrastructure

- `working_papers/WP01/` supporting files landed: `ABSTRACT.md`,
  `KEYWORDS.md`, `AUTHORS.md`, `CITATION.md`, `CITATION.cff`, `LICENSE.md`,
  `VERSION.md`, `CHANGELOG.md`, `REFERENCES.bib` (scaffold — no fabricated
  entries), `REFERENCES_APA.md` (scaffold), `METADATA.yml`, and `WP01.md`
  (annotated section outline — the manuscript body remains to be drafted
  by the author of record).
- `working_papers/WP01/{figures,tables,supplementary_materials,datasets,appendices,media}/`
  preserved with `.gitkeep`.
- `governance/implementations/` directory added with:
  - `README.md` — index of implementation records
  - `2026-07-07_WP01-publication-infrastructure.md` — the seven-step
    deliverable record for this change (Master Spec v3.0 §Deliverables)

### Added — WP01 publication-readiness pass

- `working_papers/WP01/PUBLICATION_PACKAGE.md` — manifest of the complete
  publication package with consistency rules across identity / citation /
  governance / bibliography / manuscript / package-management layers.
- `working_papers/WP01/RELEASE_CHECKLIST.md` — ordered pre-release checks
  and release procedure for Git tag + Zenodo capture + ORCID sync + SSRN.
- `working_papers/WP01/SUBMISSION_TARGETS.md` — Zenodo, SSRN, and
  peer-reviewed journal requirements captured per venue.
- `governance/implementations/2026-07-07_WP01-publication-readiness.md` —
  the six-step deliverable record following the Phase-3 spec template.

### Changed — Version scheme

- `working_papers/WP01/VERSION.md`: split single version into **package**
  and **manuscript** version tracks. `CITATION.cff` retains the package
  version to satisfy CFF schema; manuscript state is externally-visible via
  release tag names (`wp01-v0.1-package`, `wp01-v0.5-draft`, etc.).

### Fixed — ORCID correctness across the repository

Wrong ORCID `0009-0007-3691-9953` corrected to `0009-0007-3762-9792` in
six files. Because `_config.yml` feeds `jekyll-seo-tag`, this fix
propagates the correct author identity to every deployed GitHub Pages page.

- `_config.yml` (2 occurrences — `author.orcid` and `social.links`)
- `docs/working_papers/WP01/README.md` — full page rewritten as a
  GH-Pages landing that matches the canonical WP01 identity and links to
  the source directory (no content duplication).
- `docs/frameworks/JDGF/README.md` — targeted ORCID string fix only.
- `docs/journal_articles/README.md` — targeted ORCID string fix only.
- `docs/academic_profiles/PROFILES.md` — targeted ORCID string fix only.
- `ROADMAP.md` — targeted ORCID string fix in footer only.

### Ongoing

- WP01 manuscript body — to be drafted by the author of record
- WP02 outline — in preparation
- JDGF Framework documentation — in development
- Zenodo DOI integration — pending first release

---

## [2.0.0] — 2026-07-07

### Added — RDI v2.0 Full Deployment

#### Research Content
- Added `working_papers/WP02/` — placeholder structure for WP02 (Responsible AI in African Judiciaries)
- Added `ROADMAP.md` — medium-term scientific production roadmap (2026–2027)
- Added `academic_profiles/README.md` — academic ecosystem documentation (updated to English)

#### Repository Infrastructure
- Updated `CITATION.cff` to version 2.0 with corrected ORCID and English affiliation
- Updated `README.md` — full English version with RDI v2.0 structure
- Added READMEs for all portfolio folders: `journal_articles/`, `conference_papers/`, `datasets/`, `software/`, `presentations/`, `bibliography/`, `research_notes/`, `archive/`, `assets/`

#### Academic Integration
- ORCID profile linked: [0009-0007-3762-9792](https://orcid.org/0009-0007-3762-9792)
- Zenodo integration planned for first release (DOI pending)
- SSRN profile registration planned
- GitHub Pages deployment configured

---

## [1.0.0] — 2026-07-06

### Added — Initial Repository

#### Repository Infrastructure
- Initialized public GitHub repository `judicial-data-ai-governance-portfolio`
- Added `LICENSE` — Creative Commons Attribution 4.0 International (CC BY 4.0)
- Added `CITATION.cff` — machine-readable citation metadata (version 1.2.0 spec)
- Added `README.md` — professional research portfolio homepage
- Added `CHANGELOG.md` — this file
- Added `ROADMAP.md` — 2026-2027 research roadmap
- Added `CODE_OF_CONDUCT.md` — Contributor Covenant v2.1
- Added `CONTRIBUTING.md` — contribution and collaboration guidelines
- Added `SECURITY.md` — responsible disclosure policy
- Added `.gitignore` — standard academic/Python/macOS gitignore rules

#### Repository Structure
- Created folder skeleton: `working_papers/`, `journal_articles/`, `conference_papers/`, `frameworks/`, `datasets/`, `software/`, `presentations/`, `bibliography/`, `research_notes/`, `academic_profiles/`, `archive/`, `docs/`, `assets/`

#### Research Content
- Added `working_papers/WP01/` — placeholder structure for WP01 (Judicial Data Governance Framework)
- Added `frameworks/JDGF/` — placeholder structure for the Judicial Data Governance Framework
- Added `docs/index.md` — GitHub Pages landing page
- Added `academic_profiles/README.md` — academic ecosystem documentation

#### Academic Integration
- ORCID profile linked: [0009-0007-3762-9792](https://orcid.org/0009-0007-3762-9792)
- Zenodo integration planned for first release (DOI pending)
- SSRN profile registration planned
- GitHub Pages deployment configured

---

*Maintained by DJORO Yoboukoua Lionel Arnaud — contact@lioneldyla.github.io*
