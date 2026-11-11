# Spotify Music Data Pipeline — Time-Series Analysis

End-to-end data pipeline for the Spotify music dataset: ingestion, cleaning,
warehousing and time-series analysis. A modern rebuild of the original
two-phase university project (`Spotify-Music-Analysis-and-Classification-Algorithms`),
reframed from a machine-learning notebook into a data engineering pipeline —
ingest once, model in the warehouse, analyse over time.

## What it does

| Stage | What happens |
|---|---|
| Extract | Reads the Spotify track dataset (audio features, genre, popularity, release date) from `data/raw/` |
| Transform | Removes outliers, normalises audio features, imputes missing values, derives time-series features (rolling popularity, trend) |
| Load | Loads cleaned tracks into a PostgreSQL star schema (`fact_tracks`, `dim_artist`, `dim_genre`, `dim_date`) |
| Quality | Null, duplicate and range checks on every load — the pipeline fails if a check fails |
| Analyse | Time-series analysis of popularity over time; genre classification as the Gold-layer output |

Results from the original analysis, kept as the Gold-layer output:
- **Genre classification (k-NN): ~58.5% accuracy**; clustering silhouette **0.452** (DBSCAN)
- **Popular vs non-popular (XGBoost): 97.1% accuracy**
- **Rule-based classification: 96% binary accuracy** (e.g. Sleep genre)

## Architecture

```
data/raw/spotify.csv
      │  extract.py
      ▼
data/staging/ (cleaned parquet)
      │  transform.py
      ▼
PostgreSQL (sql/schema.sql — star schema)
      │  load.py
      ▼
models/ (staging → marts, SQL)
      ▼
analysis.py — time-series + classification
```

## Quick start

```bash
# 1. Place the Spotify dataset in data/raw/ (see data/README.md)
cp spotify.csv data/raw/

# 2. Start PostgreSQL
docker compose up -d postgres

# 3. Install dependencies
pip install -r requirements.txt

# 4. Run the whole pipeline
python -m src.run_pipeline

# 5. Run the time-series analysis
python -m src.analysis
```

Or run everything in Docker:

```bash
docker compose up --build
```

## Project structure

```
├── README.md
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
├── .env.example
├── src/
│   ├── config.py
│   ├── extract.py
│   ├── transform.py
│   ├── load.py
│   ├── data_quality.py
│   ├── analysis.py
│   └── run_pipeline.py
├── sql/
│   └── schema.sql
├── models/
│   ├── staging_tracks.sql
│   └── mart_genre_popularity.sql
├── tests/
│   └── test_data_quality.py
├── data/
│   └── README.md
└── .github/workflows/ci.yml
```

## How this maps to my experience

This is the project behind **Advanced Data Mining & Time-Series Analysis on
Spotify Dataset** on my CV (Oct 2024 – Dec 2025). The
rebuild adds the engineering the original lacked: a real warehouse, scheduled
loads, data-quality gates, and a time-series layer a BI tool can read.

## Tech

Python · SQL · PostgreSQL · pandas · scikit-learn · XGBoost · Docker ·
Power BI
