# DSA 405 Movie ROI Project

This project examines whether movies with higher-profile actors have different returns on investment after accounting for production budget.

The project uses movie data for films released from 2000 through 2025.

## Data

The movie data was collected from The Movie Database (TMDB) API. The raw data includes information such as movie IDs, titles, release dates, genres, production budgets, box-office revenue, and cast information.

Source information is documented in `data/raw/SOURCES.md`.

The original raw dataset, `tmdb_raw.json`, is approximately 433 MB and exceeds GitHub's 100 MB file-size limit. Following instructor guidance, the raw file is submitted separately with the assignment rather than uploaded to this repository.

The TMDB API key used to originally collect the data is private and is not included in this repository.

## How to Run

1. Download the submitted `tmdb_raw.json` file.
2. tmdb_raw.json is submitted separately because it exceeds GitHub's 100 MB file limit. Place the file in the same directory as the notebook before running it
3. Open the project notebook in Jupyter Notebook or Google Colab.
4. Navigate to and select the cell that is labeled "TO RUN FULL NOTEBOOK START HERE", select "Run" and then "Run selected cells and all cells below". The notebook can't be ran from top to bottom because a secret API key is used. 

The notebook begins with the preserved raw TMDB data and performs the audit, cleaning, and creation of the variables used for the analysis.
