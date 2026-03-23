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

## How It Works

1. Cleaning scripts in a private workspace produce `.rds` + `.json` files
2. Files are copied here via `publish_to_dinner()`
3. The `grossman` R package fetches `.rds` files from raw.githubusercontent.com URLs
4. Data is cached locally on students' machines after first download

## URL Pattern

```
https://raw.githubusercontent.com/a-torgovitsky/grossman-data/main/data/{name}.rds
```

## For Maintainers

To add a new dataset:

1. Clean data in the private workspace (`kitchen/scripts/`)
2. Run `publish_to_dinner("dataset_name")` in R
3. Commit and push:
   ```bash
   git add data/
   git commit -m "Add {dataset_name}"
   git push
   ```
4. Update documentation in the grossman package

## Rate Limits

GitHub's CDN has generous rate limits. For typical class sizes (< 200 students), you won't hit issues since each student downloads once (cached locally).
