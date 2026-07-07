# WP01 — Release Checklist

| Field | Value |
|---|---|
| Reference | WP01 |
| Date | 2026-07-07 |
| Related | [`VERSION.md`](VERSION.md), [`CHANGELOG.md`](CHANGELOG.md), [`CITATION.cff`](CITATION.cff), [`METADATA.yml`](METADATA.yml) |

---

## When to release

A release is a **Git-tagged commit** that Zenodo (via the GitHub webhook)
captures as a version DOI. Each release should be at a defensible
stopping point — package v1.0, first drafted sections, preprint,
version-of-record, journal submission — not at every commit.

Milestone plan (see [`VERSION.md`](VERSION.md)):

| Tag | Meaning | Typical trigger |
|---|---|---|
| `wp01-v0.1-package` | Publication package landed, manuscript not drafted | Now |
| `wp01-v0.5-draft` | §1 Introduction + §2 Conceptual Foundations drafted | Q3 2026 |
| `wp01-v0.8-preprint` | §1–§6 drafted, references verified | Q3–Q4 2026 |
| `wp01-v1.0-manuscript` | §1–§8 complete, peer feedback incorporated | Q4 2026 |
| `wp01-v2.0-journal` | Converted to journal style, submitted | Q1 2027 |

---

## Pre-release checklist (repeat for every tag)

Before creating the tag:

### 1. Manuscript consistency

- [ ] `WP01.md` has no `[TO BE DRAFTED BY THE AUTHOR]` markers, OR the release-notes explicitly identify the outline sections that remain
- [ ] Every `[TO BE DRAFTED]` marker replaced in the current release either has real prose or is explicitly deferred in `CHANGELOG.md`
- [ ] `WP01.md` §Abstract is byte-identical to `ABSTRACT.md` content
- [ ] `WP01.md` §Keywords match `KEYWORDS.md` primary keywords

### 2. Bibliography consistency

- [ ] Every citation in `WP01.md` maps to an entry in `REFERENCES.bib`
- [ ] Every entry in `REFERENCES.bib` is cited at least once in `WP01.md`
- [ ] Every entry in `REFERENCES.bib` is verified against Zotero / Crossref / DOI resolver
- [ ] `REFERENCES_APA.md` mirrors `REFERENCES.bib`, alphabetized by section

### 3. Metadata consistency

Run the Consistency Rules from [`PUBLICATION_PACKAGE.md`](PUBLICATION_PACKAGE.md):

- [ ] Title identical across `README.md`, `ABSTRACT.md`, `CITATION.md`, `CITATION.cff`, `METADATA.yml`
- [ ] Author name identical across `README.md`, `AUTHORS.md`, `CITATION.md`, `CITATION.cff`, `METADATA.yml`
- [ ] ORCID = `0009-0007-3762-9792` in every file that mentions ORCID
- [ ] Affiliation identical
- [ ] License = `CC-BY-4.0` in `CITATION.cff`, `METADATA.yml`, `LICENSE.md`
- [ ] Version in `VERSION.md` = version in `CITATION.cff` = version in `METADATA.yml`

### 4. Files & directories

- [ ] All expected files present per `PUBLICATION_PACKAGE.md` layout
- [ ] Sub-directories still preserved (`.gitkeep` or real content)
- [ ] No broken internal links (`find . -name '*.md' | xargs -I{} markdown-link-check {}` if tooling available)

### 5. Version + Changelog

- [ ] `VERSION.md` bumped to the new version with a new row in *History*
- [ ] `CHANGELOG.md` has an entry for the new version summarizing what changed
- [ ] Root `CHANGELOG.md` has an *Unreleased* → dated entry for this release
- [ ] `CITATION.cff` `version:` and `date-released:` updated
- [ ] `METADATA.yml` `version:` and `date:` updated

### 6. YAML validation

- [ ] `python3 -c "import yaml; yaml.safe_load(open('CITATION.cff'))"` returns 0
- [ ] `python3 -c "import yaml; yaml.safe_load(open('METADATA.yml'))"` returns 0

### 7. Git

- [ ] Working tree clean; every change committed
- [ ] Branch is `main` (or the branch you intend to release from)
- [ ] `git log` shows the release commit is the intended one

---

## Release procedure

Once every pre-release check passes:

```bash
# 1. Tag the release
git tag -a wp01-v0.1-package -m "WP01 v0.1 — publication package"

# 2. Push the tag
git push origin wp01-v0.1-package

# 3. Create a GitHub Release from the tag
#    - Title:  WP01 v0.1-package — Publication infrastructure
#    - Body:   Copy the corresponding CHANGELOG.md entry verbatim
#    - Assets: none required; the Git tag is the release artefact
```

## Zenodo capture

Prerequisite: the Zenodo–GitHub webhook is activated on the account.
See <https://zenodo.org/account/settings/github/> and enable the toggle for
`lioneldyla/judicial-data-ai-governance-portfolio`.

After the GitHub Release is published:

- [ ] Zenodo automatically ingests the release (usually within 1–5 minutes)
- [ ] A concept DOI is minted on the first release; version DOIs on subsequent releases
- [ ] Verify the DOI at <https://zenodo.org/>
- [ ] Update `CITATION.cff`:
  ```yaml
  doi: "10.5281/zenodo.XXXXXXX"
  ```
- [ ] Update `CITATION.md` BibTeX + APA + Chicago + MLA + Vancouver with the DOI
- [ ] Update `METADATA.yml` `identifiers.zenodo_version_doi` (and `zenodo_concept_doi` on first release)
- [ ] Update `README.md` DOI badge
- [ ] Commit the DOI back-fill (`chore(WP01): back-fill Zenodo DOI`)

## ORCID synchronization

- [ ] Sign into ORCID: <https://orcid.org/>
- [ ] Add WP01 as a Work
- [ ] Set the Work URL to the Zenodo DOI
- [ ] Copy citation metadata from `CITATION.cff`

## SSRN submission

(Only at `wp01-v0.5-draft` or later — SSRN accepts working drafts but
prefers substantive prose.)

- [ ] Sign into SSRN: <https://www.ssrn.com/>
- [ ] Submit WP01 as a preprint
- [ ] Requirements checklist: see [`SUBMISSION_TARGETS.md`](SUBMISSION_TARGETS.md)
- [ ] Once assigned an SSRN paper number, back-fill it into `CITATION.md`

## Announcement (LinkedIn, X, etc.)

- [ ] Post the Zenodo DOI link
- [ ] Include the abstract (≤200 words)
- [ ] Include the tag `#JudicialDataGovernance` and `#OpenScience`
- [ ] Include the ORCID link

## Post-release verification

- [ ] The GitHub Pages site at
      <https://lioneldyla.github.io/judicial-data-ai-governance-portfolio/working_papers/WP01/>
      renders correctly and shows the new version
- [ ] The GitHub "Cite this repository" button (top-right of repo) shows the
      updated `CITATION.cff`
- [ ] The Zenodo page shows the correct title, abstract, author, ORCID,
      license, and version
- [ ] The ORCID profile shows the new Work

---

*Any deviation from this checklist during a release should be documented
in `CHANGELOG.md` (under the release version) so future releases can
learn from it.*
