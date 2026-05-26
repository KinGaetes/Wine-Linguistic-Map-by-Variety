# Wine Variety Language Analysis Portfolio

This repository is a portfolio-ready export of a wine review language analysis project. It studies how wine varieties are described in tasting notes and prepares the data needed for a future web app.

## Project intent

The work has two goals: show a reproducible data analysis workflow for portfolio use, and prepare the foundation for an HTML/CSS/JS app that lets users explore wine varieties, descriptors, radial comparisons and local maps.

## Main files

- `wine_variety_language_analysis_portfolio.ipynb`: notebook with Markdown explanations and code cells.
- `wine_variety_language_analysis_portfolio.html`: bilingual HTML version with Spanish/English toggle.
- `app/data/wine_variety_language_profiles.json`: compact derived payload for the future app.
- `app/figures/full_local_word_map.png`: high resolution local map example.
- `requirements.txt`: Python dependencies.
- `DATASETS.txt`: expected raw CSV files and GitHub size notes.

## Data note

The raw CSV files are not included because one file is larger than GitHub's 100 MB file limit. Place the CSV files in the project root before running the notebook locally.

## How to read the visual work

Bar charts compare how strongly a word appears in different varieties. Radial charts compare several varieties or several words at once. Local maps place wines and descriptors in a shared space where closer items use more similar tasting language.

## Next step

The exported JSON is intended to power a simple web app where users can select varieties, choose descriptor words from the generated dictionary and navigate the wine matrix interactively.

## Interactive portfolio HTML

The HTML export includes visible test charts and an interactive canvas map. The map contains all analyzed varieties and all descriptor words with more than 1% global review presence. Users can pan, zoom, search and inspect each point.
