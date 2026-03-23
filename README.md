# grossman-data

Public data repository for the [grossman](https://github.com/a-torgovitsky/grossman) R package.

## Contents

| Dataset | Description | Rows | Cols | Variants |
|---------|-------------|------|------|----------|
| `cps` | IPUMS CPS wage data (Blau & Kahn 2017 sample) | 48371 | 16 | |
| `eskom` | Dinkelman (2011) electrification data | 1816 | 18 | |
| `psid` | Blundell, Pistaferri, & Preston (2008) earnings & consumption | 4566 | 12 | `unbalanced` |
| `tenncare` | Garthwaite, Gross, & Notowidigdo (2014) DiD | 136 | 29 | `micro` |

## Data Format

Each dataset is distributed as two files:

- **`{name}.rds`** — R data file with variable labels embedded as column attributes. R users get labels automatically via `attr(df$column, "label")`.
- **`{name}.json`** — JSON metadata file mapping variable names to human-readable labels. Useful for non-R users or for quick reference.

