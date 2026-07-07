# WP01 — Submission Targets

| Field | Value |
|---|---|
| Reference | WP01 |
| Date | 2026-07-07 |
| Related | [`RELEASE_CHECKLIST.md`](RELEASE_CHECKLIST.md), [`../../ROADMAP.md`](../../ROADMAP.md), [`../../PUBLICATION_POLICY.md`](../../PUBLICATION_POLICY.md) |

---

## Purpose

Every submission channel imposes requirements — word count, keyword count,
abstract length, license compatibility, embargo policy. Capturing them
per-target avoids last-minute reformatting and reduces the risk of
non-compliant submissions.

This document is **not** an endorsement of any specific venue. It is a
requirements register informing the researcher's choice.

---

## Track A — Open preprint / archive

### A.1 Zenodo *(planned for `wp01-v0.1-package`)*

| Field | Requirement |
|---|---|
| Deposit type | Publication → Report → Working paper |
| DOI | Minted automatically per release |
| Title | ≤ 200 chars (WP01 title: 148 chars — fits) |
| Abstract | HTML-safe; no length limit but 150–500 words recommended |
| Keywords | Comma-separated; free-form |
| Author | Full name, ORCID, affiliation |
| License | CC BY 4.0 (compatible) |
| Community | `zenodo` (see `.zenodo.json`) |
| Trigger | GitHub Release → Zenodo webhook |

**Compliance status:** WP01 metadata is Zenodo-ready. `CITATION.cff`,
`METADATA.yml`, and `.zenodo.json` at the repository root are aligned.

### A.2 SSRN *(planned for `wp01-v0.5-draft`)*

| Field | Requirement |
|---|---|
| Content type | Working Paper |
| Length | No minimum; SSRN accepts partial drafts |
| Abstract | ≤ 1,500 characters (WP01 abstract: ~950 chars — fits) |
| Keywords | 6–10 (WP01 primary: 10 — fits) |
| JEL codes | Optional; consider `K10 General`, `K40 Legal Procedure`, `O33 Technological Change` |
| Author profile | Requires SSRN account tied to institutional email |
| License | SSRN accepts CC-BY-4.0 with reserved rights |
| Networks | Consider posting to: Law & Society, Legal Scholarship Network, Development Economics eJournal |
| Turnaround | 2–5 business days to public visibility |

**Compliance status:** Metadata is SSRN-ready. Blockers: (i) SSRN account
activation, (ii) manuscript draft to submit.

---

## Track B — Peer-reviewed journals

Candidates from `ROADMAP.md` §2027 — Journal Articles table. Confirm each
venue against its current submission page before drafting the journal
version.

### B.1 *African Journal of Legal Studies*

| Field | Requirement |
|---|---|
| Publisher | Brill |
| Scope match | Legal studies with a comparative African orientation |
| Article types | Full articles (10,000–14,000 words including footnotes) |
| Style | *Harvard Blue Book* citation style (verify current edition) |
| Open access | Hybrid; APC applies for gold OA |
| Language | English or French |
| Submission portal | Brill EM |
| Preprint policy | Verify — Brill traditionally allows working-paper preprints |
| Fit for WP01 | ⚠️ WP01 is more institutional-analytical than legal-doctrinal; verify fit |

### B.2 *Law and Development Review*

| Field | Requirement |
|---|---|
| Publisher | De Gruyter |
| Scope match | Law-and-development; strong Africa track |
| Article types | Research articles, review articles, notes |
| Style | Author-date (Chicago) |
| Open access | Hybrid |
| Preprint policy | Generally permissive |
| Fit for WP01 | ✅ Strong fit — legal + institutional + African development |

### B.3 *Computer Law & Security Review*

*(Target for WP02, not WP01. Listed here to record its requirements early.)*

### B.4 *Journal of African Law*

| Field | Requirement |
|---|---|
| Publisher | Cambridge University Press |
| Scope match | African legal systems, comparative and empirical work |
| Article types | Articles, notes and recent developments, book reviews |
| Style | OSCOLA or in-house style guide |
| Open access | Gold OA available; Read & Publish agreements |
| Preprint policy | CUP: preprints permitted; check green route |
| Fit for WP01 | ✅ Excellent — African orientation + institutional analysis |

### B.5 *International Journal of Law and Information Technology*

| Field | Requirement |
|---|---|
| Publisher | Oxford University Press |
| Scope match | Law + IT + governance |
| Fit for WP01 | ✅ Strong — bridging law/administration and data governance |

---

## Track C — Policy / practitioner outlets

WP01 may have policy resonance beyond academic journals.

| Outlet | Fit | Notes |
|---|---|---|
| ECOWAS Court of Justice Working Paper Series | ✅ | Regional policy audience |
| African Union Legal Affairs Working Papers | ✅ | Continental audience |
| OHADA Ohadata portal | ✅ | Francophone reach |
| IDLO (International Development Law Organization) | ⚠️ | Practitioner-oriented; requires policy-brief adaptation |

Submissions to policy outlets should be *adaptations* of the peer-review
version, not the version-of-record itself.

---

## Requirements table — comparative snapshot

| Requirement | Zenodo | SSRN | AJLS | LDR | JAL | IJLIT |
|---|---|---|---|---|---|---|
| Abstract length | any | ≤ 1500 chars | ≤ 250 words | ≤ 250 words | ≤ 300 words | ≤ 250 words |
| Word count target | any | any | 10–14k | 8–12k | 8–15k | 6–10k |
| Keywords | free | 6–10 | 5–7 | 4–6 | 4–6 | 4–6 |
| License CC-BY-4.0 | ✅ | ✅ | via APC | via APC | via APC | via APC |
| Preprint allowed | native | native | verify | ✅ | ✅ | ✅ |
| Response time | mins | days | months | months | months | months |

(Table values are indicative; verify against each venue's current
"Instructions to Authors" before drafting the journal version.)

---

## Decision framework

The researcher should choose one *primary* target and 1–2 fallbacks.
Recommended criteria:

1. **Scope fit** — does the paper answer a question the journal cares about?
2. **Africa orientation** — venues committed to Global-South scholarship are preferred to avoid the extractive dynamic of publishing African research in Northern-only outlets.
3. **Open access** — CC BY 4.0 preferred; hybrid OA acceptable with APC.
4. **Timeline** — Q1 2027 target per the ROADMAP.
5. **Language** — English preferred for maximum reach; French possible for AJLS or Francophone-oriented outlets.

Recommended primary target for the journal version: **Journal of African
Law** or **Law and Development Review**.

---

## Update policy

This document is updated whenever a submission is made or a new candidate
venue is identified. Every update is recorded in `CHANGELOG.md`.
