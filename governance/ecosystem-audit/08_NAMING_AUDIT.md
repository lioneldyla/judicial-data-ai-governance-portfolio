# 08 — Naming Audit

> Names are cheap to fix now and costly to fix later once external links,
> DOIs, and citations accumulate. This audit standardizes repository names,
> branch names, and file-level naming across the ecosystem.

---

## Standards

### Repository names

- **Case:** kebab-case (`jdgf-toolkit`), not PascalCase, not snake_case, not mixed.
- **Length:** ≤ 40 chars, preferably ≤ 30.
- **Prefixes:** avoid ecosystem-wide prefixes (Le Wagon's `data-*` polluted the account). Use suffixes for variants (`-cloud`, `-lab`).
- **Special chars:** letters, digits, hyphen only. No dots.
- **Language:** English, unless the artefact is language-specific.
- **Numbers/versions:** never `-v2` in the canonical name — that's a source of the CS GREFFE OS confusion. Use SemVer tags for versions, and only include a suffix when the fork is materially distinct (e.g., `-cloud`, `-lab`, `-mobile`).

### Branch names

- Default: `main`. Never `master` on any active repo.
- Feature: `feature/<slug>` or `<user>/<slug>` (e.g., the current `claude/github-ecosystem-audit-117kak`).
- Docs: `docs/<slug>`.
- Fixes: `fix/<slug>`.
- Never a randomly-named default branch (e.g., `codex/advanced-rag-contracts` should not be default).

### File names inside repositories

- **Root governance files:** `SCREAMING_SNAKE_CASE.md` (`README.md`, `CHANGELOG.md`, `RESEARCH_MANIFESTO.md`).
- **Documentation files under `docs/`:** lowercase, hyphen-separated (`architecture-overview.md`).
- **Working paper directories:** `WP01`, `WP02` (numeric, two-digit, uppercase prefix).
- **Framework directories:** uppercase acronym (`JDGF/`, `SPJEJ/`).
- **Software subdirectories in a monorepo:** kebab-case (`registry-core/`, `dashboard-web/`).
- **Assets:** `<category>_<description>_v<n>.<ext>` (already documented in the Portfolio's handbook).

### CITATION.cff naming

Always `CITATION.cff` at repo root (case-sensitive).

---

## Findings

### Repository naming violations

| Repo | Issue | Fix |
|---|---|---|
| `JDGF-LAB-FRAMEWORK` | Uppercase + hyphenated suffix `-FRAMEWORK` | Rename → `jdgf-lab` (kebab, no redundant suffix) |
| `Playground` | PascalCase | Rename → `playground` |
| `Leken.ci` | Contains `.` | Rename → `leken-ci` (or move under a dedicated domain) |
| `cs-greffe-os-v2` | Version in canonical name | Rename → `cs-greffe-os` (after archival of v1) |
| `data-agents` | Collides semantically with the ~87 Le Wagon `data-*` archive | Rename → `judicial-ai-agents` or `data-agents-toolkit` |
| `blank-app-1` | Numeric suffix, no mission | Delete or rename → `streamlit-starter` (if kept) |
| `desktop-tutorial` | Auto-generated placeholder | Delete; unrecoverable naming |
| `skills-introduction-to-github` | Course-fixture name | Archive; do not rename |
| `jdgf-framework` | Correct kebab; but "framework" is broader than what the Portfolio names ("JDGF Toolkit") | Rename → `jdgf-toolkit` for consistency with Portfolio README |

### Branch naming violations

| Repo | Default branch | Fix |
|---|---|---|
| `JDGF-LAB-FRAMEWORK` | `codex/advanced-rag-contracts` | Set to `main`; if `main` doesn't exist, create it from the working tip |
| ~half of Le Wagon `data-*` repos | `master` | Rename `master` → `main` (Git command + GitHub setting) |
| `data-preprocessor-tuning` | `master` | Same |
| `data-workflow` | `master` | Same |
| … (see 01_REPOSITORY_INVENTORY §E) | | |

### Prefix pollution

The `data-*` prefix, adopted from Le Wagon's bootcamp scaffolds, is
pattern-matched by GitHub search and appears in every "recently updated"
list. Consolidating the 87 exercises into a single `le-wagon-archive` repo
removes the pollution in one operation. That is the single highest-value
naming action available.

### File naming inside the Portfolio

Confirmed clean. Root files are `SCREAMING_SNAKE_CASE`. Working papers use
`WP01`, `WP02`. Framework directory uses `JDGF/`.

One minor inconsistency: `RESEARCH_STRATEGY_2026-2035.md` uses a hyphen in
its year range while the rest of the file uses underscores. Handbook
explicitly declares this acceptable ("hyphen in year range"). No change
needed.

---

## Rename sequencing

Renames must be executed in an order that avoids name collisions on GitHub.

```
Step 1: Rename cs-greffe-os → cs-greffe-os-v1
Step 2: Rename cs-greffe-os-v2 → cs-greffe-os
Step 3: Archive cs-greffe-os-v1

Step 4: Rename jdgf-framework → jdgf-toolkit  (redirect for 90 days)
Step 5: Rename JDGF-LAB-FRAMEWORK → jdgf-lab   (redirect for 90 days)

Step 6: Rename Playground → playground
Step 7: Rename Leken.ci → leken-ci (or delete if superseded)
Step 8: Rename data-agents → judicial-ai-agents (or data-agents-toolkit)
```

Every rename creates a GitHub redirect that lasts 90 days — long enough to
update external references (LinkedIn, publications, CVs). Track those
external references in `governance/ecosystem-audit/verification/external-references.md`
during Phase 1.

---

## Post-rename validation checklist

After each rename:

- [ ] Confirm redirect works: `git remote get-url origin` still resolves
- [ ] Update the Portfolio's `README.md` ecosystem section
- [ ] Update `CITATION.cff` `repository-code:` field
- [ ] Update all cross-references in Portfolio docs
- [ ] Update Zenodo metadata (if the repo has a Zenodo release)
- [ ] Update ORCID entry (if the repo is listed as a work)
- [ ] Update LinkedIn / CV references
- [ ] Post to any project boards / issues that reference the old URL
