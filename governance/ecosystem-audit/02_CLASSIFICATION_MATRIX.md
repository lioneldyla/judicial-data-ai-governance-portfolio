# 02 — Repository Classification Matrix

> Each repository is assigned **one** category, per mission constraint
> "one repository = one mission". The category vocabulary is fixed by the
> mission brief: **Core Research · Framework · Software Product · Platform ·
> Library · Dataset · Demonstration · Archive · Sandbox · Legacy · Profile**
> (Profile added because the target architecture explicitly lists it).

Where the assignment is ambiguous, the current-state category and a
proposed target-state category are both shown, and the ambiguity is flagged
in `04_DUPLICATION_REPORT.md`.

---

## Legend

| Symbol | Meaning |
|---|---|
| ✅ | Category is unambiguous |
| ⚠️ | Ambiguous — see notes column |
| 🔒 | Private repository |
| 🌐 | Public repository |

---

## Programme repositories

| Repo | Vis. | Current category | Target category | Notes |
|---|---|---|---|---|
| judicial-data-ai-governance-portfolio | 🌐 | Core Research | **Core Research** ✅ | The academic hub; already scoped correctly |
| jdgf-framework | 🌐 | Framework | **Framework** ⚠️ | Conflicts with `JDGF-LAB-FRAMEWORK`. See dup report §1. Target name: `jdgf-toolkit` |
| JDGF-LAB-FRAMEWORK | 🌐 | Framework | **Framework or Archive** ⚠️ | If not the canonical JDGF, archive with pointer to canonical |
| living-digital-governance-platform | 🌐 | Platform | **Platform** ✅ | Matches target arch item "Living Digital Governance Platform" |
| judicial-statistics | 🌐 | Software Product | **Software Product** ✅ | Matches target arch item "Judicial Statistics" |
| cs-greffe-os | 🔒 | Software Product | **Software Product** ⚠️ | Which of v1/v2 is canonical? See dup report §2 |
| cs-greffe-os-v2 | 🌐 | Software Product | **Software Product** ⚠️ | Public v2; supersedes v1? |
| cs-greffe-os-cloud | 🔒 | Software Product | **Software Product** ✅ | Cloud e-learning companion; distinct product |
| data-agents | 🔒 | Software Product (AI) | **Software Product** ⚠️ | Rename to `data-agents-toolkit` to avoid confusion with the ~87 Le Wagon `data-*` repos |
| monitor-the-reactor | 🌐 | Demonstration | **Demonstration** ✅ | Le Wagon capstone; legitimate portfolio piece — do not archive with the bulk Le Wagon set |
| working-papers | 🌐 | ⚠️ Unclear | **Archive** ⚠️ | Overlaps with `judicial-data-ai-governance-portfolio/working_papers/`. See dup report §3 |
| lioneldyla | 🌐 | Profile | **Profile** ✅ | GitHub profile README — target arch matches |
| personal-branding | 🌐 | Profile / Documentation | **Archive or merge into `lioneldyla`** ⚠️ | Semantically overlaps with the profile repo. See dup report §4 |
| personal-archive | 🔒 | Archive | **Archive** ✅ | Matches target arch item "Personal Archive" |

## Sandbox & experiments

| Repo | Vis. | Current | Target | Notes |
|---|---|---|---|---|
| Playground | 🌐 | Sandbox | **Sandbox** ✅ | Matches target arch item "Playground" |
| blank-app-1 | 🌐 | Sandbox | **Sandbox** (merge into `Playground`) | Streamlit blank-app scaffold |

## Website / branding side-projects

| Repo | Vis. | Current | Target | Notes |
|---|---|---|---|---|
| Leken.ci | 🔒 | Unknown | **⚠️ Requires user decision** | Purpose not evident from metadata |
| taxifare-website | 🔒 | Software Product (Le Wagon MVP) | **Legacy** (merge into Le Wagon Archive) | |

## GitHub onboarding

| Repo | Vis. | Current | Target | Notes |
|---|---|---|---|---|
| desktop-tutorial | 🔒 | Legacy | **Legacy** ✅ | GitHub Desktop auto-generated; archive or delete |
| skills-introduction-to-github | 🌐 | Legacy | **Legacy** ✅ | GitHub Skills course clone; 1 open issue — close and archive |

## Le Wagon Data Science bootcamp (87 repos)

Bulk classification. Each private, each an exercise slug, each part of the
Batch 2149 (Le Wagon Data Science & AI, Oct–Dec 2025).

| Repo pattern | Vis. | Current | Target |
|---|---|---|---|
| `data-*` (85 pedagogical exercises) | 🔒 | Legacy | **Le Wagon Archive** |
| `data-playground`, `data-playground-part-ii` | 🔒 | Legacy | **Le Wagon Archive** (not to be confused with `Playground`) |
| `data-check`, `data-git`, `data-notebook`, `data-context-and-setup` (bootcamp setup) | 🔒 | Legacy | **Le Wagon Archive** |

Selection of noteworthy Le Wagon repos worth surfacing individually rather
than bulk-archiving (candidate demonstration pieces):

- `data-olist` / `data-olist_ceo_request` / `data-olist_nps` — CEO-request customer analytics
- `data-classify-electrocardiograms` — Medical ML classification
- `data-rag-with-langchain` — RAG pipeline
- `data-agents` (already elevated) — Multi-agent framework
- `data-transformer-finetuning-challenge` — Transformer fine-tuning

Recommendation: leave in the Le Wagon Archive; if any becomes a portfolio
piece, extract to its own repo with a new name (never re-purpose the
Le Wagon slug).

---

## Category count summary

| Category | Count |
|---|---:|
| Core Research | 1 |
| Framework | 1–2 (depending on JDGF decision) |
| Platform | 1 |
| Software Product | 4–5 |
| Library | 0 |
| Dataset | 0 (planned within Core Research) |
| Demonstration | 1 |
| Archive | 2 |
| Sandbox | 1 (after merging blank-app-1) |
| Legacy / Le Wagon Archive | ~87 |
| Profile | 1 |
| Unknown / needs decision | 1 (Leken.ci) |

---

*Classifications marked ⚠️ block Phase 3 execution. Resolutions are proposed
in `05_MIGRATION_PLAN.md` and `10_ARCHITECTURE_BLUEPRINT.md`.*
