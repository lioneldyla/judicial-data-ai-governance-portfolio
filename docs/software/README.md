# Research Software

> **Category:** Software | **Version:** 1.0.0  
> **License:** MIT (unless otherwise noted)  
> **Last Updated:** July 2026

---

## Overview

This directory documents research software, analytical tools, and computational notebooks developed within the *Data Governance for Intelligent Justice Systems* research programme. All software follows open-source principles and is designed for reproducibility.

---

## Software Register

| ID | Name | Description | Language | Repository | Status |
|---|---|---|---|---|---|
| SW01 | `jdg-diagnostic` | Judicial data governance diagnostic tool | Python | This repo | Planned Q1 2027 |
| SW02 | `judicial-stats-toolkit` | Statistical analysis toolkit for judicial indicators | Python/R | This repo | Planned Q3 2027 |

---

## Software Citation

All research software should be cited using the CITATION.cff format. Software-specific citation metadata will be provided in each tool's subdirectory once released.

---

## Development Standards

- Python 3.10+ for all Python tools
- Code style: PEP 8 compliant, formatted with `black`
- Documentation: docstrings (Google style) + Markdown README
- Testing: `pytest` with minimum 80% coverage
- Version control: semantic versioning (MAJOR.MINOR.PATCH)
- Reproducibility: `requirements.txt` or `pyproject.toml` pinned dependencies

---

## Reproducibility Commitment

All computational results published in working papers and journal articles will be accompanied by the corresponding code and data. Reproducibility packages will be archived on Zenodo with a persistent DOI linked from the relevant publication.
