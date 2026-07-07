# WP01 — Publication Package Manifest

| Field | Value |
|---|---|
| Reference | WP01 |
| Package version | 1.0 |
| Manuscript version | 0.0 (outline) |
| Date | 2026-07-07 |
| Related record | [`../../governance/implementations/2026-07-07_WP01-publication-readiness.md`](../../governance/implementations/2026-07-07_WP01-publication-readiness.md) |

---

## What is the "publication package"

The publication package is the *complete set of files* an external reader,
peer reviewer, publisher, indexer, or citation manager needs to (a)
identify WP01 as a scholarly artefact, (b) cite it correctly, (c) verify
its licensing, (d) trace its versions, and (e) obtain its bibliography and
supplementary materials.

The package is separate from the *manuscript*. A publication package can
exist and be citable before the manuscript is drafted — it just cannot be
*read* as a paper until the manuscript is drafted.

This distinction matters because the researcher may need to cite the WP01
package (in doctoral applications, LinkedIn, grant submissions, etc.)
before the manuscript is complete. Zenodo will mint a DOI against the
package on first tagged release, regardless of manuscript state.

---

## Package layout

### Identity layer

The identity of the paper: title, abstract, keywords, authors.

| File | Purpose | Publication role |
|---|---|---|
| [`README.md`](README.md) | Landing page, publication-quality metadata sheet | First entry point for any reader |
| [`ABSTRACT.md`](ABSTRACT.md) | Standalone abstract | Feeds Zenodo, OpenAIRE, SSRN abstract fields |
| [`KEYWORDS.md`](KEYWORDS.md) | Primary + secondary keywords | Indexing on Zenodo, SSRN, and search engines |
| [`AUTHORS.md`](AUTHORS.md) | Author identity, CRediT roles, positionality | Feeds every citation format |

### Citation layer

How WP01 is cited.

| File | Purpose | Publication role |
|---|---|---|
| [`CITATION.md`](CITATION.md) | Human-readable BibTeX, APA, Chicago, MLA, Vancouver | Copy-paste citation source for readers |
| [`CITATION.cff`](CITATION.cff) | Machine-readable CFF v1.2.0 | GitHub "Cite this repository" button; Zotero; Zenodo ingestion |

### Governance layer

Version, license, change history.

| File | Purpose | Publication role |
|---|---|---|
| [`LICENSE.md`](LICENSE.md) | CC BY 4.0 declaration for WP01 | License clarity for reusers |
| [`VERSION.md`](VERSION.md) | Package + manuscript version register | Version-of-record clarity |
| [`CHANGELOG.md`](CHANGELOG.md) | Keep-a-Changelog history | Provenance for any revision |
| [`METADATA.yml`](METADATA.yml) | Machine-readable YAML for OpenAIRE + Jekyll | Site frontmatter + machine harvesters |

### Bibliography layer

| File | Purpose | Publication role |
|---|---|---|
| [`REFERENCES.bib`](REFERENCES.bib) | BibTeX bibliography | Citation-manager import; LaTeX compile |
| [`REFERENCES_APA.md`](REFERENCES_APA.md) | APA-formatted bibliography | Reader-facing bibliography |

*Both are empty scaffolds at v1.0 package. Entries are added as the
manuscript is drafted.*

### Manuscript layer

| File | Purpose | Publication role |
|---|---|---|
| [`WP01.md`](WP01.md) | The manuscript | The paper itself |

*At v1.0 package, this is an annotated outline. The manuscript body
transitions to prose as it is drafted, per the milestone plan in
[`VERSION.md`](VERSION.md).*

### Package-management layer

| File | Purpose | Publication role |
|---|---|---|
| [`PUBLICATION_PACKAGE.md`](PUBLICATION_PACKAGE.md) | This manifest | Discoverability of the package |
| [`RELEASE_CHECKLIST.md`](RELEASE_CHECKLIST.md) | Release procedure | Repeatable release process |
| [`SUBMISSION_TARGETS.md`](SUBMISSION_TARGETS.md) | Zenodo/SSRN/journal requirements | Preparation for external submission |

### Supplementary layer

Preserved sub-directories for future contents.

| Directory | Purpose |
|---|---|
| [`figures/`](figures/) | Publication figures (SVG preferred, PNG at 300 dpi min) |
| [`tables/`](tables/) | Publication-quality tables (CSV + Markdown) |
| [`supplementary_materials/`](supplementary_materials/) | Extended analysis; supplementary code |
| [`datasets/`](datasets/) | Datasets attached to the paper |
| [`appendices/`](appendices/) | Appendix documents |
| [`media/`](media/) | Slides, videos, dissemination material |

---

## How the layers interlock

```
Identity ─────► Citation ─────► Bibliography ─────► Manuscript
     │                                                    ▲
     ▼                                                    │
Governance ────────────────────────────────────────────────┘
     │
     ▼
Package management ◄──── Supplementary
```

- **Identity** files feed the **Citation** and **Governance** layers.
- **Citation** files must always agree with **Identity** (title, author, ORCID) — any drift is a bug.
- **Bibliography** files support the **Manuscript**.
- **Governance** files (VERSION, CHANGELOG, LICENSE, METADATA) apply across everything.
- **Package management** files (this manifest, RELEASE_CHECKLIST, SUBMISSION_TARGETS) apply across everything and are read-only by external systems.

## Consistency rules

The following must always hold:

1. `README.md` title = `CITATION.md` title = `CITATION.cff` title = `METADATA.yml` title.
2. `AUTHORS.md` name/ORCID/affiliation = `CITATION.md` name = `CITATION.cff` authors = `METADATA.yml` authors.
3. `VERSION.md` current version = `CITATION.cff` version = `METADATA.yml` version.
4. `LICENSE.md` license = `CITATION.cff` license = `METADATA.yml` license = repository-level LICENSE.
5. `ABSTRACT.md` abstract = `WP01.md` §Abstract = `CITATION.cff` abstract = `METADATA.yml` (implicit).
6. `KEYWORDS.md` primary keywords ⊆ `CITATION.cff` keywords ⊆ `METADATA.yml` keywords.
7. Every internal link in every file must resolve.

## What is NOT in the package

- The manuscript prose at v1.0 package — outline only. See [`VERSION.md`](VERSION.md).
- Verified references — empty scaffolds at v1.0 package. See editorial policy in [`REFERENCES.bib`](REFERENCES.bib).
- Figures, tables, appendices — sub-directories preserved with `.gitkeep` for future contents.
- DOI — assigned by Zenodo on first Git-tagged release. See [`RELEASE_CHECKLIST.md`](RELEASE_CHECKLIST.md).
- SSRN paper number — assigned on SSRN submission. See [`SUBMISSION_TARGETS.md`](SUBMISSION_TARGETS.md).

## Release lifecycle

See [`RELEASE_CHECKLIST.md`](RELEASE_CHECKLIST.md) for the ordered release
procedure. See [`VERSION.md`](VERSION.md) for the milestone plan across
versions.

---

*This manifest is the authoritative description of the WP01 publication
package. Update it whenever the package structure changes.*
