# 09 — Archive Plan

> Mission policy: *"Repositories that have been superseded should be
> archived rather than deleted whenever historical value exists. Every
> archived repository must contain a README indicating: reason for
> archival; replacement repository; migration status; archival date."*
>
> This plan defines which repos are archive-bound, when, using what
> mechanism, and with what archival README.

---

## Archival mechanism options

| Option | Where content lives | When to use |
|---|---|---|
| **A. GitHub `archived: true` flag** | In place; repo is read-only | For repositories whose Git history is worth preserving in situ (external DOI, prior citations, open-source community) |
| **B. Consolidation into monorepo** | New repo, `git subtree add` per source | For clusters of small repos with a common origin (Le Wagon exercises) |
| **C. Zenodo capture then delete** | Zenodo DOI; GitHub deleted | For repositories whose GitHub presence adds noise but content should be citeable |
| **D. Merge into another repo, then delete source** | Absorbed into a larger sibling | For duplicate content (working-papers → Portfolio) |

Each archival batch below specifies its option.

---

## Archival batches

### B1 — Superseded programme repos (Option A: GitHub flag OR D: merge)

| Repo | Option | Rationale |
|---|---|---|
| `cs-greffe-os-v1` (renamed from `cs-greffe-os`) | A | Preserve for history; replaced by public `cs-greffe-os` (formerly `-v2`) |
| `JDGF-LAB-FRAMEWORK` (if not canonical) | A | Preserve open issues; replaced by `jdgf-lab` (rename) or `jdgf-toolkit` |
| `working-papers` | D | Fold unique WPs into Portfolio, then archive |
| `blank-app-1` | Delete | Empty template, no history |
| `personal-branding` (if merged) | D | Fold into Portfolio's academic_profiles/ or into personal-archive/ |

### B2 — GitHub tutorial residue (Option A + delete for duplicates)

| Repo | Option | Rationale |
|---|---|---|
| `desktop-tutorial` | Delete | Auto-generated onboarding; zero unique value |
| `skills-introduction-to-github` | A | Course participation record; low harm to keep archived, easy to delete later |

### B3 — Le Wagon exercises (~87 repos) (Option B: consolidation, recommended)

**Recommended.** Consolidate into a single `le-wagon-archive` repo. Reasons:

- Cleans the account front-page.
- Preserves each exercise's Git history via `git subtree add`.
- One README indexes all exercises.
- One archival flag then applies to the whole batch.

Structure of the new monorepo:

```
le-wagon-archive/
├── README.md          — batch summary + exercise index
├── AGENTS.md          — mission = "read-only bootcamp archive; do not extend"
├── LICENSE            — MIT
├── exercises/
│   ├── 01-fundamentals/
│   │   ├── data-notebook/
│   │   ├── data-numpy/
│   │   └── ...
│   ├── 02-data-analysis/
│   │   └── ...
│   ├── 03-decision-science/
│   │   └── ...
│   ├── 04-ml/
│   │   └── ...
│   ├── 05-deep-learning/
│   │   └── ...
│   └── 06-mlops/
│       └── ...
└── capstone/
    └── (link out to monitor-the-reactor — that stays a separate repo)
```

Effort: ~1 focused session for the batch subtree operation + README.

**Alternative.** Bulk-archive in place using Option A: cheaper but leaves
87 tiles cluttering the account. Not recommended.

### B4 — Website side-projects (User decision)

| Repo | Option | Rationale |
|---|---|---|
| `Leken.ci` (renamed `leken-ci`) | ⚠️ Pending | Unknown purpose |
| `taxifare-website` | B | Fold into `le-wagon-archive/exercises/06-mlops/taxifare-website/` |

---

## Archival README template

Every archived repo (Option A) gets its README overwritten with this
template. The original README is preserved as `README_ORIGINAL.md`.

```markdown
# <Repo Name> — Archived

> This repository is preserved as read-only. It is no longer maintained.

| Field | Value |
|---|---|
| **Archival date** | YYYY-MM-DD |
| **Reason** | [Superseded / Consolidated / Educational scaffolding / Discontinued] |
| **Replacement** | [Link to canonical repo, or "None — closed permanently"] |
| **Migration status** | [Complete / Partial / Content preserved elsewhere / N/A] |
| **Preserved for** | [History / Reference / Reproducibility / DOI stability] |
| **Related audit** | [`governance/ecosystem-audit/`](https://github.com/lioneldyla/judicial-data-ai-governance-portfolio/tree/main/governance/ecosystem-audit) |

## Why is this archived?

<One paragraph explaining the decision in prose.>

## Where should new work go?

<Explicit URL of the replacement repo, or "n/a".>

## Content preservation

- Git history: preserved in place.
- (Optionally) Zenodo snapshot DOI: `10.5281/zenodo.XXXXXXX`

## Original README

The original README is available at [`README_ORIGINAL.md`](./README_ORIGINAL.md).

---

*This archival README is generated per the ecosystem audit archive policy.
Do not edit; changes to policy live in the audit.*
```

---

## Pre-archival checklist (per repo)

Before flipping the `archived: true` flag:

- [ ] Snapshot the current README as `README_ORIGINAL.md`
- [ ] Write the archival README from the template
- [ ] Close all open issues with a comment linking to the replacement
- [ ] Close all open PRs with a comment linking to the replacement
- [ ] Tag the current HEAD as `archive/YYYY-MM-DD`
- [ ] If public and citeable: push to Zenodo for DOI (via the Zenodo–GitHub webhook)
- [ ] Verify no active CI is running
- [ ] Verify the repo is not a Git dependency of another active repo
- [ ] Enable the `archived` flag in GitHub settings

---

## Post-archival monitoring

- Quarterly, list archived repos and confirm each is still referenced
  correctly from the Portfolio's ecosystem section.
- Annually, review whether any archived repo should be **restored to
  active** (if the research direction has changed) or **deleted** (if the
  content has been fully absorbed elsewhere).

---

## What is *never* archived

- The Portfolio (`judicial-data-ai-governance-portfolio`) — this is the
  DAG root of the ecosystem.
- Any repo currently backing a DOI (unless it has been formally
  superseded and a redirect is in place).
- Any repo referenced by an active publication.
