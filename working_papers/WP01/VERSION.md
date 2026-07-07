# WP01 — Version Register

| Field | Value |
|---|---|
| Reference | WP01 |
| Current **package** version | **1.0** — publication infrastructure landed |
| Current **manuscript** version | **0.0** — annotated outline; body not drafted |
| Current status | Package release-ready; manuscript in preparation |
| Versioning scheme | Semantic Versioning ([SemVer 2.0.0](https://semver.org/spec/v2.0.0.html)) — see §Two version tracks |
| Machine-readable | [`CITATION.cff`](CITATION.cff) `version:` field (tracks package version at v1.0) |
| Change log | [`CHANGELOG.md`](CHANGELOG.md) |

---

## Two version tracks

WP01 uses **two independent version tracks**, tracked in this file:

| Track | What it tracks | Bumped when | Externally-visible |
|---|---|---|---|
| **Package version** | The publication infrastructure — metadata, citation files, license, changelog, references scaffolds | Structure of the package changes | Yes — `CITATION.cff` and Zenodo DOI |
| **Manuscript version** | The scholarly prose in `WP01.md` — sections drafted, references verified | Sections drafted, revised, or peer-reviewed | Yes — release tags (e.g. `wp01-v0.5-draft`) |

The distinction matters because Zenodo mints DOIs against tagged releases,
which can happen at *package v1.0 + manuscript v0.0* (defensible: the
package is a citable artefact). External readers need to know they are
citing the package, not the paper, until the manuscript reaches v1.0.

The single `version:` field in [`CITATION.cff`](CITATION.cff) tracks the
**package** version to satisfy schema requirements. The **manuscript**
version is exposed via release tag names (see
[`RELEASE_CHECKLIST.md`](RELEASE_CHECKLIST.md)).

---

## Version semantics for a working paper

Semantic versioning maps to publication practice as follows:

| Change type | Version increment | Example transition |
|---|---|---|
| Change to author, title, license, or scope | MAJOR | 1.x.x → 2.0.0 |
| Substantive revision to any section; new section; new figure or table | MINOR | 1.0.x → 1.1.0 |
| Editorial correction, typo, broken link, metadata fix | PATCH | 1.0.0 → 1.0.1 |

Additionally, pre-release versions are allowed:

- `0.1.0`, `0.2.0`, ... — draft states before v1.0 was released.
- `1.1.0-preprint.1` — pre-release of an upcoming minor revision.

## Package version history

| Package v | Manuscript v | Date | Status |
|---|---|---|---|
| **1.0** | 0.0 | 2026-07-07 | Publication infrastructure landed. Abstract, keywords, authors, citation, license, references scaffold, manuscript outline, publication-package manifest, release checklist, and submission targets. Manuscript body still to be drafted. |

## Milestones (planned)

Package version is bumped at each infrastructure change; manuscript
version is bumped at each drafted / revised state.

| Release tag | Package v | Manuscript v | Target | Milestone |
|---|---|---|---|---|
| `wp01-v0.1-package` | 1.0 | 0.0 | Now | Publication package landed; concept DOI minted on Zenodo |
| `wp01-v0.5-draft` | 1.0 | 0.5 | Q3 2026 | §1 Introduction + §2 Conceptual Foundations drafted |
| `wp01-v0.8-preprint` | 1.0 | 0.8 | Q3–Q4 2026 | §3–§6 drafted; SSRN preprint submission |
| `wp01-v1.0-manuscript` | 1.0 | 1.0 | Q4 2026 | §7 + §8 drafted; peer feedback incorporated; version-of-record |
| `wp01-v2.0-journal` | 2.0 | 2.0 | Q1 2027 | Journal-style version submitted (see [`SUBMISSION_TARGETS.md`](SUBMISSION_TARGETS.md)) |

## Relation to the Portfolio's version

The Portfolio itself is versioned at the repository level. As of
2026-07-07 the Portfolio is at **v2.0.0**. WP01's version is **independent
of the Portfolio version** — a v1.2 of WP01 can be released without
bumping the Portfolio's version.

## Zenodo relationship

Each MINOR or MAJOR version of WP01 should be tagged in Git and released
on GitHub, which triggers Zenodo to mint a version DOI. The concept DOI
of WP01 remains stable across versions.

---

*Update this register whenever the version bumps; do not backfill.*
