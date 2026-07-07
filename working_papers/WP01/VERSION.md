# WP01 — Version Register

| Field | Value |
|---|---|
| Reference | WP01 |
| Current version | **1.0** |
| Current status | Publication infrastructure landed; manuscript in preparation |
| Versioning scheme | Semantic Versioning ([SemVer 2.0.0](https://semver.org/spec/v2.0.0.html)) |
| Machine-readable | [`CITATION.cff`](CITATION.cff) `version:` field |
| Change log | [`CHANGELOG.md`](CHANGELOG.md) |

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

## History

| Version | Date | Status |
|---|---|---|
| **1.0** | 2026-07-07 | Publication infrastructure landed. Abstract, keywords, authors, citation, license, references scaffold, and manuscript outline. Manuscript body still to be drafted. |

## Milestones (planned)

| Version | Target date | Milestone |
|---|---|---|
| 1.1 | Q3 2026 | Draft manuscript §1 Introduction + §2 Conceptual Foundations added; first Zenodo release (concept DOI). |
| 1.2 | Q3 2026 | Draft manuscript §3–§5 added; SSRN preprint submission. |
| 1.3 | Q4 2026 | Draft manuscript §6–§8 added; complete first-pass bibliography. |
| 1.4 | Q4 2026 | Peer feedback incorporated; camera-ready. |
| 2.0 | Q1 2027 | Journal article version submitted (see [`ROADMAP.md`](../../ROADMAP.md)). |

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
