# DSA 405 Movie ROI Project

This project examines whether movies with higher-profile actors have different returns on investment after accounting for production budget.

The project uses movie data for films released from 2000 through 2025.

## Data

The project uses movie data from The Movie Database (TMDB) API and ratings data from IMDb.

The TMDB data includes information such as movie IDs, IMDb IDs, titles, release dates, genres, production budgets, box-office revenue, and cast information. The cleaned TMDB dataset used for P3 is stored in data/clean/tmdb_clean.json.

IMDb ratings data is retrieved from IMDb's official downloadable dataset at https://datasets.imdbws.com/title.ratings.tsv.gz. The raw IMDb file is saved to data/raw/title.ratings.tsv.gz and contains IMDb title IDs, average ratings, and number of votes.

Source information is documented in data/raw/SOURCES.md.

The original raw TMDB dataset, tmdb_raw.json, is approximately 433 MB and exceeds GitHub's 100 MB file-size limit. Following instructor guidance, the raw file is submitted separately with the assignment rather than uploaded to this repository.

The TMDB API key used to originally collect the data is private and is not included in this repository.

## How to Run

### P2

1. Download the separately submitted `tmdb_raw.json` file.
2. Place `tmdb_raw.json` in the `data/raw/` folder so that the full path is:

   `data/raw/tmdb_raw.json`

3. Open the project notebook in Jupyter Notebook.
4. Restart the kernel.
5. Run the notebook from top to bottom.

The notebook includes the original TMDB API collection code to document how the raw dataset was created. This code is disabled by default with `RUN_SCRAPE = False`, so the notebook does not require a TMDB API key when run normally.

The notebook loads the preserved raw dataset from `data/raw/tmdb_raw.json` and then performs the data audit, cleaning, and creation of the variables used for the analysis.

The notebook does not write to or modify files inside `data/raw/`.

The notebook begins with the preserved raw TMDB data and performs the audit, cleaning, and creation of the variables used for the analysis.

### P3

1. Make sure the cleaned TMDB dataset is available at:

   `data/clean/tmdb_clean.json`
   
2. Open the P3 notebook in Google Colab.

3. Restart the runtime.

4. Run the notebook from top to bottom.

The notebook creates the required `data/raw/` and `data/clean/` folders if they do not already exist.

The IMDb ratings dataset is downloaded from IMDb's official downloadable dataset and saved to:

`data/raw/title.ratings.tsv.gz`

If the IMDb raw file already exists, the notebook uses the cached copy instead of downloading the same resource again.

The cleaned TMDB dataset is loaded from `data/clean/tmdb_clean.json` and joined with the IMDb ratings dataset using TMDB `imdb_id` and IMDb `tconst`.

The final integrated dataset contains 5,810 rows and is saved as:

`data/clean/movie_data.csv`

The notebook includes validation checks to confirm that the join preserves the expected row count and that important values in the final dataset remain valid.
