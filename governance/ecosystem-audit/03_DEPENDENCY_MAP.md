# 03 — Ecosystem Dependency Map

> This map is built from three evidence sources:
> (1) explicit cross-references I could read in the Portfolio,
> (2) semantic relationships implied by descriptions, topics, and target-architecture roles,
> (3) external platform links declared in Portfolio metadata (Zenodo, ORCID, GitHub Pages, SSRN, OpenAIRE).
>
> Cross-repository code dependencies (imports, submodules, git subtrees) could
> not be verified from search-API metadata alone; verification requires cloning
> each repo. That check is scheduled as part of Phase 3 pre-migration
> validation and is called out where relevant.

---

## 1. Diagram — target-state dependency graph

Legend: `[A] --uses--> [B]`  means A depends on B. `[A] ==publishes==> [B]`
means A produces canonical content that lives in B.

```
                     ┌──────────────────────────────────────┐
                     │  judicial-data-ai-governance-        │
                     │   portfolio (Core Research)          │
                     │  — vision, strategy, working papers, │
                     │    frameworks docs, roadmaps         │
                     └──────────────────────────────────────┘
                        │             │             │
              cites     │             │  cites      │  cites
                        ▼             ▼             ▼
        ┌───────────────────┐  ┌──────────────┐  ┌──────────────────────┐
        │  JDGF Toolkit     │  │  Judicial    │  │  Living Digital      │
        │  (framework code) │  │  Statistics  │  │  Governance Platform │
        └───────────────────┘  └──────────────┘  └──────────────────────┘
                    │
                    │  informs
                    ▼
        ┌───────────────────┐         ┌───────────────────────┐
        │   CS GREFFE OS    │◀────────│   CS GREFFE OS Cloud  │
        │   (registry OS)   │  extends│   (learning platform) │
        └───────────────────┘         └───────────────────────┘
                    ▲
                    │  automates research on
                    │
        ┌───────────────────┐
        │   Data Agents     │
        │   (AI toolkit)    │
        └───────────────────┘

    ┌────────────────┐    ┌───────────────────┐    ┌──────────────────────┐
    │  Monitor the   │    │   Playground      │    │  Personal Archive    │
    │   Reactor      │    │   (sandbox)       │    │   (private memory)   │
    │  (demo)        │    │                   │    │                      │
    └────────────────┘    └───────────────────┘    └──────────────────────┘

    ┌────────────────────────────────────────────────────────────────────┐
    │  lioneldyla profile — links out to all above; not depended on      │
    └────────────────────────────────────────────────────────────────────┘

    ┌────────────────────────────────────────────────────────────────────┐
    │  Le Wagon Archive (collection) ─── Legacy Projects (collection)    │
    │  — read-only history; nothing depends on them                      │
    └────────────────────────────────────────────────────────────────────┘
```

---

## 2. Explicit inbound / outbound references in the Portfolio

From the Portfolio (this repo) outward, extracted from the READMEs I read:

| From (Portfolio path) | Referenced repo / target | Type |
|---|---|---|
| `README.md` open-source projects table | *CS GREFFE OS* | Named plan |
| `README.md` open-source projects table | *AI PhD Agent* | Named plan (probable rename → `data-agents`) |
| `README.md` open-source projects table | *JDGF Toolkit* | Named plan (probable canonical → `jdgf-framework`) |
| `README.md` open-source projects table | *SPJEJ Platform* | Named plan — not yet a repo |
| `README.md` badges | `zenodo.org/badge/DOI/10.5281/zenodo.PENDING` | Zenodo DOI (pending) |
| `README.md` GitHub Pages badge | `https://lioneldyla.github.io/judicial-data-ai-governance-portfolio/` | Pages site |
| `README.md` ORCID badge | `https://orcid.org/0009-0007-3762-9792` | ORCID |
| `README.md` author section | `github.com/lioneldyla` | Profile |
| `README.md` author section | `linkedin.com/in/lioneldyla` | External |
| `CITATION.cff` | `github.com/lioneldyla/judicial-data-ai-governance-portfolio` | Self |
| `frameworks/JDGF/README.md` | `working_papers/WP01/` | Internal |
| `working_papers/WP01/README.md` | `frameworks/JDGF/` | Internal |
| `DOCTORAL_RESEARCH_PLAN.md` | `working_papers/WP01/`, `working_papers/WP02/`, `working_papers/WP03/`, `working_papers/WP04/`, `frameworks/JDGF/` | Internal |
| `docs/RESEARCH_PORTFOLIO_HANDBOOK.md` | The full docs/ tree | Internal |

Notably absent: the Portfolio does not explicitly link to
`jdgf-framework`, `judicial-statistics`, `monitor-the-reactor`,
`living-digital-governance-platform`, `cs-greffe-os*`, or `data-agents` as
GitHub URLs. All references are by conceptual name only.

**Implication for target architecture:** the Portfolio's `README.md` needs a
new *Ecosystem* section that lists sibling repos with their GitHub URLs, so
the whole graph is navigable from the entry point.

---

## 3. Inferred inbound references (need verification)

From what non-Portfolio repos likely reference:

| Repo | Likely inbound reference (to Portfolio) |
|---|---|
| jdgf-framework | Description implies "toolkit for governing data" — likely cites JDGF framework doc |
| JDGF-LAB-FRAMEWORK | Topic "judicial-data" + "data-governance" — likely cites Portfolio |
| judicial-statistics | Description mentions Ministry of Justice CI data — likely cites WP01 / SPJEJ methodology |
| living-digital-governance-platform | Description mirrors Portfolio phrasing — likely cites RESEARCH_MANIFESTO |
| working-papers | Description names Working Papers — near-certain duplicate of Portfolio/working_papers |
| monitor-the-reactor | Le Wagon capstone — probably does not cite Portfolio |
| lioneldyla (profile) | Profile README — probably lists all programme repos |

**Verification method for Phase 3:** clone each repo, grep for
`lioneldyla/judicial-data-ai-governance-portfolio`, `orcid.org/0009-0007-3762-9792`,
and the string "Judicial Data Governance Framework".

---

## 4. External platform dependencies

| Platform | Status | Repositories that link to it | Action for Phase 3 |
|---|---|---|---|
| ORCID `0009-0007-3762-9792` | Active | All programme repos (via CITATION.cff or README badge, expected) | Verify CITATION.cff exists in all |
| Zenodo | DOI pending | Portfolio declares `10.5281/zenodo.PENDING` | Register concept DOI, back-fill badge |
| SSRN | Profile pending | Portfolio references it | Create account, deposit WP01 |
| OpenAIRE | Referenced | Portfolio | Configure after Zenodo |
| GitHub Pages | Configured | Portfolio (`docs/`) | Verify build and deploy |
| DataCite (via Zenodo) | Automatic | Portfolio | Automatic once Zenodo is live |

---

## 5. Absent-but-expected dependencies

Things the current graph is **missing** that a coherent research infrastructure
should have:

| Missing edge | Why it matters | Fix |
|---|---|---|
| Portfolio → `jdgf-framework` explicit URL | The flagship framework is not linked from the flagship portfolio | Add to Portfolio README + `frameworks/JDGF/README.md` |
| Portfolio → `judicial-statistics` explicit URL | Statistics is a stated Software Product; not linked | Add to Portfolio README + `software/README.md` |
| Portfolio → `living-digital-governance-platform` explicit URL | Platform layer not linked | Add cross-reference in RESEARCH_MANIFESTO |
| `jdgf-framework` → Portfolio doc | Framework should point back to conceptual reference | Add in framework repo's README |
| `monitor-the-reactor` → Portfolio | Demo should credit the portfolio it belongs to | Add in demo repo's README |
| A single CITATION.cff scheme across all programme repos | Discoverability | Standardize per Documentation Audit §7 |

---

## 6. Circular-dependency risks

None detected. The intended graph is a DAG rooted at the Portfolio.

The risk to watch during Phase 3 migration: if `working-papers` (standalone
repo) is folded into `judicial-data-ai-governance-portfolio/working_papers/`
with `git subtree add`, do so *before* deleting the standalone repo, and do
not create the reverse edge (Portfolio does not need to publish anything back
to `working-papers`).

---

*Update this map when a new programme repository is created or an existing
one is renamed.*
