# GitHub Ecosystem Audit — 2026-07-07

> Phase 1–2 deliverables of the GitHub Ecosystem Reorganization mission.
> Read-only diagnosis of the `lioneldyla` GitHub account. **No repository outside
> `judicial-data-ai-governance-portfolio` has been modified.**

---

| Field | Value |
|---|---|
| Author | DJORO Yoboukoua Lionel Arnaud |
| ORCID | [0009-0007-3762-9792](https://orcid.org/0009-0007-3762-9792) |
| Account audited | [github.com/lioneldyla](https://github.com/lioneldyla) |
| Repositories in scope | 110 (14 public, 96 private) |
| Method | Metadata inventory via GitHub search API + full read of the entry-point repository (`judicial-data-ai-governance-portfolio`) |
| Branch | `claude/github-ecosystem-audit-117kak` |
| Date | 2026-07-07 |
| Status | **Draft — Awaiting user validation before Phase 3 execution** |

---

## Mission Recap

The mission is a long-term architectural redesign of the entire GitHub account
so that it becomes suitable for international research collaborations, PhD
applications, software development, open-source contributions, long-term
maintenance, and AI-assisted development. This audit is the mandatory
diagnostic step that precedes any structural change.

**Guiding principle (from mission brief):** *Never perform destructive
actions before migration has been verified.* Accordingly, this audit
proposes; it does not execute.

---

## Deliverables

| # | Deliverable | File |
|---|---|---|
| 1 | Repository Inventory | [01_REPOSITORY_INVENTORY.md](01_REPOSITORY_INVENTORY.md) |
| 2 | Repository Classification Matrix | [02_CLASSIFICATION_MATRIX.md](02_CLASSIFICATION_MATRIX.md) |
| 3 | Dependency Map | [03_DEPENDENCY_MAP.md](03_DEPENDENCY_MAP.md) |
| 4 | Duplication Report | [04_DUPLICATION_REPORT.md](04_DUPLICATION_REPORT.md) |
| 5 | Migration Plan | [05_MIGRATION_PLAN.md](05_MIGRATION_PLAN.md) |
| 6 | Documentation Audit | [06_DOCUMENTATION_AUDIT.md](06_DOCUMENTATION_AUDIT.md) |
| 7 | Metadata Audit | [07_METADATA_AUDIT.md](07_METADATA_AUDIT.md) |
| 8 | Naming Audit | [08_NAMING_AUDIT.md](08_NAMING_AUDIT.md) |
| 9 | Archive Plan | [09_ARCHIVE_PLAN.md](09_ARCHIVE_PLAN.md) |
| 10 | Final Architecture Blueprint | [10_ARCHITECTURE_BLUEPRINT.md](10_ARCHITECTURE_BLUEPRINT.md) |

---

## What the audit found — headline numbers

| Bucket | Count | Recommended action |
|---|---:|---|
| Core research (Portfolio, this repository) | 1 | Keep and standardize |
| Public academic-programme repositories (JDGF, LDGP, judicial-statistics, monitor-the-reactor, working-papers, personal-branding, lioneldyla profile) | 7 | Keep, standardize, resolve JDGF overlap |
| Software products (CS GREFFE OS family) | 3 | Consolidate around one canonical repo |
| AI / data agents (private) | 1 | Keep private, standardize docs |
| Playground / sandbox (Playground, blank-app-1) | 2 | Consolidate into single `playground` |
| Le Wagon Data Science bootcamp exercises (`data-*` prefix, mostly private) | ~87 | Bulk archive into a `le-wagon-archive` collection |
| GitHub tutorial residue (desktop-tutorial, skills-introduction-to-github) | 2 | Archive as `Legacy Projects` |
| Website / branding side-projects (Leken.ci, taxifare-website) | 2 | Archive or absorb |
| **Total** | **110** | |

The single biggest gain is turning ~90 orphaned tutorial/exercise repositories
into an intentional archive so that the account front page shows only 15–20
purposeful repositories, each answering a clear question.

---

## Reading order

If you are the researcher: read **10_ARCHITECTURE_BLUEPRINT.md** first — it
frames the target end-state — then **05_MIGRATION_PLAN.md** for the concrete
sequence, then dive into the individual audits for details.

If you are an AI coding agent picking this up in a future session: read this
README, then **02_CLASSIFICATION_MATRIX.md**, then **10_ARCHITECTURE_BLUEPRINT.md**.
Those three files are enough to continue the work without prior conversation
context.

---

## Open questions requiring user decision

These block Phase 3 (execution). They are consolidated at the end of
**10_ARCHITECTURE_BLUEPRINT.md** with per-question context and a
recommendation.

1. Which JDGF repository is canonical: `jdgf-framework` or `JDGF-LAB-FRAMEWORK`?
2. Which CS GREFFE OS repository is canonical: `cs-greffe-os` (private) or `cs-greffe-os-v2` (public)? What is the relationship with `cs-greffe-os-cloud`?
3. What is the purpose of the standalone `working-papers` repository, and does it duplicate `judicial-data-ai-governance-portfolio/working_papers/`?
4. What is `Leken.ci`? Should it stay private, become public, or archive?
5. How should the ~87 Le Wagon exercises be archived — bulk-archive-in-place (GitHub archive flag), consolidate into a `le-wagon-archive` monorepo, or delete after a Zenodo capture?
6. Does the account want a separate `personal-branding` repo alongside the `lioneldyla` profile README?

---

*This audit is a diagnostic. Its purpose is to make the next architectural
decisions safe, reversible, and defensible.*
