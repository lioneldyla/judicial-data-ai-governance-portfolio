# 04 — Duplication Report

> Mission principle: *"Never duplicate documentation. Never duplicate
> production code."* This report enumerates suspected duplications with
> evidence and a proposed resolution. Every duplication is either
> **confirmed** (verified from files I read) or **suspected** (from name +
> description + topic overlap; requires Phase 3 grep-level verification).

---

## §1 — `jdgf-framework` vs `JDGF-LAB-FRAMEWORK` — **SUSPECTED**

| Field | jdgf-framework | JDGF-LAB-FRAMEWORK |
|---|---|---|
| Visibility | Public | Public |
| Description | *Judicial Data Governance Framework — Tools, methodology and maturity model for governing data in African judicial institutions* | *A modular governed framework for AI-assisted projects knowledge systems and data-governance research* |
| Topics | africa, data-governance, digital-transformation, judicial-systems, justice, public-sector, python, responsible-ai | ai-governance, data-governance, judicial-data, knowledge-systems, multi-agent, python, rag |
| Default branch | `main` | `codex/advanced-rag-contracts` (⚠️ non-`main` default is a smell) |
| Open issues | 0 | 4 |
| Created | 2026-06-23 | 2026-06-27 (4 days after the first) |

**Analysis.** The younger repo (`JDGF-LAB-FRAMEWORK`) reads more like a
technical lab exploring RAG + multi-agent scaffolding using the *JDGF*
branding, while the older repo (`jdgf-framework`) reads like the canonical
methodology framework aligned with the Portfolio's `frameworks/JDGF/`.

**Portfolio evidence.** The Portfolio's `README.md` names *"JDGF Toolkit"* in
the Open-Source Projects table. Only one repo can hold that title.

**Proposed resolution.**

1. Keep `jdgf-framework` as the canonical **Framework** (rename to
   `jdgf-toolkit` to match the Portfolio's stated name).
2. Reclassify `JDGF-LAB-FRAMEWORK` as an internal R&D sandbox → rename to
   `jdgf-lab` (drop `-FRAMEWORK`) or fold its RAG/multi-agent work into
   `data-agents`. Add an archival-pointer README explaining the split.
3. Move its 4 open issues to `jdgf-toolkit` or `data-agents` before archiving.

**Blocker.** Need user confirmation of the canonical intent.

---

## §2 — `cs-greffe-os` vs `cs-greffe-os-v2` vs `cs-greffe-os-cloud` — **SUSPECTED**

| Field | cs-greffe-os | cs-greffe-os-v2 | cs-greffe-os-cloud |
|---|---|---|---|
| Visibility | Private | Public | Private |
| Description | *(none)* | *(none)* | *CS GREFFE OS Learn - prototype cloud e-learning* |
| Created | 2026-06-14 | 2026-07-01 | 2026-06-14 |
| Language | — | Python | Python |
| Default branch | `main` | `main` | `main` |

**Analysis.** Standard v1→v2 refactor pattern:

- v1 (private) was the first attempt.
- v2 (public) is the next iteration; being public suggests it will become the canonical product.
- `cs-greffe-os-cloud` is a distinct product (e-learning wrapper) — likely not a duplicate but a companion.

**Portfolio evidence.** The Portfolio names only "CS GREFFE OS" and
"CS GREFFE OS Cloud" — no "v2". The v2/v1 naming should not survive into the
target architecture; the canonical repo should simply be named `cs-greffe-os`.

**Proposed resolution.**

1. Confirm `cs-greffe-os-v2` is the canonical product going forward.
2. Rename `cs-greffe-os-v2` → `cs-greffe-os-next` briefly, then archive
   the old `cs-greffe-os` (private), then rename the new one to
   `cs-greffe-os`. Two-step to avoid a name-collision race on GitHub.
3. Keep `cs-greffe-os-cloud` as-is.

**Blocker.** Need user confirmation of which repo is canonical, and whether
old-`cs-greffe-os` history should be preserved via `git filter-repo` merge.

---

## §3 — `working-papers` repository vs `judicial-data-ai-governance-portfolio/working_papers/` — **SUSPECTED (high confidence)**

| Field | working-papers (repo) | Portfolio working_papers/ |
|---|---|---|
| Description | *Working Papers on Judicial Data Governance & Responsible AI — Lionel Dyla* | Sub-directory containing WP01 and WP02 |
| Created | 2026-06-23 | (part of Portfolio, WP01 pre-existing) |
| Visibility | Public | Public (parent) |

**Analysis.** These almost certainly overlap. A standalone `working-papers`
repo predates the Portfolio's decision to host working papers internally.
The mission's Portfolio Rules explicitly say the Portfolio contains
*"Working Papers, White Papers, Framework documentation, Research Notes,
Publications, Datasets, Citation assets, Roadmaps, Strategic documentation"*.

**Proposed resolution.**

1. Clone `working-papers` and diff its contents against
   `judicial-data-ai-governance-portfolio/working_papers/`.
2. If subset or duplicate → archive `working-papers` with a README pointing
   at the Portfolio.
3. If it contains unique WPs → migrate the unique content into the Portfolio
   (`git subtree add`), then archive.

**Blocker.** Cannot inspect standalone repo without adding it to session
scope.

---

## §4 — `personal-branding` vs `lioneldyla` (profile) — **SUSPECTED**

| Field | lioneldyla | personal-branding |
|---|---|---|
| Description | *Judicial Data & AI Governance Architect \| Data Governance · Digital Justice · Responsible AI* | *Building an international academic and professional identity in Judicial Data Governance, Digital Justice and Responsible AI.* |
| Visibility | Public | Public |
| Created | 2026-06-23 | 2026-06-30 |

**Analysis.** GitHub renders the `lioneldyla/lioneldyla` repo's README as the
account's profile page. A separate `personal-branding` repo cannot serve
that function. The `personal-branding` repo appears to be a
communication-strategy workspace (LinkedIn plans, CV, bios) rather than a
GitHub-facing profile.

**Proposed resolution.**

- Keep `lioneldyla` as **Profile** (target arch).
- Reclassify `personal-branding` as either (a) private branding workspace →
  make private, or (b) fold its content into the `personal-archive` repo.
- If kept, the two must not share README content — `personal-branding`
  should hold strategy assets, `lioneldyla` should hold public identity.

**Blocker.** User decision on whether to keep the branding workspace public.

---

## §5 — Internal Portfolio duplication — **CONFIRMED (minor)**

Within `judicial-data-ai-governance-portfolio` itself:

| Duplicate | Files |
|---|---|
| Two "audit reports" | `AUDIT_REPORT.md` (9.1 KB) and `REPOSITORY_AUDIT.md` (9.1 KB) |
| Two "improvement plans" | `IMPROVEMENT_PLAN.md` (4.9 KB) and `REPOSITORY_IMPROVEMENT_PLAN.md` (6.2 KB) |

Both pairs cover the same subject (repository audit / improvement plan)
from prior modernization runs. They are not identical files but their
purpose overlaps.

**Proposed resolution.**

Once this ecosystem-audit deliverable is accepted, consolidate:

- Retire `AUDIT_REPORT.md` and `IMPROVEMENT_PLAN.md` (the shorter, older ones).
- Keep `REPOSITORY_AUDIT.md` and `REPOSITORY_IMPROVEMENT_PLAN.md` as
  historical records of the *v1.x* audit; move both into
  `governance/history/` and add a note pointing at this new audit.
- All future audits live under `governance/ecosystem-audit/` following
  the pattern established here.

---

## §6 — `Playground` vs `blank-app-1` — **CONFIRMED (semantic duplicate)**

Both public. Both empty-scaffold. Target architecture names only *Playground*.

**Proposed resolution.** Delete `blank-app-1` (nothing to preserve) or fold
its scaffold into `Playground/streamlit-starter/`.

---

## §7 — Le Wagon exercises inside the Portfolio? — **NOT DETECTED**

I checked the Portfolio's `software/` and `research_notes/` directories and
found no Le Wagon code or notebooks inside. The Le Wagon body of work is
cleanly isolated to the standalone repositories. Good.

---

## Summary of confirmed vs suspected duplications

| # | Duplication | Status | Resolution blocker |
|---|---|---|---|
| §1 | JDGF x 2 repos | Suspected | User decision (which is canonical) |
| §2 | CS GREFFE OS v1/v2/cloud | Suspected | User decision (which is canonical) |
| §3 | working-papers repo vs Portfolio | Suspected (high confidence) | Clone + diff |
| §4 | personal-branding vs profile | Suspected | User decision |
| §5 | Portfolio internal audit files | **Confirmed** | None — safe to consolidate now |
| §6 | Playground vs blank-app-1 | **Confirmed** | None — safe to delete |
| §7 | Le Wagon inside Portfolio | Not detected | — |

Nothing in this report authorizes a delete. All items require user
confirmation OR a Phase-3 clone-and-diff step, per the mission rule
*"Archive before deleting."*
