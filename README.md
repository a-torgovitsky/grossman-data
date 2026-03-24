# grossman-data

Public data repository for the [grossman](https://github.com/a-torgovitsky/grossman) R package.

## Contents

| Dataset | Description | Rows | Cols | Variants |
|---------|-------------|------|------|----------|
| `bureaucrats` | He & Wang (2017) village officials in China | 2809 | 18 | |
| `childpen` | Cortés & Pan (2023) child penalty panel | 54365 | 12 | |
| `cigs` | Abadie, Diamond, & Hainmueller (2010) cigarette sales panel | 1209 | 7 | |
| `cookstove` | Berkouwer & Dean (2022) cookstove adoption | 7949 | 7 | |
| `cps` | IPUMS CPS wage data (Blau & Kahn 2017 sample) | 48371 | 16 | |
| `eskom` | Dinkelman (2011) electrification data | 1816 | 18 | |
| `hurricane` | Deryugina (2017) hurricane fiscal costs | 49698 | 7 | |
| `kenyagrid` | Lee, Miguel, & Wolfram (2020) rural electrification RCT | 4368 | 52 | |
| `kindy` | Gelbach (2002) kindergarten & maternal labor supply | 17817 | 23 | |
| `olyset` | Dupas (2014) bed net pricing experiment | 1078 | 4 | |
| `pisa` | Gneezy et al. (2019) test score incentive experiment | 1103 | 21 | |
| `psid` | Blundell, Pistaferri, & Preston (2008) earnings & consumption | 4566 | 12 | `unbalanced` |
| `queens` | Dube & Harish (2020) monarchs and wars | 3586 | 17 | |
| `redistribution` | Alesina, Stantcheva, & Teso (2018) mobility & redistribution | 9792 | 105 | |
| `reservations` | Dippel (2014) Native American reservations | 182 | 19 | |
| `tenncare` | Garthwaite, Gross, & Notowidigdo (2014) DiD | 136 | 29 | `micro` |
| `thirdkid` | Angrist & Evans (1998) family size & labor supply | 254652 | 34 | |
| `unions` | Vella & Verbeek (1998) union wage panel | 4360 | 36 | |
| `widows` | Dillon & Voena (2018) land inheritance in Zambia | 7825 | 16 | |

## Data Format

Each dataset is distributed as two files:

- **`{name}.rds`** — R data file with variable labels embedded as column attributes. R users get labels automatically via `attr(df$column, "label")`.
- **`{name}.json`** — JSON metadata file mapping variable names to human-readable labels. Useful for non-R users or for quick reference.

