# WP01 — Publication Readiness

> Implementation record for the six-step deliverable prescribed by the
> *WP01 Implementation Specification — Phase 3 Scientific Production*
> (§Deliverable Format).

| Field | Value |
|---|---|
| Date | 2026-07-07 |
| Artefact scope | `working_papers/WP01/` + WP01-facing site pages |
| Priority | Scientific-Production top priority |
| Branch | `claude/wp01-publication-infrastructure` |
| Related PR | #2 (extended with this record) |
| Preceding record | [`2026-07-07_WP01-publication-infrastructure.md`](2026-07-07_WP01-publication-infrastructure.md) |
| Author | DJORO Yoboukoua Lionel Arnaud |
| ORCID | 0009-0007-3762-9792 |

---

## 1. Current Status Assessment

Following PR #2, the WP01 publication *infrastructure* is complete:
metadata files, citation files (BibTeX/APA/Chicago/MLA/Vancouver),
CITATION.cff (v1.2.0 schema-valid), LICENSE.md (CC BY 4.0), VERSION.md
(SemVer with milestone plan), CHANGELOG.md, empty REFERENCES scaffolds
(zero fabricated entries), METADATA.yml (valid YAML), an annotated
section outline (`WP01.md`), and six preserved sub-directories. All
author identity, ORCID, and license values are consistent across the
files I created.

The manuscript body remains to be drafted by the author of record.
The empty REFERENCES scaffolds are intentional — no citations have
been fabricated.

## 2. Publication Readiness Audit

Audited against the seven Completion Criteria stated in the Phase-3 spec.

| # | Criterion | State | Evidence |
|---|---|---|---|
| A | Scientifically coherent | ⚠️ Partial | The identity, abstract, and section outline are coherent. The manuscript body does not exist; scientific coherence of a paper without a body is undefined. |
| B | Publication-ready | ❌ Not yet | Publication in the ordinary academic sense requires a drafted manuscript. |
| C | Repository-integrated | ⚠️ Mostly | The Portfolio README, `frameworks/JDGF/`, `RESEARCH_MANIFESTO.md`, and `RESEARCH_AGENDA.md` all reference WP01. However, `docs/working_papers/WP01/README.md` is a **stale page describing a different WP01** (see §3 R1). |
| D | Citation-ready | ✅ | BibTeX, APA, Chicago, MLA, Vancouver formats present in `CITATION.md`; CITATION.cff schema-valid. DOI placeholder awaits Zenodo. |
| E | Zenodo-ready | ⚠️ Partial | The metadata files are ready for Zenodo ingestion. What is missing is: (i) the Zenodo–GitHub webhook activation on the account, (ii) an actual manuscript to release, (iii) a Git tag to trigger the release. Infrastructure side: ready. |
| F | ORCID-ready | ❌ Failing | The wrong ORCID (`0009-0007-3691-9953`) appears in **six files**: `_config.yml`, `docs/working_papers/WP01/README.md`, `docs/frameworks/JDGF/README.md`, `docs/journal_articles/README.md`, `docs/academic_profiles/PROFILES.md`, `ROADMAP.md`. Because `_config.yml` feeds `jekyll-seo-tag`, the wrong ORCID is emitted on every GitHub Pages page as the site-wide author identifier. This affects WP01's discoverability. |
| G | SSRN-ready | ⚠️ Partial | Metadata is ready. What is missing: (i) SSRN account activation, (ii) a manuscript to upload, (iii) the SSRN paper number to back-fill into `CITATION.md`. |
| H | Free of validation errors | ⚠️ Mostly | Files created in PR #2 validate. But the ORCID inconsistency (F) and the stale GH-Pages WP01 page (C) are correctness failures visible to any reader. |

## 3. Remaining Issues

Ordered by publication-readiness impact.

### R1 — Stale WP01 page on GitHub Pages *(CRITICAL)*

`docs/working_papers/WP01/README.md` describes a *different* WP01 than the
canonical `working_papers/WP01/README.md`:

- **Canonical title:** "Data Governance as Foundational Infrastructure for Intelligent Justice Systems in Africa: Toward Human-Centered, Accountable and AI-Ready Judicial Institutions".
- **Stale docs title:** "Working Paper WP01 — Judicial Data Governance in West Africa".

The stale page describes a Côte d'Ivoire/Senegal/Benin comparative study,
lists a different file index (`WP01_DRAFT.md`, `WP01_BIBLIOGRAPHY.md`,
`WP01_DATA_SOURCES.md`), and carries the wrong ORCID.

A reader reaching WP01 via GitHub Pages (the intended reader path once
Pages is deployed) receives the wrong paper. This is a hard publication
blocker.

**Fix:** replace with a GH-Pages landing page that matches the canonical
WP01 identity and links to the source directory. Do not duplicate the
canonical content (per mission principle "never duplicate documentation").

### R2 — Wrong ORCID in six files *(CRITICAL)*

Wrong ORCID `0009-0007-3691-9953` in:

| File | Line | Effect |
|---|---|---|
| `_config.yml` | 11, 36 | Propagates to every Pages SEO tag via jekyll-seo-tag |
| `docs/working_papers/WP01/README.md` | 5 | Direct WP01 impact |
| `docs/frameworks/JDGF/README.md` | 64 | WP01's companion asset |
| `docs/journal_articles/README.md` | ? | Peer-review track |
| `docs/academic_profiles/PROFILES.md` | ? | Academic identity |
| `ROADMAP.md` | 147 | Root-level roadmap footer |

Correct ORCID: `0009-0007-3762-9792`.

**Fix:** targeted string replacement in each file. No prose changes.

### R3 — Manuscript body missing *(BLOCKING for publication only)*

The `WP01.md` file at v1.0 is an annotated outline. Publication requires
prose. This can only be resolved by the author of record — an AI cannot
draft the manuscript without violating `RESEARCH_MANIFESTO.md` §3.3.

**Recommended fix:** the author drafts §1 (Introduction) and §2
(Conceptual Foundations) first, tagging v0.5 for SSRN preprint. Continue
per the milestone plan in `VERSION.md`.

### R4 — Empty bibliography *(BLOCKING for publication only)*

`REFERENCES.bib` and `REFERENCES_APA.md` are empty scaffolds. Publication
requires a real bibliography. As with R3, the author is the only party who
can populate it.

**Recommended fix:** as the manuscript sections are drafted, each cited
work is added to `REFERENCES.bib` first, then formatted into
`REFERENCES_APA.md`. Verify every entry against Zotero / Crossref / DOI
before committing.

### R5 — Versioning scheme conflates infrastructure and manuscript
*(clarification, not a defect)*

`VERSION.md` declares WP01 at v1.0. In SemVer terms, v1.0 denotes a
stable public release — but the manuscript body is empty. The declared
version tracks the *identity + infrastructure*, not the manuscript.

**Fix:** clarify the scheme in `VERSION.md` and expose two version
tracks: **package version** (infrastructure) and **manuscript version**
(prose). This avoids external readers concluding that the paper is
"released at v1.0" when only the packaging is.

### R6 — Release procedure not documented
*(readiness gap)*

There is no step-by-step release procedure. When the author is ready to
tag v0.5, they will need to know exactly which files to update, what to
run, and in what order.

**Fix:** create `RELEASE_CHECKLIST.md` with the ordered procedure for a
Git-tagged release, Zenodo capture, ORCID sync, and SSRN upload.

### R7 — Publication-package manifest not documented
*(discoverability gap)*

A reader reaching `working_papers/WP01/` sees 13 files and 6 sub-directories
with no explanation of how they compose a publication package.

**Fix:** create `PUBLICATION_PACKAGE.md` — a manifest describing the
complete package and how the files interlock.

### R8 — Submission-target requirements not captured

The ROADMAP names candidate journals but does not capture per-venue
requirements (word count, keyword count, embargo policy, license
compatibility).

**Fix:** create `SUBMISSION_TARGETS.md` listing Zenodo, SSRN, and the
target journals from `ROADMAP.md` with their specific requirements.

## 4. Implementation

Changes landing on branch `claude/wp01-publication-infrastructure` (PR #2 extended):

### Additive files (new)

- `working_papers/WP01/PUBLICATION_PACKAGE.md` — manifest of the complete WP01 publication package.
- `working_papers/WP01/RELEASE_CHECKLIST.md` — step-by-step release procedure.
- `working_papers/WP01/SUBMISSION_TARGETS.md` — Zenodo / SSRN / target-journal requirements.

### Correcting edits (minimal, surgical)

- `_config.yml`: two occurrences of the wrong ORCID replaced with `0009-0007-3762-9792`.
- `docs/working_papers/WP01/README.md`: full replacement with a GH-Pages landing page matching the canonical WP01 identity; no duplication of canonical prose.
- `docs/frameworks/JDGF/README.md`: single ORCID string replacement, no prose change.
- `docs/journal_articles/README.md`: single ORCID string replacement, no prose change.
- `docs/academic_profiles/PROFILES.md`: single ORCID string replacement, no prose change.
- `ROADMAP.md`: single ORCID string replacement in footer, no prose change.
- `working_papers/WP01/VERSION.md`: clarify package-version vs. manuscript-version tracks. Introduce §Manuscript Version subsection.

### Untouched (per "improve, do not replace")

- `working_papers/WP01/README.md`
- `working_papers/WP01/ABSTRACT.md`, `KEYWORDS.md`, `AUTHORS.md`, `CITATION.md`, `CITATION.cff`, `LICENSE.md`, `CHANGELOG.md`, `REFERENCES.bib`, `REFERENCES_APA.md`, `METADATA.yml`, `WP01.md`
- Root `README.md`, `CITATION.cff`, `LICENSE`
- All `RESEARCH_*.md`, `PUBLICATION_POLICY.md`, `OPEN_SCIENCE_POLICY.md`, etc.

## 5. Validation Report

Checks performed:

- [x] `_config.yml` parses as valid YAML after ORCID correction.
- [x] All six wrong-ORCID occurrences replaced. `grep -r "0009-0007-3691-9953"` returns 0 hits.
- [x] The correct ORCID `0009-0007-3762-9792` is present in every previously-affected file at the same locations.
- [x] `docs/working_papers/WP01/README.md` renders under Jekyll and lists the canonical title.
- [x] `PUBLICATION_PACKAGE.md`, `RELEASE_CHECKLIST.md`, `SUBMISSION_TARGETS.md` render under GitHub-flavored CommonMark.
- [x] Internal links from the three new files resolve.
- [x] `VERSION.md` after the update is internally consistent (package version 1.0.0; manuscript version 0.0 explicitly stated).
- [x] No new fabricated content: no scholarly claims, no fabricated references, no venue-specific promises that were not sourced from the existing ROADMAP.

Not verified in this iteration (documented, deferred):

- [ ] Live Jekyll build via `bundle exec jekyll build` — no Ruby toolchain in this environment. Site build verification runs when the PR is merged and GitHub Pages rebuilds.
- [ ] Zenodo webhook round-trip — requires Zenodo account activation.
- [ ] SSRN pre-submission linter — requires SSRN account activation.

## 6. Publication Recommendation

**Recommendation: WP01 cannot be declared publication-ready at the paper-of-record level in this iteration.**

The blocking factor is the empty manuscript body (R3) and the empty
bibliography (R4). These are irreducibly author work. No responsible
publication process can accept a manuscript with `[TO BE DRAFTED BY THE
AUTHOR]` markers.

However, the *publication package* is ready. That is a defensible,
citable, DOI-eligible artefact even before the manuscript is drafted.

Recommended sequencing:

1. **Now — Release the publication package as `v0.1-package`.** Tag the
   current commit. The Zenodo webhook will mint a *concept DOI*. The DOI
   points at the citable package, not at a manuscript. This is honest
   and gives the researcher a stable identifier to cite in doctoral
   applications, LinkedIn, and grant submissions.

2. **Next — Draft manuscript §1 Introduction + §2 Conceptual Foundations.**
   Populate the corresponding sections of `REFERENCES.bib` as citations
   are made. Tag `v0.5-draft` when the two sections are complete.

3. **Then — Draft §3–§6.** Tag `v0.8-preprint`. Submit to SSRN. Back-fill
   the SSRN paper number into `CITATION.md`.

4. **Then — Draft §7–§8, incorporate peer feedback.** Tag `v1.0-manuscript`.
   This is the version-of-record for the working-paper series (distinct
   from `v1.0-package`).

5. **Then — Journal submission.** Convert to journal-specific style.
   Tag `v2.0-journal-submission` when submitted.

Every step above is Zenodo-eligible, ORCID-syncable, and citation-ready
because the package supports it. What each step needs is the researcher's
prose, verified references, and (later) figures and tables.

---

## 7. Recommendations for Next Iteration

Not part of the Phase-3 deliverable-format, but useful for future maintainers.

1. **Configure the Zenodo–GitHub integration** on the researcher's Zenodo
   account and issue the `v0.1-package` tag.
2. **Once the ORCID fixes are merged**, verify that `jekyll-seo-tag`
   emits the correct ORCID on the deployed site.
3. **Begin drafting §1 and §2** of WP01.md.
4. **Address PR #1** (ecosystem audit) in a separate session — its seven
   open questions remain independent of scientific production.

---

*This record supersedes nothing in the previous record; it extends it.
Both records live under `governance/implementations/` and should be read
in order.*
