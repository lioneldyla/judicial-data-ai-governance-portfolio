# 05 — Migration Plan

> Sequenced, reversible plan to move the ecosystem from current state to
> target state without losing Git history and without destructive actions
> before verification.
>
> **Principle:** every repo transition is either (a) *rename in place*,
> (b) *archive with README pointer*, (c) *migrate content via `git subtree`*,
> or (d) *delete only after archive + Zenodo capture*.

---

## Phasing

| Phase | Nature | Reversible? | Approval gate |
|---|---|---|---|
| 0 | This audit (documentation only) | Yes | — |
| 1 | Pre-migration verification (clone, diff, grep) | Yes | — |
| 2 | Metadata standardization (descriptions, topics, homepage, license, badges) | Yes (metadata edit) | User |
| 3 | Documentation standardization (add AGENTS.md, PROJECT_STATUS.md, ARCHITECTURE.md, CITATION.cff to every active repo) | Yes (net-add of files) | User |
| 4 | Renames (single-hop, GitHub keeps redirects) | Reversible for 90 days | User |
| 5 | Content migrations (git subtree adds) | Yes | User |
| 6 | Archival (`archived: true` flag + README banner) | Reversible (un-archive) | User |
| 7 | Deletions (only after Zenodo snapshot for public repos) | **Irreversible** | User, per-repo |

---

## Phase 1 — Verification checklist (no changes)

For each of the ~19 non-Le-Wagon repos:

- [ ] Add repo to session scope (`add_repo`)
- [ ] Clone to a workspace
- [ ] `git log --oneline | wc -l` — capture commit count as history-preservation baseline
- [ ] Grep for `lioneldyla/judicial-data-ai-governance-portfolio` — capture inbound references
- [ ] Read root README and any AGENTS.md, PROJECT_STATUS.md, ARCHITECTURE.md
- [ ] Compare content against Portfolio for duplication candidates (§3, §4 of the Duplication Report)
- [ ] Record findings in a new file `governance/ecosystem-audit/verification/<repo>.md`

Deliverable of Phase 1: a `verification/` sub-directory with one file per
programme repo, each answering: *"what is this? what does it depend on?
what depends on it? what should happen to it?"*

For the ~87 Le Wagon repos: sample 5, confirm they follow the Le Wagon
scaffold, then bulk-classify. Do not clone all 87.

---

## Phase 2 — Metadata standardization (per-repo)

Standard applied to every **active** repo. Applies to metadata only, not
files; failure to save is a no-op.

| Field | Value / rule |
|---|---|
| Description | ≤160 chars, sentence case, ends without period. Names the mission, not the tech. |
| Topics | 4–8 topics, lowercase-kebab, at least one geographical (`africa`, `cote-divoire`) and one thematic (`data-governance`, `digital-justice`, `responsible-ai`) |
| Homepage | Portfolio for research repos; deployed app URL for software; blank for archives |
| License | CC-BY-4.0 for research/docs; MIT for software; specified in `LICENSE` file at root |
| Default branch | `main` (rename any `master` → `main`) |
| README badge row | ORCID, License, Programme, Portfolio-link, DOI (where applicable) |

Per-repo overrides live in **07_METADATA_AUDIT.md**.

---

## Phase 3 — Documentation standardization (per-repo)

Every active repo gets, at minimum, the seven files below. Templates are
listed in **06_DOCUMENTATION_AUDIT.md**.

- `README.md` (upgraded, badge row, ecosystem section)
- `AGENTS.md` (mission, scope, coding standards, prohibited actions, branching, release policy, relationships)
- `PROJECT_STATUS.md` (completed / current / open issues / pending / next)
- `ROADMAP.md` (short and long horizon)
- `ARCHITECTURE.md` (organization + inbound/outbound deps)
- `CHANGELOG.md` (Keep-a-Changelog)
- `CITATION.cff` (author, ORCID, license)

Community files (`CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`,
`LICENSE`) already exist in the Portfolio and are cloned into other public
repos (adapted per-repo).

---

## Phase 4 — Renames

Executed via GitHub Settings → Rename (creates automatic redirect for
90 days; safe).

| From | To | Reason |
|---|---|---|
| `JDGF-LAB-FRAMEWORK` | `jdgf-lab` **or** archive | Name collision with `jdgf-framework`; drop `-FRAMEWORK` suffix. Only if kept as active R&D lab |
| `jdgf-framework` | `jdgf-toolkit` | Portfolio names it "JDGF Toolkit" everywhere; align |
| `cs-greffe-os-v2` | `cs-greffe-os` (after archiving v1) | Drop version suffix from active product |
| `cs-greffe-os` | `cs-greffe-os-v1` (then archive) | Free up canonical name for v2 |
| `data-agents` | `data-agents-toolkit` **or** `judicial-ai-agents` | Disambiguate from Le Wagon `data-*` archive |
| `Playground` | `playground` | Match kebab-case convention across account |
| `Leken.ci` | `leken-ci` **or** move under a dedicated domain | Drop dot in name (not portable) — pending decision |
| Le Wagon `data-*` repos on `master` default | rename default branch to `main` | Convention alignment before archiving |

Renames are cheap and reversible for 90 days on GitHub. Do them
**before** content migrations so the new URLs are the ones baked into
migrated cross-references.

---

## Phase 5 — Content migrations

Each migration is a `git subtree add` (or `git filter-repo --to-subdirectory-filter`
if history rewriting is desired) that preserves the full commit history of
the source repo inside the destination repo.

| Source | Destination | Path in destination | Migration command sketch |
|---|---|---|---|
| `working-papers` | `judicial-data-ai-governance-portfolio` | `working_papers/` (merge unique WPs) | `git remote add wp git@github.com:lioneldyla/working-papers.git && git subtree add --prefix=working_papers wp main --squash=NO` |
| `personal-branding` (if merging) | `personal-archive` | `branding/` | Same pattern |
| Optional: canonical Le Wagon exercises worth preserving as portfolio pieces | dedicated repo per piece | root | Extract from Le Wagon Archive |

Never migrate in the reverse direction: content leaves the Portfolio only if
it is out-of-scope per the Portfolio Rules (which forbid production
software inside the Portfolio — none currently violates this).

---

## Phase 6 — Archival

The mission's *Archive Policy* is: repositories that have been superseded
should be **archived** rather than deleted. Archival keeps them read-only
in place with a banner README explaining why.

### 6.1 Standard archival README template

```markdown
# [Repo Name] — Archived

**Archived on:** YYYY-MM-DD
**Reason:** [Concise reason — one sentence]
**Replacement:** [Link to canonical repo, e.g. `jdgf-toolkit`]
**Migration status:** [Complete / Partial / N/A]
**Preserved for:** [History / Reference / Reproducibility]

This repository is preserved as read-only. All active development has moved
to the replacement above. Issues and PRs are disabled.

For context, see the ecosystem audit:
https://github.com/lioneldyla/judicial-data-ai-governance-portfolio/tree/main/governance/ecosystem-audit
```

### 6.2 Archival batches

| Batch | Repos | Timing |
|---|---|---|
| B1 — Superseded programme repos | `JDGF-LAB-FRAMEWORK` (if not canonical), `cs-greffe-os-v1` (old private), `working-papers` (after content migration), `blank-app-1`, `personal-branding` (if merged) | After Phase 4-5 |
| B2 — GitHub tutorial residue | `desktop-tutorial`, `skills-introduction-to-github` | After Phase 4 |
| B3 — Le Wagon exercises (all 87) | Every `data-*` repo + `taxifare-website` | After Phase 4 |
| B4 — Website side-projects | `Leken.ci` (unless promoted) | After user decision |

### 6.3 Alternative for Le Wagon: consolidation

Instead of archiving 87 individual repos, an alternative is:

1. Create one new repo `le-wagon-archive` (public or private per user preference).
2. `git subtree add --prefix=exercises/<slug>` each of the 87 repos into it.
3. Add a top-level README indexing the exercises.
4. Delete the 87 originals (only after the consolidation is verified and the
   history is preserved in the monorepo).

**Trade-off.** GitHub archival flag is cheaper but keeps 87 tiles on the
account. Consolidation is one-time work but leaves a single tidy repo.
Recommendation: **consolidate** — the account gains cleanliness, and the
work is proportional to the reorganization mission.

---

## Phase 7 — Deletions

Only performed after:

1. Content is preserved elsewhere (archive, monorepo, or Zenodo snapshot).
2. Duplicate detection has confirmed no unique content is lost.
3. User has approved per-repo.
4. A dated backup tag is pushed to the source repo before deletion.

Recommended deletion candidates *after archival capture*:

- `desktop-tutorial` (auto-generated onboarding; zero unique value)
- `blank-app-1` (empty template)
- Duplicate Le Wagon repos after consolidation into `le-wagon-archive`

---

## Rollback strategy

- Renames: reversible for 90 days via GitHub redirect.
- Archival: reversible immediately (un-archive flag).
- Content migrations: reversible if source repo is not yet deleted.
- Deletions: only via GitHub restore within 90 days; else via Zenodo
  snapshot (irreversible loss of Git graph but content is preserved).

The plan is designed so that any user-approved change up to and including
Phase 6 can be reversed in a single session.

---

## Estimated effort

| Phase | Effort | Ownership |
|---|---|---|
| 1 — Verification | 1 session (agent-heavy) | Agent |
| 2 — Metadata | 1 session | Agent + user metadata review |
| 3 — Documentation | 2–3 sessions (per-repo scaffolding) | Agent |
| 4 — Renames | 1 hour (GitHub UI or `gh` calls) | User (or agent with approval) |
| 5 — Content migrations | 1 session per migration | Agent |
| 6 — Archival | Bulk operation, 1 session | Agent |
| 7 — Deletions | Per-repo, user approval each | User |

Total realistic timeline: **4–6 focused sessions** spread across 1–2 weeks.
