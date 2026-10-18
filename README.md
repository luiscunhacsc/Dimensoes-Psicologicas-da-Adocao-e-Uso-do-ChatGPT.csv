# Dimensões Psicológicas da Adoção e Uso do ChatGPT

Portuguese-language survey data about the psychological dimensions of adopting and using ChatGPT. The questionnaire covers usage habits, perceptions of the technology, social and emotional experiences, and expectations about its role in professional life.

## Repository contents

| File | Description |
| --- | --- |
| [Dimensões Psicológicas da Adoção e Uso do ChatGPT.csv](Dimens%C3%B5es%20Psicol%C3%B3gicas%20da%20Ado%C3%A7%C3%A3o%20e%20Uso%20do%20ChatGPT.csv) | Survey responses, with the original Portuguese questions as column headers. |

The repository currently contains the dataset; analysis scripts, scoring instructions, and study methodology are not included.

## Dataset structure

The CSV contains **142 response records and 74 columns**, excluding the header row. All response records have 74 fields.

| Columns (1-based) | Content |
| --- | --- |
| 1–10 | Timestamp, consent, demographic and professional background, country of residence, and a spam-check question. |
| 11–14 | Frequency, weekly hours, intensity, and purposes of ChatGPT use. |
| 15–54 | 40 statements about usability, usefulness, trust, communication, emotional support, privacy, dependence, agency, and perceived personal or social effects. |
| 55–74 | 20 statements about professional productivity, creativity, adaptation, employment, ethics, inequality, collaboration, and future expectations. |

These groups describe the order and topics of the questions; they are not a documented scoring model or validated subscales.

## Open the data

In Excel, LibreOffice Calc, or another spreadsheet application, import the file using **UTF-8** encoding, a **comma** delimiter, and a **double quote** text qualifier.

For Python 3, the standard library is sufficient. Run this example from the repository root:

```python
import csv
from pathlib import Path

path = Path("Dimensões Psicológicas da Adoção e Uso do ChatGPT.csv")

with path.open(encoding="utf-8", newline="") as file:
    reader = csv.DictReader(file)
    columns = reader.fieldnames
    responses = list(reader)

print(f"Responses: {len(responses)}")
print(f"Columns: {len(columns)}")
```

Expected output for the current dataset:

```text
Responses: 142
Columns: 74
```

## Working with the data

- Use a CSV parser: the spam-check column header contains embedded line breaks, so physical line counts do not equal response counts.
- Preserve the original headers when loading the file. Some contain leading or trailing whitespace; normalize them explicitly if an analysis requires it.
- Review the consent and spam-check fields, missing values, and response formats before selecting records for analysis. The record count above does not imply that responses have passed these checks.
- Establish response coding and any reverse-scoring rules before calculating composite scores. The repository does not supply a codebook or scale anchors.
- The questions capture self-reported experiences and beliefs. They do not by themselves establish causal effects of ChatGPT use.

## Source and reuse

The repository does not currently document authorship, recruitment, sampling methods, or a license. Consent wording and permissions for redistribution are also not documented here. The dataset includes timestamps, demographic information, and personal survey responses; any shared analysis should take those details into account.
