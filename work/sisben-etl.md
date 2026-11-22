# Sisbén IV data pipeline

> The first Power BI dashboard of Antioquia’s Planning Department and the Python pipeline behind it, built on ~25M records of Sisbén, the survey Colombia uses to target social programs.

Canonical page: https://vvanegasar.github.io/work/sisben-etl/
Author: Valentina Vanegas Aristizábal (Head of AI & Technology)

*Data and economics · Public sector · 2026*

The first Power BI dashboard of Antioquia’s Planning Department and the Python pipeline behind it, built on ~25M records of Sisbén, the survey Colombia uses to target social programs.

- Status: Covers all 125 municipalities
- Role: Data & Economics Intern. Planning Department, Government of Antioquia
- Period: Feb – Jun 2026
- Stack: Python, DuckDB, PyArrow, Power BI, DAX, TMDL

## Abstract

Sisbén is the survey Colombia uses to decide who can receive social programs, so its numbers have to be right before anyone reads a chart. I built the path from six raw annual snapshots to a dashboard by municipality: a Python pipeline that cleans and audits the data, and a Power BI model the department’s Technical Director used with all 125 municipalities of Antioquia.

## 1. What I built

- The first Power BI dashboard of Antioquia’s Planning Department, with Sisbén data by municipality (2021–2026), used by the Technical Director with all 125 municipalities.
- A batch ETL in Python with DuckDB and PyArrow over ~25M records across six annual snapshots (2021–2026).
- 24 derived columns moved into the batch ETL, plus automated data-quality audits.
- A Power BI semantic model in TMDL and DAX, with 19 tables.

Table 1. The pipeline in numbers.

| What | Count |
| --- | --- |
| Records | ~25M |
| Annual snapshots | 6 (2021–2026) |
| Derived columns | 24 |
| Tables in the semantic model | 19 |
| Municipalities in the dashboard | 125 |

Figure 1. From six raw annual snapshots to a dashboard by municipality, with the data audited before anyone reads a chart.

## Links

- [Code](https://github.com/vvanegasar/sisben-iv-etl-analytics-pipeline)
- [DOI (Zenodo)](https://doi.org/10.5281/zenodo.24442461)
- [My post on LinkedIn (in Spanish)](https://www.linkedin.com/feed/update/urn:li:activity:7478586067563098114/)
- [Internship certificate, in Spanish](https://vvanegasar.github.io/records/internship-certificate-government-of-antioquia.pdf) (PDF, 575 KB)
- [My supervisor’s letter of recommendation](https://vvanegasar.github.io/records/recommendation-letter-hector-mauricio-romero.pdf) (PDF, 148 KB)

## Contact

- Email: aristizabal56vane@gmail.com
- LinkedIn: https://www.linkedin.com/in/vvanegasa
- GitHub: https://github.com/vvanegasar
- Contact form: https://vvanegasar.github.io/contact/
