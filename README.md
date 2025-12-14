# Real-World Crime Analytics for the London Metropolitan Area

This project analyses crime patterns in London using real-world data from the UK Police API combined with socio-economic (income), population, and spatial (LSOA/MSOA map) datasets. The workflow is implemented as a single Jupyter notebook that:

- Ingests raw source datasets (downloads + extracts)
- Cleans and standardizes them with Apache Spark
- Writes cleaned data to `Datasets/Cleaned-Data/`
- Runs analytical Spark SQL queries to produce summary tables (e.g., by year, by location)

## Notebook (main pipeline)

- Run the notebook in order: [main.ipynb](main.ipynb)
- Cell-by-cell explanation (very detailed): [NOTEBOOK_README.md](NOTEBOOK_README.md)

### Important notes before running

- Some early notebook cells run system package commands (e.g., `apt`) and may require `sudo`.
- Download steps require internet access and enough disk space (police data ZIP + extracted monthly folders).
- The notebook uses Spark locally (`master("local[*]")`). If you run in a constrained environment, Spark jobs may be slow.

## Repository structure (high level)

- `Datasets/Raw-Data/`: downloaded source files
- `Datasets/Data-for-Cleaning/`: subset/copies of raw files used for cleaning
- `Datasets/Cleaned-Data/`: cleaned and transformed outputs (CSV/Parquet)
- `requirements.txt`: Python dependencies

## How to use (quick start)

1. Open [main.ipynb](main.ipynb)
2. Execute cells from top to bottom
3. Review outputs in the notebook and the generated datasets under `Datasets/Cleaned-Data/`
