# Netflix Data Analysis 🎬

Exploratory data analysis and sentiment analysis on the Netflix titles dataset using Python and Google Colab. The project examines content distribution, top talent, release trends, and the emotional tone of show/movie descriptions across the catalog.

---

## Overview

This project works with a dataset of 8,807 Netflix titles to answer questions about what kind of content Netflix offers, who dominates the platform as directors and actors, how content volume has grown over the years, and what sentiment Netflix uses to market its titles through descriptions.

---

## Dataset

**Source:** [Netflix Movies and TV Shows – Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows)

**Shape:** 8,807 rows × 12 columns

| Column | Description |
|---|---|
| `show_id` | Unique identifier |
| `type` | Movie or TV Show |
| `title` | Title of the content |
| `director` | Director(s) |
| `cast` | Cast members |
| `country` | Country of production |
| `date_added` | Date added to Netflix |
| `release_year` | Original release year (ranges from 1925 to 2021) |
| `rating` | Content rating (17 unique values, e.g. TV-MA, TV-14, PG-13) |
| `duration` | Runtime in minutes or seasons |
| `listed_in` | Genres |
| `description` | Short synopsis used for sentiment analysis |

---

## Tech Stack

| Library | Purpose |
|---|---|
| Pandas | Data loading, cleaning, and manipulation |
| NumPy | Numerical operations |
| Matplotlib | Visualization |
| Seaborn | Statistical charts |
| Plotly Express | Interactive charts (pie, bar, line) |
| TextBlob | Sentiment polarity scoring on descriptions |
| Google Colab | Development environment |

---

## Analysis & Key Findings

**Content Ratings Distribution**

Plotted a pie chart of all 17 rating categories. TV-MA leads with 3,207 titles, followed by TV-14 (2,160) and TV-PG (863) — indicating Netflix's catalog skews heavily toward mature and teen audiences.

**Top Directors on Netflix**

After handling missing director values and exploding multi-director entries, Rajiv Chilaka ranks #1 with 22 titles, followed by Jan Suter (21) and Raúl Campos (19).

**Top Actors on Netflix**

Applied the same approach to the cast column across 8,807 entries. Anupam Kher leads with 39 appearances, followed by Rupa Bhimani (31), Takahiro Sakurai (30), Julie Tejwani (28), and Om Puri (27).

**Content Trends Over Time (2000–2021)**

A line chart comparing Movies vs. TV Shows by release year shows both categories growing sharply from 2012 onward, with Movies peaking at 767 titles in both 2017 and 2018, and TV Shows peaking at 436 in 2020. Both types saw a decline in 2021, likely reflecting the dataset's cutoff date rather than an actual drop.

**Sentiment Analysis of Descriptions**

Used TextBlob to classify each title's description as Positive, Neutral, or Negative based on polarity score. Across all years (filtered to post-2005), Positive sentiment consistently dominates — Netflix tends to frame its content in an optimistic or adventurous tone in descriptions, regardless of the actual genre or content rating.

---

## Visualizations

The notebook produces five interactive Plotly charts:

- Pie chart — distribution of content ratings
- Horizontal bar chart — top 5 directors by title count
- Horizontal bar chart — top 5 actors by appearance count
- Line chart — Movies vs. TV Shows released per year (2000–2021)
- Stacked bar chart — sentiment breakdown (Positive / Neutral / Negative) by release year (2006–2021)

---

## Data Cleaning Steps

- Missing `director` values filled with `'Director not specified'` and excluded from director analysis
- Missing `cast` values filled with `'Cast not specified'` and excluded from actor analysis
- Multi-value fields (`director`, `cast`) split and exploded into individual rows before grouping
- Release year filtered to post-2000 for trend analysis and post-2005 for sentiment analysis to focus on the period with meaningful data volume

---

## How to Run

1. Clone the repository
   ```bash
   git clone https://github.com/your-username/netflix-data-analysis.git
   ```

2. Open `NetflixAnalysis.ipynb` in [Google Colab](https://colab.research.google.com/) or Jupyter

3. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows) and upload `netflix_titles.csv` to your Colab session

4. Install any missing dependencies
   ```bash
   pip install textblob plotly
   ```

5. Run all cells in order

---

## Project Structure

```
netflix-data-analysis/
│
├── NetflixAnalysis.ipynb    # Main analysis notebook
├── netflix_titles.csv       # Dataset (download from Kaggle)
└── README.md
```

---

## Acknowledgements

- Dataset by [Shivam Bansal](https://www.kaggle.com/shivamb) on Kaggle
- Project built following a guided tutorial, independently implemented in Google Colab

---

## License

This project is open source under the [MIT License](LICENSE).
