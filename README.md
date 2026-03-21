# grossman-data

Public data repository for the [grossman](https://github.com/a-torgovitsky/grossman) R package.

## Contents

| File | Dataset | Rows | Cols |
|------|---------|------|------|
| `cps.parquet` | IPUMS CPS wage data (Blau & Kahn 2017 sample) | 48371 | 16 |
| `eskom.parquet` | Dinkelman (2011) electrification data | 1816 | 18 |
| `example_wages.parquet` | Simulated wage data | 50 | 8 |

## How It Works

1. Cleaning scripts in a private workspace produce `.parquet` files
2. Files are copied here via `publish_to_dinner()`
3. The `grossman` R package fetches from raw.githubusercontent.com URLs
4. Data is cached locally on students' machines after first download

## URL Pattern

```
https://raw.githubusercontent.com/a-torgovitsky/grossman-data/main/data/{filename}.parquet
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
