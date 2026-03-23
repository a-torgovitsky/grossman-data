# grossman-data

Public data repository for the [grossman](https://github.com/a-torgovitsky/grossman) R package.

## Contents

| Dataset | Rows | Cols | Files |
|---------|------|------|-------|
| `cps` — IPUMS CPS wage data (Blau & Kahn 2017 sample) | 48371 | 16 | `.rds` `.json` |
| `eskom` — Dinkelman (2011) electrification data | 1816 | 18 | `.rds` `.json` |
| `example_wages` — Simulated wage data | 50 | 8 | `.rds` `.json` |
| `psid` — Blundell, Pistaferri, & Preston (2008) balanced panel | 4566 | 12 | `.rds` `.json` |
| `psid_unbalanced` — PSID unbalanced panel (variant) | 10370 | 12 | `.rds` `.json` |
| `tenncare` — Garthwaite, Gross, & Notowidigdo (2014) DiD | 136 | 29 | `.rds` `.json` |
| `tenncare_micro` — TennCare individual-level (variant) | 454260 | 28 | `.rds` `.json` |

## Data Format

Each dataset is distributed as two files:

- **`{name}.rds`** — R data file with variable labels embedded as column attributes. R users get labels automatically via `attr(df$column, "label")`.
- **`{name}.json`** — JSON metadata file mapping variable names to human-readable labels. Useful for non-R users or for quick reference.

