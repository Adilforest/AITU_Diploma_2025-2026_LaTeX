# AITU Diploma Thesis — LaTeX Source

LaTeX source for the bachelor's diploma thesis *"Development of a Service for Receipt Storage, Analysis, and Price Monitoring"*, Astana IT University, 2025–2026.

![LaTeX](https://img.shields.io/badge/LaTeX-008080?style=flat&logo=latex&logoColor=white)
![License](https://img.shields.io/badge/license-academic-blue?style=flat)

## Overview

| | |
|---|---|
| **Title** | Development of a Service for Receipt Storage, Analysis, and Price Monitoring |
| **Institution** | Astana IT University (AITU), School of Software Engineering |
| **Program** | 6B06102 — Software Engineering |
| **Authors** | Adil Ormanov, Damir Timergazin, Yerassyl Salimgerey |
| **Supervisor** | Askar Khaimuldin |
| **Defense** | June 2026, Astana, Kazakhstan |

The thesis describes the design and implementation of **MonServ** — an event-driven, microservice receipt-analytics platform. The system ingests electronic fiscal receipts from Kazakhstani OFD operators (oofd.kz, wofd.kz, ofd1.kz) through three input channels (manual entry, OCR, and web parsing), normalises and clusters product names using multilingual NLP and vector search, and surfaces price and category analytics through a single-page web application.

For an overview of the code and system architecture see the companion repository: [github.com/Adilforest/monserv-portfolio](https://github.com/Adilforest/monserv-portfolio)

## Repository Structure

```
memoirthesis.tex          # Root document (memoir class, A4, 1.5-spaced)
thesisbiblio.bib          # BibTeX bibliography
frontmatter/
  title.tex               # Title page
  abstract.tex            # Abstract (EN / RU / KK)
  definitions.tex         # Glossary / abbreviations
  intro.tex               # Introduction
  concl.tex               # Conclusion
  declaration.tex         # Authorship declaration
chapters/
  chapter01/introduction.tex    # Chapter 1 — Literature review & analysis
  chapter02/main.tex            # Chapter 2 — System design & implementation
  chapter03/conclusion.tex      # Chapter 3 — Evaluation & results
  appendices/app0A.tex          # Appendix A
logos/
  AITU.png                # University logo
```

## Building the PDF

Requires a TeX distribution with `pdflatex`, `bibtex`, and `latexmk` (TeX Live 2022+ or MiKTeX).

```bash
# Recommended — handles multiple passes and bibliography automatically
latexmk -pdf -interaction=nonstopmode -f memoirthesis.tex
```

Or manually:

```bash
pdflatex -interaction=nonstopmode memoirthesis.tex
bibtex memoirthesis
pdflatex -interaction=nonstopmode memoirthesis.tex
pdflatex -interaction=nonstopmode memoirthesis.tex
```

Output: `memoirthesis.pdf`

The document uses the `memoir` class with `T2A` font encoding and `babel` for English, Russian, and Kazakh.

## Tech Stack

- LaTeX (memoir document class)
- BibTeX for bibliography
- `babel` with English / Russian / Kazakh
- `pgvector`, `listings`, `microtype`, `hyperref`, and related packages

---

Adil Ormanov — [GitHub](https://github.com/Adilforest)
