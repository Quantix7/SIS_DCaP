# Performance vs Fan Attendance in the Premier League

**SIS Project — Data Collection & Preparation**  
**Kazakh-British Technical University (KBTU)**  
**Season:** 2024–2025 English Premier League

## Project Overview

This project explores the relationship between **average home attendance** and **football club performance** in the 2024–2025 Premier League season.

The main research question is: **Do clubs with more fans attending home matches achieve better league results?**

The analysis covers all **20 Premier League clubs** and compares attendance with total points, wins, goal difference, and final league position.

## Data Sources

Data was collected from two different sources:

1. **Football-data.org API** — final league standings, matches played, wins, draws, losses, goals, and points.  
   Endpoint: `https://api.football-data.org/v4/competitions/PL/standings?season=2024`
2. **Wikipedia (web scraping)** — average home attendance and number of home games for each club.  
   Page: [2024–25 Premier League](https://en.wikipedia.org/wiki/2024%E2%80%9325_Premier_League)

## Technologies Used

- Python
- pandas
- requests
- BeautifulSoup (bs4)
- Matplotlib
- Seaborn
- Jupyter Notebook

## Project Workflow

1. Retrieve the 2024–2025 standings using the Football-data.org API.
2. Scrape the attendance table from Wikipedia with `requests` and `BeautifulSoup`.
3. Check missing values, remove duplicates, validate data types, and standardize club names.
4. Merge both datasets by club name.
5. Perform exploratory data analysis (EDA) and calculate Pearson correlations.
6. Visualize attendance and performance using five charts.

## Key Findings

| Comparison | Pearson correlation |
| --- | ---: |
| Average attendance vs. league points | +0.206 |
| Average attendance vs. wins | +0.228 |
| Average attendance vs. league position | −0.197 |
| Average attendance vs. goal difference | +0.269 |

- **Manchester United** had the highest average home attendance (**73,747**), but finished **15th**.
- **Liverpool** won the league while averaging **60,330** home spectators.
- **AFC Bournemouth** had the lowest average attendance (**11,214**), yet finished **9th**.

**Conclusion:** Average home attendance shows only a **weak relationship** with league performance in this season. These correlations do not demonstrate that attendance causes better or worse results.

## How to Run

1. Download or clone this repository.
2. Install the required libraries:

   ```bash
   pip install pandas requests beautifulsoup4 matplotlib seaborn
   ```

3. Open `SIS_PremierLeague_Attendance.ipynb` in Jupyter Notebook or Google Colab.
4. Run the cells in order. When prompted, enter your **Football-data.org API key** (required to access the API).

   > **Security:** Never paste your API key into a notebook cell or commit it to GitHub. The notebook uses `getpass` to request the key securely at runtime.

5. Review the cleaned dataset, summary statistics, and visualizations.

**Note:** Access to the historical 2024–2025 season may depend on your Football-data.org API plan. The notebook reports an error if the required data cannot be retrieved.

## Repository Contents

| File | Description |
| --- | --- |
| `SIS_PremierLeague_Attendance.ipynb` | Data collection, cleaning, merging, analysis, and charts |
| `report_Abdikhamitov.pdf` | Short written project report |
| `README.md` | Project overview and instructions |
| `requirements.txt` | Optional dependency list |

Running the notebook also saves the cleaned dataset as `premier_league_attendance_performance_2024_25.csv` and exports chart images as PNG files.

## Limitations

The analysis uses **one season** and **average club-level home attendance**, not actual attendance for each individual match. Other factors such as stadium capacity, team budget, and squad quality were not controlled for. Therefore, the findings describe associations rather than causal effects.
