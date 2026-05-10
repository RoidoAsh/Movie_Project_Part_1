# Movie_Project_Part_1
# 🎬 IMDb & Wikipedia Movie Data Scraper (Top 5,000 Movies)

I developed a Python-based data engineering project that builds a comprehensive, enriched movies dataset. This project extracts the top 5,000 most popular movies from IMDb and enriches them dynamically with financial data, language, country, and plot summaries retrieved from **Wikipedia** and the **OMDb API**.

---

## 📌 Data Collection Methodology (שיטת האיסוף)

I constructed and executed the data pipeline using Python through the following steps:

* **Target Population & Sampling:** I extracted the top 5,000 most popular movies from IMDb based on user engagement, filtering by the number of votes (`numVotes`).
* **Metadata Enrichment (OMDb API):** For each movie, I performed an API call to OMDb to dynamically retrieve the movie's plot summary.
* **Financials & Background Enrichment (Wikipedia Web Scraping):** I developed a custom web scraper using `BeautifulSoup` and `requests`. The scraper searches Wikipedia for each movie's dedicated page, locates the structured Infobox, and extracts the production budget, worldwide box office revenue, language, and country of origin.
* **Crash-Resilience & Efficiency:** I implemented an incremental saving mechanism (writing to the CSV every 50 movies) and smart skip-logic to allow resuming from the exact stopping point without duplicate server requests.

---

## 🚀 How to Run the Project (הוראות הרצה)

Follow these steps to run the pipeline on your machine:

### 1. Prerequisites (דרישות קדם)
Make sure you have Python installed, along with the required libraries. You can install them by running:

pip install pandas beautifulsoup4 requests

### 2. Execution (הרצה)
1. Download all the files from this repository to your local computer.
2. Open the Jupyter Notebook / Google Colab file: Movie_Project_Part_1.ipynb.
3. Ensure the source dataset Master_Movies_Dataset.csv is located in the same working directory as your notebook.
4. Run the notebook cells sequentially from top to bottom.
5. The pipeline will automatically check for missing values, fetch the data, and update the master CSV file incrementally.

### 📁 Files in this Repository
* **`Movie_Project_Part_1.ipynb`** - The complete Python scraper notebook.
* **`Master_Movies_Dataset.csv`** - The final consolidated and cleaned dataset.
* **`Project_Report.pdf`** - The executive summary report.









