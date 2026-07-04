# EEAI-Chile — Design and Initial Validation of a Comprehensive Academic Engagement Scale for Chilean University Faculty

[![License: MIT](https://img.shields.io/badge/Code%20License-MIT-yellow.svg)](LICENSE)
[![Data License: CC BY 4.0](https://img.shields.io/badge/Data%20License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
<!-- After archiving a release on Zenodo, add the DOI badge here:
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX) -->

This repository contains the anonymized data, analysis code, and reproducible outputs for the research article:

> **Fuentes-Lama, R., Juárez-Hernández, L. G., & Monge-Rogel, R.** (2026). *Diseño y validación inicial de una escala integral de engagement académico para el profesorado universitario chileno* [Design and initial validation of a comprehensive academic engagement scale for Chilean university faculty]. Manuscript in preparation.

## Overview

The **EEAI-Chile** (Escala de Engagement Académico Integral) is a 29-item, 5-point Likert instrument measuring academic engagement among Chilean university faculty across six dimensions:

| Code | Dimension |
|------|-----------|
| D1 | Teaching vitality, dedication, and absorption |
| D2 | Social engagement and impact |
| D3 | Digital agency and information technologies |
| D4 | Fairness and contractual environment |
| D5 | Academic leadership and support |
| D6 | Governance and strategic participation |

The validation reported here comprises two stages:

1. **Content validity (expert judgment).** A panel of expert judges rated each item on relevance and wording. Content validity was quantified with **Aiken's V** coefficient and 95% confidence intervals.
2. **Pilot study (*N* = 104 university faculty).** Internal-consistency reliability was estimated per dimension and for the total scale using **Cronbach's α**, **ordinal α** (from polychoric correlations), and **McDonald's ω**, with bootstrap confidence intervals, alongside APA 7 descriptive tables of the sample's sociodemographic and professional characteristics.

## Repository structure

```
.
├── README.md                  <- This file
├── LICENSE                    <- MIT License (code)
├── CITATION.cff               <- Citation metadata (GitHub "Cite this repository")
├── requirements.txt           <- Python dependencies
├── data/
│   ├── README.md              <- Data dictionary and anonymization notes
│   ├── expert_judgment/
│   │   ├── data_aiken_engagement.csv       <- Expert ratings (relevance & wording, 31 initial items)
│   │   └── sociodemographic_judges.csv     <- Expert panel characteristics
│   └── pilot/
│       └── EEAI-Chile_Pilot_Data_2026_anonymized.xlsx  <- Anonymized pilot survey (N = 104)
├── notebooks/
│   ├── 01_content_validity_aiken_v.ipynb   <- Aiken's V + 95% CI, judge characterization, Figure 2
│   ├── 02_pilot_demographics_tables.ipynb  <- APA 7 Tables 1–2 (sample description, instrument evaluation)
│   └── 03_pilot_reliability.ipynb          <- APA 7 Tables 3–4 (α, ordinal α, ω, item analysis)
├── outputs/
│   ├── figures/               <- Generated figures (PNG 600 dpi, PDF, TIFF)
│   └── tables/                <- Generated APA 7 tables (Word .docx)
└── docs/
    └── (supplementary materials, e.g., final instrument, ethics documentation)
```

## Reproducing the analyses

### Requirements

- Python ≥ 3.10
- Dependencies listed in [`requirements.txt`](requirements.txt)

```bash
git clone https://github.com/<USERNAME>/EEAI-Chile-Validation.git
cd EEAI-Chile-Validation
pip install -r requirements.txt
```

### Running the notebooks

Run the notebooks from the `notebooks/` directory (paths are relative to it), in order:

| # | Notebook | Inputs | Outputs |
|---|----------|--------|---------|
| 1 | `01_content_validity_aiken_v.ipynb` | `data/expert_judgment/*.csv` | Aiken's V tables + Figure 2 → `outputs/` |
| 2 | `02_pilot_demographics_tables.ipynb` | `data/pilot/*.xlsx` | Tables 1–2 (.docx) → `outputs/tables/` |
| 3 | `03_pilot_reliability.ipynb` | `data/pilot/*.xlsx` | Tables 3–4 (.docx) → `outputs/tables/` |

```bash
jupyter lab   # then open and run each notebook top-to-bottom
```

All tables are exported in APA 7th-edition format as Word documents; the Aiken's V figure is exported at publication quality (600 dpi PNG/TIFF and vector PDF).

## Data availability

The datasets supporting this study are openly available in this repository (`data/`) under a **CC BY 4.0** license:

- **Expert-judgment data:** ratings of the 31 initial items on relevance and wording, plus anonymized sociodemographic characteristics of the expert panel.
- **Pilot data:** anonymized item-level responses and sociodemographic/professional variables for 104 Chilean university faculty.

To protect participant privacy, the public pilot dataset has been **de-identified**: response timestamps were replaced with sequential participant IDs, and institution names and open-text comments were removed prior to publication. No direct identifiers were collected. See [`data/README.md`](data/README.md) for the full data dictionary and anonymization procedure.

## Code availability

All analysis code (Jupyter notebooks, Python) used to generate the results, tables, and figures reported in the article is openly available in this repository under the **MIT License**. <!-- After the Zenodo release: "and permanently archived at https://doi.org/10.5281/zenodo.XXXXXXX" -->

## Ethics statement

Participation was voluntary and anonymous; informed consent was obtained from all participants before responding (consent item recorded in the dataset). <!-- TODO: add ethics committee approval, e.g., "The study protocol was approved by the [Ethics Committee, Institution] (approval no. XXXX, date)." -->

## How to cite

If you use this repository, please cite both the article (once published) and the repository:

```bibtex
@misc{fuenteslama2026eeai,
  author    = {Fuentes-Lama, Ricardo and Ju{\'a}rez-Hern{\'a}ndez, Luis Gibran and Monge-Rogel, Ricardo},
  title     = {EEAI-Chile: Data and code for the design and initial validation of a
               comprehensive academic engagement scale for Chilean university faculty},
  year      = {2026},
  publisher = {GitHub},
  url       = {https://github.com/<USERNAME>/EEAI-Chile-Validation}
}
```

Citation metadata is also provided in [`CITATION.cff`](CITATION.cff) (use GitHub's "Cite this repository" button).

## Authors

| Author | Affiliation | Role |
|--------|-------------|------|
| **Ricardo Fuentes-Lama** | Facultad de Economía y Negocios, Universidad Andrés Bello, Chile | <!-- ORCID: 0000-0000-0000-0000 --> Corresponding author <!-- email --> |
| **Luis Gibran Juárez-Hernández** | Centro Universitario CIFE, México | <!-- ORCID --> |
| **Ricardo Monge-Rogel** | Instituto de Matemática, Física y Estadística, Universidad de Las Américas, Chile | <!-- ORCID --> |

## License

- **Code** (notebooks, scripts): [MIT License](LICENSE)
- **Data** (`data/`): [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)

## Acknowledgments

We thank the expert judges and the university faculty who participated in the pilot study.
