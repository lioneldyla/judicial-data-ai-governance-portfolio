# Repository Improvement Plan

**Programme:** Data Governance for Intelligent Justice Systems  
**Repository:** `lioneldyla/judicial-data-ai-governance-portfolio`  
**Version:** 1.0  
**Date:** 2026-07-06  
**Reference:** REPOSITORY_AUDIT.md — findings v1.0  

---

## 1. Purpose

This document translates the findings from `REPOSITORY_AUDIT.md` into a structured, prioritized action plan. It defines what will be created, improved, or reorganized — and in what order — to transform the repository into an internationally recognized academic research portfolio.

---

## 2. Guiding Principles

Every action in this plan is guided by three constraints:

1. **Preserve existing work.** No existing file is deleted or replaced unless a clear quality improvement is demonstrated.
2. **Improve rather than replace.** Existing documents are upgraded in place; their Git history is maintained.
3. **Handbook compliance.** The Research Portfolio Handbook v1.0 is the documentary reference. Every artifact created must correspond to a defined Handbook section.

---

## 3. Improvement Actions — Phase 1 (Governance & Policies)

### Priority: HIGH | Timeline: Immediate

| # | Action | File | Handbook Ref | Status |
|---|--------|------|--------------|--------|
| 1 | Create Open Science Policy | `OPEN_SCIENCE_POLICY.md` | §16 | ✅ Done |
| 2 | Create Publication Policy | `PUBLICATION_POLICY.md` | §15 | ✅ Done |
| 3 | Create Research Ethics | `RESEARCH_ETHICS.md` | §17 | ✅ Done |
| 4 | Create Data Governance Principles | `DATA_GOVERNANCE_PRINCIPLES.md` | §18 | ✅ Done |
| 5 | Create AI Governance Principles | `AI_GOVERNANCE_PRINCIPLES.md` | §19 | ✅ Done |
| 6 | Create Doctoral Research Plan | `DOCTORAL_RESEARCH_PLAN.md` | §22 | ✅ Done |
| 7 | Create Repository Audit Report | `REPOSITORY_AUDIT.md` | Deliverable | ✅ Done |
| 8 | Create Repository Improvement Plan | `REPOSITORY_IMPROVEMENT_PLAN.md` | Deliverable | ✅ Done |
| 9 | Normalize strategy filename | `RESEARCH_STRATEGY_2026_2035.md` | §14 | 📋 Planned |

---

## 4. Improvement Actions — Phase 2 (Research Output Scaffolds)

### Priority: HIGH | Timeline: July–August 2026

| # | Action | Path | Handbook Ref | Status |
|---|--------|------|--------------|--------|
| 10 | Create WP01 directory structure | `working_papers/WP01/` | §11 | 📋 Planned |
| 11 | Create WP01 README | `working_papers/WP01/README.md` | §11 | 📋 Planned |
| 12 | Create WP01 metadata | `working_papers/WP01/metadata.yml` | §11 | 📋 Planned |
| 13 | Create JDGF directory structure | `frameworks/JDGF/` | §12 | 📋 Planned |
| 14 | Create JDGF README | `frameworks/JDGF/README.md` | §12 | 📋 Planned |
| 15 | Create academic profiles README | `docs/academic_profiles/README.md` | §10 | 📋 Planned |

---

## 5. Improvement Actions — Phase 3 (Directory Architecture)

### Priority: MEDIUM | Timeline: August–September 2026

| # | Action | Path | Notes | Status |
|---|--------|------|-------|--------|
| 16 | Init `docs/frameworks/` | `.gitkeep` | Navigation | 📋 Planned |
| 17 | Init `docs/working_papers/` | `.gitkeep` | Navigation | 📋 Planned |
| 18 | Init `docs/journal_articles/` | `.gitkeep` | Future track | 📋 Planned |
| 19 | Init `docs/conference_papers/` | `.gitkeep` | Future track | 📋 Planned |
| 20 | Init `docs/datasets/` | `.gitkeep` | FAIR data | 📋 Planned |
| 21 | Init `docs/software/` | `.gitkeep` | Research software | 📋 Planned |
| 22 | Init `docs/bibliography/` | `.gitkeep` | Reference management | 📋 Planned |
| 23 | Init `docs/research_notes/` | `.gitkeep` | Research workspace | 📋 Planned |
| 24 | Init `docs/presentations/` | `.gitkeep` | Academic dissemination | 📋 Planned |
| 25 | Init `docs/assets/` | `.gitkeep` | GitHub Pages assets | 📋 Planned |
| 26 | Init `docs/archive/` | `.gitkeep` | Archival | 📋 Planned |

---

## 6. Improvement Actions — Phase 4 (Open Science Integration)

### Priority: MEDIUM | Timeline: Q4 2026

| # | Action | Notes | Status |
|---|--------|-------|--------|
| 27 | Register on Zenodo | Link DOI to repository | 📋 Planned |
| 28 | Add `_config.yml` for GitHub Pages | Enable Pages site | 📋 Planned |
| 29 | Verify ORCID integration | `https://orcid.org/0009-0007-3762-9792` | 📋 Planned |
| 30 | Register on SSRN | Upload WP01 preprint | 📋 Planned |
| 31 | Add OpenAIRE metadata | `codemeta.json` | 📋 Planned |
| 32 | Add `FUNDING.yml` | Declare funding sources | 📋 Planned |

---

## 7. Documentation Quality Improvements

### Priority: LOW | Timeline: Ongoing

| # | Document | Improvement | Status |
|---|----------|-------------|--------|
| 33 | `README.md` | Add badge row (license, ORCID, version) | 📋 Planned |
| 34 | `CHANGELOG.md` | Add Phase 1 entry | ✅ Done |
| 35 | `docs/index.md` | Add cross-links to new governance docs | 📋 Planned |
| 36 | All docs | Verify internal links point to existing files | 📋 In Progress |

---

## 8. Quality Assurance Protocol

Before any phase is considered complete, the following checks must pass:

- [ ] All Markdown renders without errors on GitHub
- [ ] All internal links resolve to existing files
- [ ] No unfinished placeholder text (except sections explicitly marked `[Future Work]`)
- [ ] Metadata fields complete in every document header
- [ ] Filenames consistent with UPPER_SNAKE_CASE convention at root level
- [ ] CHANGELOG.md updated with all changes

---

## 9. Success Criteria

The repository modernization is complete when:

1. All 22 Handbook-required documents exist
2. All `docs/` subdirectories are initialized
3. Research output scaffolds (WP01, JDGF) are created
4. Zenodo DOI is registered
5. GitHub Pages renders `docs/index.md` as home page
6. ORCID profile links to this repository
7. CITATION.cff is valid and up to date

---

## 10. Document Governance

| Field | Value |
|-------|-------|
| Version | 1.0 |
| Author | DJORO Yoboukoua Lionel Arnaud |
| Created | 2026-07-06 |
| Review Cycle | Per phase completion |
| Category | Administration |

---

*This improvement plan is a living document. Update the status column upon completion of each action.*
