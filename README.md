# 🎬 Movie Metadata Cleaning & Exploratory Analysis

Welcome to the **Movie Metadata Cleaning & Analysis** project!  
This project focuses on **data wrangling, preprocessing, and insight extraction** from a raw movie dataset. The dataset contains metadata such as popularity, user ratings, genres, and release dates for thousands of movies.  
The primary goal is to make the dataset **clean, analyzable, and machine-learning ready** by addressing missing values, correcting data types, and uncovering initial patterns.

---

## 📦 Table of Contents

- [📄 Project Overview](#-project-overview)  
- [📁 Dataset Description](#-dataset-description)  
- [🛠️ Tools & Technologies](#-tools--technologies)  
- [🔍 Data Cleaning Process](#-data-cleaning-process)  
- [📊 Key Insights](#-key-insights)  
- [📌 File Structure](#-file-structure)  
- [🚀 How to Run the Project](#-how-to-run-the-project)  
- [📈 Future Improvements](#-future-improvements)  
- [🙋‍♂️ Contact](#-contact)

---

## 📄 Project Overview

This project addresses the common problems faced in real-world movie datasets:

- Inconsistent data types (e.g., numeric values stored as strings)  
- Null values in essential fields  
- Mixed or malformed dates  
- Redundant data or duplicates  
- Lack of derived features like `year` or `language group`

By performing **robust data cleaning and transformation**, we prepare this dataset for further tasks such as:

- Descriptive statistics  
- Time series trend analysis  
- Genre-based segmentation  
- Machine learning models (e.g., recommendation systems)

---

## 📁 Dataset Description

The original dataset `movies.csv` includes the following features:

| Column Name         | Description                                           |
|---------------------|-------------------------------------------------------|
| `title`             | Name of the movie                                     |
| `overview`          | Short summary/description of the movie                |
| `popularity`        | Popularity score (numeric, sometimes string-formatted)|
| `vote_count`        | Number of votes the movie received                    |
| `vote_average`      | Average rating score (0–10 scale)                     |
| `original_language` | Language code (e.g., `en`, `fr`)                      |
| `genre`             | Movie genre(s)                                        |
| `poster_path`       | URL to the movie poster image                         |
| `release_date`      | Movie's release date in varying formats               |

---

## 🛠️ Tools & Technologies

- **Python 3.10+**  
- **Pandas** – data manipulation  
- **NumPy** – numerical processing  
- **Matplotlib & Seaborn** – data visualization  
- **Jupyter Notebook** – interactive development and visualization  

---

## 🔍 Data Cleaning Process

Each transformation step is implemented systematically to ensure reproducibility and traceability.

### 1. Load Dataset
- Loaded using `pd.read_csv()`.
- Quick overview with `.head()` and `.info()`.

### 2. Null Value Analysis
- Calculated percentage of nulls using:
```python
df.isnull().mean() * 100

## 3. Drop or Impute

> Dropped rows with nulls in critical fields like title and overview.

> Imputed numeric fields (vote_count, vote_average, popularity) with mode.

## 4. Convert Numeric Fields

Converted string-formatted numeric fields using:

pd.to_numeric(df["col"], errors="coerce")
Dropped rows where conversions failed.

## 5. Date Parsing

Converted release_date into datetime using:

pd.to_datetime(df['release_date'], errors='coerce')

Extracted year into a new column:

df['year'] = df['release_date'].dt.year

## 6. Drop Irrelevant or Corrupt Records

> Removed rows with:

> Missing or invalid release_date

> vote_average > 10 (invalid)

> Negative or zero vote_count

## 7. Duplicates Check

Checked for duplicates:

df.duplicated().sum()
Removed if any (result: zero duplicates found)

#📊 Key Insights

## 🎥 General Stats

> Total valid movies after cleaning: 9,827

> Average movie rating: 6.0

> Popularity ranges from ~13 to over 5,000

> Most common original language: English (en)

# 🧹 Null Handling Summary

Column	Original Null %	Cleaning Action
title	~0.03%	Dropped
overview	~0.01%	Dropped
popularity	0.11%	Imputed (mode)
vote_count	0.11%	Imputed (mode)
vote_average	0.11%	Imputed (mode)
release_date	~0.7%	Dropped (invalid)

📅 Yearly Trends

Earliest valid movie: 1902

Most data points concentrate between 1980–2020

Common missing dates were due to parsing errors or placeholder values

# 📌 File Structure

movie-data-cleaning/
├── movie_cleaning.ipynb       # Main notebook with all analysis steps
├── movies.csv                 # Original dataset
├── cleaned_movies.csv         # Final cleaned data (optional output)
├── README.md                  # You're here!

# 🚀 How to Run the Project

##📋 Prerequisites

Make sure Python and pip are installed. Then, install the required packages:

pip install pandas numpy matplotlib seaborn jupyter

##🧪 Run Instructions

Clone or download this repository.

Launch Jupyter Notebook:

jupyter notebook
Open and run movie_cleaning.ipynb step-by-step.

