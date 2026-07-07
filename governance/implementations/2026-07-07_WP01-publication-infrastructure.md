# WP01 — Publication Infrastructure

> Implementation record for the seven-step deliverable prescribed by the
> *Master Implementation Specification v3.0*, §Deliverables.

| Field | Value |
|---|---|
| Date | 2026-07-07 |
| Artefact scope | `working_papers/WP01/` |
| Priority | #1 in the Scientific-Production priority order |
| Branch | `claude/wp01-publication-infrastructure` |
| Related PR | To be opened as draft |
| Preceding audit | [`governance/ecosystem-audit/`](../ecosystem-audit/README.md) |
| Author | DJORO Yoboukoua Lionel Arnaud |
| ORCID | 0009-0007-3762-9792 |

---

## 1. Current State Assessment

The `working_papers/WP01/` directory contains a **single file**:
`README.md` (~3.9 KB).

That README declares WP01's identity: title, status (*In Publication*),
version 1.0, abstract (~140 words), keywords (10 terms), a target directory
structure, a publication workflow, and a BibTeX citation stub. It is a
publication-quality metadata sheet — but nothing else in the directory
exists yet.

The Research Portfolio Handbook (`docs/RESEARCH_PORTFOLIO_HANDBOOK.md`
§*File Naming Conventions*) declares that working papers should live under
a `WP[NN]/` directory containing at minimum `README.md` and a
`WP[NN]_DRAFT.md`. WP01's own README declares a fuller layout (`WP01.md`,
`ABSTRACT.md`, `KEYWORDS.md`, `AUTHORS.md`, `CITATION.md`, `LICENSE.md`,
`VERSION.md`, `CHANGELOG.md`, `REFERENCES.bib`, `REFERENCES_APA.md`, and
sub-directories `figures/`, `tables/`, `supplementary_materials/`,
`datasets/`, `appendices/`, `media/`).

The Portfolio's *Scientific Production* priority order (Master Spec v3.0)
places **WP01 publication as #1**, ahead of Zenodo DOI issuance, ORCID
synchronization, and SSRN publication — which all depend on WP01 having a
citeable, DOI-eligible artefact.

**Conclusion.** The metadata is in place; the publication artefact and its
surrounding infrastructure are not. Nothing blocks the researcher from
writing the manuscript. Nothing helps the researcher either — every
supporting file the manuscript will need is missing.

## 2. Gap Analysis

| # | Missing artefact | Category | Rationale |
|---|---|---|---|
| G1 | `WP01.md` | Manuscript | The paper itself. |
| G2 | `ABSTRACT.md` | Metadata | Standalone abstract (repeats README §Abstract) so it is discoverable outside the README. |
| G3 | `KEYWORDS.md` | Metadata | Standalone keywords for SEO and repository search. |
| G4 | `AUTHORS.md` | Metadata | Author identity, ORCID, affiliation, contribution roles (CRediT). |
| G5 | `CITATION.md` | Metadata | Human-readable APA / MLA / Chicago / BibTeX. |
| G6 | `CITATION.cff` | Metadata | Machine-readable CFF v1.2.0 specific to WP01 (the root CITATION.cff is for the whole portfolio). |
| G7 | `LICENSE.md` | Governance | Publication license declaration for WP01. |
| G8 | `VERSION.md` | Governance | Semantic versioning register. |
| G9 | `CHANGELOG.md` | Governance | Modification history (Keep a Changelog). |
| G10 | `REFERENCES.bib` | Bibliography | BibTeX file for citation management. |
| G11 | `REFERENCES_APA.md` | Bibliography | APA-formatted bibliography. |
| G12 | `METADATA.yml` | GitHub Pages / OpenAIRE | Machine-readable metadata frontmatter for Jekyll and OpenAIRE. |
| G13 | `figures/`, `tables/`, `supplementary_materials/`, `datasets/`, `appendices/`, `media/` | Structure | Preserved sub-directories with `.gitkeep`. |

Two gaps I explicitly do **not** claim to close in this iteration:

- **G14.** The manuscript body itself — writing WP01's scholarly prose. That
  is the researcher's responsibility. Fabricating it would violate
  `RESEARCH_MANIFESTO.md` §3.3 ("*Intellectual honesty is non-negotiable*").
- **G15.** A curated bibliography (real, verified references). Fabricating
  citations to plausible-sounding-but-non-existent works is the specific
  failure mode this repository must avoid. `REFERENCES.bib` and
  `REFERENCES_APA.md` are created as **empty scaffolds with structural
  comments**, not with fabricated entries.

## 3. Improvement Strategy

**Principle: separate publication *infrastructure* from publication *content*.**

An AI can safely build the infrastructure — file structure, metadata,
citation formats, licensing declarations, changelog scaffolding, YAML
frontmatter, and an annotated section-by-section outline of the manuscript.
An AI cannot safely write the manuscript body without risking fabricated
citations, false authority, or content the researcher never chose. The
strategy respects that boundary.

Concretely:

1. **Close infrastructure gaps G2–G13 completely** in this iteration.
   All artefacts are derivable from data already in the repository
   (README.md, root CITATION.cff, LICENSE, ORCID identifier), or are pure
   structural scaffolds.

2. **Address G1 partially** by creating `WP01.md` as an *annotated outline*.
   Each section carries: heading, a two-sentence description of what the
   section will cover, and an explicit `[TO BE DRAFTED BY THE AUTHOR]`
   marker. No scholarly claims are asserted; no references are placed;
   no summaries of imagined content are provided.

3. **Do not touch G14–G15** in this iteration.

4. **Do not touch the existing README.md** — it is publication-quality.

## 4. Implementation Plan

Files to create under `working_papers/WP01/`:

- `WP01.md` — annotated section outline (see Strategy §2).
- `ABSTRACT.md`
- `KEYWORDS.md`
- `AUTHORS.md`
- `CITATION.md`
- `CITATION.cff` (WP01-scoped)
- `LICENSE.md`
- `VERSION.md`
- `CHANGELOG.md`
- `REFERENCES.bib` — empty scaffold, header comments only
- `REFERENCES_APA.md` — empty scaffold
- `METADATA.yml`
- `figures/.gitkeep`, `tables/.gitkeep`, `supplementary_materials/.gitkeep`,
  `datasets/.gitkeep`, `appendices/.gitkeep`, `media/.gitkeep`

Root-level updates:

- `CHANGELOG.md` — add an *Unreleased* bullet for the WP01 infrastructure.

Files explicitly **not** touched:

- `working_papers/WP01/README.md` — already publication quality.
- Root `CITATION.cff` — portfolio-scoped, not paper-scoped.
- Root `LICENSE` — covers the whole repository under CC-BY-4.0.

## 5. Implementation

Landed on branch `claude/wp01-publication-infrastructure`. See the diff on
the associated PR. Sixteen files added; no existing file rewritten;
CHANGELOG updated.

## 6. Validation Report

Checks performed before opening the PR:

- [x] All new Markdown renders under GitHub-flavored CommonMark.
- [x] Every internal link in the new files resolves to a file that exists
      in the same commit.
- [x] `working_papers/WP01/CITATION.cff` validates against CFF v1.2.0
      schema (ORCID URL, author `family-names` + `given-names`, license
      identifier `CC-BY-4.0`, `type: report`).
- [x] `working_papers/WP01/METADATA.yml` parses as valid YAML and is
      compatible with Jekyll frontmatter.
- [x] Author identity (name, ORCID, affiliation) is identical across
      README.md, ABSTRACT.md, AUTHORS.md, CITATION.md, CITATION.cff, and
      METADATA.yml — one string, one ORCID, one affiliation.
- [x] `REFERENCES.bib` contains no fabricated entries. It contains only
      BibTeX comments explaining the intended citation format.
- [x] `WP01.md` contains no fabricated scholarly claims. Every section is
      an outline marker.

Not verified in this iteration (deferred):

- [ ] Zenodo release round-trip (blocked on Zenodo account activation).
- [ ] SSRN upload compatibility (blocked on SSRN account activation).
- [ ] Downstream ORCID work sync (blocked on Zenodo DOI issuance).

## 7. Recommendations for Next Iteration

Ordered by priority within the Master Spec v3.0 priority list.

1. **Draft the WP01 manuscript body.**
   The outline in `WP01.md` names 8 sections. Recommended drafting order:
   §1 Introduction → §2 Conceptual Foundations → §3 Judicial Data as a
   Category → §4 Governance Requirements → §5 Institutional Conditions →
   §6 Application to African Context → §7 Discussion → §8 Conclusion.
   Each section should end with 2–5 references added to `REFERENCES.bib`
   as the drafting proceeds — never after.

2. **Register the Zenodo — GitHub webhook.**
   Once WP01 §1–§3 are drafted (even in preliminary form), issue a v0.1
   tag on the repo. Zenodo will mint a concept DOI. The paper does not
   need to be complete to receive a DOI — it needs to exist as a
   consistent artefact.

3. **Back-fill the Zenodo DOI badge** in the Portfolio README and in
   `WP01/README.md`.

4. **Synchronize ORCID.** Add WP01 as a "Work" on the ORCID profile,
   pointing at the Zenodo DOI.

5. **Prepare the SSRN submission.** SSRN accepts preprints; the WP01
   manuscript at v0.5 (a discussable draft) is enough for a submission.
   SSRN's identifier is added to `CITATION.md` once assigned.

6. **Begin JDGF v1.0 conceptual model.** WP01 §4 (Governance Requirements)
   is the empirical grounding for the JDGF framework's first version.
   Open a companion implementation record
   `2026-XX-XX_JDGF-v1-conceptual-model.md` when starting.

7. **Introduce a `research_questions/` section** (per Master Spec v3.0
   §Research Questions). Currently the research questions are dispersed
   across `RESEARCH_AGENDA.md`, `DOCTORAL_RESEARCH_PLAN.md`, and
   `RESEARCH_STRATEGY_2026-2035.md`. Consolidating them into a single
   register makes it possible to link every scientific output to at
   least one identified question.

8. **Address PR #1 (ecosystem audit).** The seven open questions in
   `governance/ecosystem-audit/10_ARCHITECTURE_BLUEPRINT.md` still block
   the cross-ecosystem work. The scientific-production track is
   independent of them and can proceed in parallel.

---

*Records under `governance/implementations/` are the working memory of
the Research Digital Infrastructure. They are the first thing a future
maintainer — human or AI — should read after `README.md` and
`RESEARCH_PORTFOLIO_HANDBOOK.md`.*
