# SpaceX Falcon 9 First-Stage Landing Prediction

## Project overview

This repository contains the notebooks and lab instructions for the capstone project in the IBM Data Science Professional Certificate. The project investigates whether the first stage of a Falcon 9 launch will land successfully. Since SpaceX reuses first-stage boosters, launch and landing data can be used to explore factors associated with successful landings and to train classification models.

The work follows a data-science workflow: collect and scrape data, clean and explore it, query it with SQL, visualize launch sites and trends, and evaluate machine-learning classifiers. The dashboard lab instructions describe an additional interactive analysis using Plotly Dash.

## Project workflow and files

Run the notebooks in the order below. Some notebooks use datasets hosted by IBM Skills Network, and the collection notebooks access the SpaceX API and Wikipedia, so an internet connection may be required.

| # | Notebook or resource | What it covers |
|---|---|---|
| 1 | [Collect SpaceX data from the API](./1_jupyter-labs-spacex-data-collection-api.ipynb) | Requests launch and related rocket, launchpad, payload, and core data from the SpaceX API; filters for Falcon 9 launches and prepares fields for analysis. |
| 2 | [Scrape launch records](./2_jupyter-labs-webscraping.ipynb) | Uses `requests` and BeautifulSoup to parse Falcon 9 and Falcon Heavy launch records from a Wikipedia table. |
| 3 | [Wrangle launch data](./3_labs-jupyter-spacex-Data%20wrangling.ipynb) | Examines launches by site, orbit, and mission outcome, then creates the binary landing-success target used in later analysis. |
| 4 | [Explore data with SQL](./4_jupyter-labs-eda-sql-coursera_sqllite.ipynb) | Loads launch data into SQLite and uses SQL queries to investigate launch sites, payload mass, booster versions, landing outcomes, and launch trends. |
| 5 | [Exploratory data analysis and visualization](./5_eda_data_viz.ipynb) | Visualizes relationships among flight number, payload mass, launch site, orbit, success, and year; prepares categorical features for modeling. |
| 6 | [Map launch-site locations with Folium](./6_lab_jupyter_launch_site_location.ipynb) | Builds an interactive map with launch-site markers and launch outcome information to explore the geographic distribution of launches. |
| 7 | [Predict landing outcomes with machine learning](./7_SpaceX_Machine%20Learning%20Prediction_Part_5.ipynb) | Trains and evaluates logistic regression, support vector machine, decision tree, and k-nearest-neighbors classifiers, including parameter tuning and confusion-matrix evaluation. |
| — | [Dashboard instructions](./Dashboard_Instructions.md) | Guides the creation of a Plotly Dash dashboard with a launch-site selector, success-rate pie chart, payload-range slider, and payload-versus-outcome scatter plot. |

## Interactive dashboard

The dashboard lab is intended to help answer questions such as which launch site has the most successful launches, which site or payload range has the highest or lowest success rate, and how success varies by Falcon 9 booster version.

`Dashboard_Instructions.md` is a lab guide. It describes downloading the dataset and a starter Dash application in the lab environment; the starter application and dashboard dataset are not included as standalone project files in this repository.

## Data and target

The notebooks use SpaceX launch information from the SpaceX API, launch-history tables scraped from Wikipedia, and prepared CSV datasets hosted by IBM Skills Network. The analysis combines launch dates, sites, payload masses, orbits, booster attributes, and landing outcomes.

For the classification work, the landing outcome is represented as a binary target: successful landing (`1`) or unsuccessful landing (`0`). The notebooks prepare and explore these data before using them to fit and compare classification models.

## Tools and libraries

The project uses Python and Jupyter notebooks, with libraries and tools including:

- `requests`, `BeautifulSoup`, and `pandas` for data collection, web scraping, and tabular analysis
- `sqlite3` for SQL-based exploration
- `NumPy`, `Matplotlib`, and `Seaborn` for data preparation and visual analysis
- `Folium` for interactive maps
- `scikit-learn` for model training and evaluation
- `Plotly Dash` for the dashboard lab

Install the libraries required by the notebooks in your Python environment before running them. For example:

```bash
python -m pip install requests beautifulsoup4 pandas numpy matplotlib seaborn folium scikit-learn dash plotly
```

`sqlite3` is included with Python. Depending on your Jupyter setup, you may also need to install or enable a Jupyter kernel.

## Running the project

1. Clone or download this repository and open it in Jupyter Notebook or Visual Studio Code with the Jupyter extension.
2. Install the required Python libraries and select the intended Python kernel.
3. Run the notebooks in the workflow order above. Review each notebook's data-source URLs and follow its cells from top to bottom.
4. To complete the dashboard lab, follow [Dashboard_Instructions.md](./Dashboard_Instructions.md) in an environment where the starter application and CSV dataset can be downloaded.

Some notebooks create local analysis artifacts, such as the SQLite database used for SQL exercises. Results may depend on the availability and contents of remote APIs and datasets.

## Presentation

A presentation summarizing the analysis and results is part of the project deliverables described in the notebooks and dashboard lab. No presentation file is currently included in this repository.
