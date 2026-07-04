# Data documentation

All datasets are shared under a **CC BY 4.0** license. Please cite the repository (see root `README.md` / `CITATION.cff`) when reusing them.

## 1. `expert_judgment/data_aiken_engagement.csv`

Expert-judgment ratings used for the content-validity analysis (Aiken's V).

| Variable | Type | Description |
|----------|------|-------------|
| `dimension` | string | Rating criterion: `relevance` or `wording` (pertinencia / redacción) |
| `item01`–`item31` | integer (1–4) | Rating assigned by each judge to each of the 31 initial items on a 4-point ordinal scale (1 = lowest, 4 = highest) |

Each row is one judge × one criterion. Aiken's V is computed per item and criterion with 95% confidence intervals (score method).

## 2. `expert_judgment/sociodemographic_judges.csv`

Characteristics of the expert panel (one row per judge). Contains no direct identifiers.

| Variable | Type | Description |
|----------|------|-------------|
| `sexo` | string | Gender (`Femenino` / `Masculino`) |
| `grado_academico` | string | Highest academic degree |
| `Area_OCDE` | string | OECD (Frascati Manual) field of science |
| `experiencia_profesional` | string | Main professional role (e.g., researcher, director, academic) |
| `anios_experiencia` | integer | Years of professional experience |
| `exp_valid_inst` | string | Prior experience in instrument validation (`SI` / `NO`) |

## 3. `pilot/EEAI-Chile_Pilot_Data_2026_anonymized.xlsx`

Anonymized pilot survey responses (**N = 104** Chilean university faculty; Google Forms export, one sheet, one row per respondent). Column *positions* are preserved from the original export because the analysis notebooks select variables by position.

Key columns (0-based position, as used by the notebooks):

| Position | Content |
|----------|---------|
| 0 | `participant_id` (P001–P104; replaces original timestamps — see anonymization below) |
| 1 | Informed-consent confirmation (constant acceptance string) |
| 2 | Institution — **values removed** for anonymization (empty column retained to preserve positions) |
| 3–15 | Sociodemographic / professional variables: contract type, weekly teaching hours, working regime, OECD field (Frascati), years of experience, degree, gender, age, research activity, management role, marital status, children, MacArthur subjective status ladder |
| 16–44 | The 29 EEAI-Chile items (5-point Likert, 1–5), in dimension order: D1 (16–20), D2 (21–25), D3 (26–29), D4 (30–34), D5 (35–39), D6 (40–44) |
| 45 | Open-text suggestions — **values removed** for anonymization |
| 46–49 | Participants' evaluation of the instrument (instructions clarity, item clarity, satisfaction, relevance) |
| 50–52 | Tenure at current institution (years), faculty-development participation, perceived job security |
| 53–56 | Duplicated form columns (empty; retained to preserve positions) |

### Anonymization procedure

The public dataset was de-identified before publication:

1. **Timestamps** of form submission were replaced with sequential participant IDs (`P001`–`P104`).
2. **Institution names** (column 2) were deleted.
3. **Open-text comments** (column 45) were deleted.
4. No names, emails, or other direct identifiers were collected by the form.

Remaining variables (age, gender, discipline, contract type, etc.) are retained at their original granularity because, with institutional affiliation removed, the residual re-identification risk in a national population of university faculty is considered very low. The original (non-anonymized) export is **not** distributed and is excluded from version control (see `.gitignore`).
