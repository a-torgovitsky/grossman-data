# Dinner: Public Data Repository

This repository hosts the cleaned datasets that students download via the `grossman` package.

## Structure

```
dinner/
├── data/           # Parquet/RDS files served to students
│   ├── labor_data.parquet
│   └── ...
└── README.md
```

## How It Works

1. Cleaning scripts in `kitchen/` produce `.parquet` files
2. Files are copied here via `publish_to_dinner()`
3. This repo is public on GitHub
4. The `grossman` package fetches from raw.githubusercontent.com URLs

## Adding a New Dataset

1. Clean the data in `kitchen/scripts/`
2. Run `publish_to_dinner("dataset_name")` to copy here
3. Commit and push this repo
4. Update `grossman/inst/manifest.csv` with the new dataset

## URL Pattern

Files are served at:
```
https://raw.githubusercontent.com/{username}/dinner/main/data/{filename}.parquet
```

Update the `DINNER_BASE_URL` in `grossman/R/config.R` to match your GitHub username.

## Rate Limits

GitHub's raw.githubusercontent.com CDN has generous rate limits. For a typical class size (< 200 students), you should never hit issues. Each student only downloads once due to local caching.

If you do hit limits, consider:
- GitHub Releases (attach files as release assets)
- A simple static file server
- Cloudflare R2 or similar (free egress)
