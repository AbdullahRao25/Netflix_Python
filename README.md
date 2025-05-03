# Movie Database Analysis

This project involves cleaning, processing, and analyzing a movie dataset to derive insights and visualize movie popularity and ratings over time. The dataset contains information about various movies, such as their release date, title, popularity, vote count, and average vote.

## Project Overview

In this project, we:

- Cleaned and processed a movie dataset with missing values and inconsistencies.
- Performed exploratory data analysis (EDA) to understand movie trends.
- Visualized the distribution of movie attributes such as popularity, vote count, and vote average.
- Categorized movies based on their popularity and rating into different grade categories.

## Dataset

The dataset used in this project is named `mymoviedb.csv`, and it contains the following columns:

- `Release_Date`: The release date of the movie.
- `Title`: The name of the movie.
- `Overview`: A brief description of the movie plot.
- `Popularity`: A measure of how popular the movie is.
- `Vote_Count`: The number of votes the movie received.
- `Vote_Average`: The average rating of the movie.
- `Original_Language`: The language in which the movie was originally released.
- `Genre`: The genres of the movie (e.g., Action, Adventure, Drama).
- `Poster_Url`: The URL for the movie poster.
- `Year_of_Release`: The year the movie was released.

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/moviedb-analysis.git
    ```

2. Install the required Python libraries:

    ```bash
    pip install -r requirements.txt
    ```

3. Ensure you have the dataset (`mymoviedb.csv`) in the appropriate directory.

## Usage

To run the project and perform the analysis:

1. Clone the repository and navigate to the project directory.
2. Run the following Python script:

    ```bash
    python movie_analysis.py
    ```

## Files

- `movie_analysis.py`: The main Python script containing the data cleaning, analysis, and visualization code.
- `mymoviedb.csv`: The raw movie dataset.
- `requirements.txt`: A list of required Python libraries for the project.
- `README.md`: This file.

## Data Cleaning Process

- Removed rows with missing values in critical columns like `Title` and `Overview`.
- Filled missing numerical values (`Popularity`, `Vote_Count`, `Vote_Average`) with the most frequent values using `SimpleImputer` from Scikit-Learn.
- Converted columns such as `Popularity`, `Vote_Count`, and `Vote_Average` to appropriate numerical types.
- Extracted the year of release from the `Release_Date` column and added it as a new feature (`Year_of_Release`).
- Created a new `Popularity_Grade` column to categorize movies based on their `Vote_Average`.

## Visualizations

Several visualizations were generated, including:

- Distribution of `Popularity`, `Vote_Count`, and `Vote_Average` using histograms and boxplots.
- Count of movies categorized by their popularity grade (`Unpopular`, `Below_Average`, `Average`, `Above_Average`, `Popular`).

## Contributing

Feel free to fork the repository and submit pull requests if you have any improvements or new ideas for the analysis.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
