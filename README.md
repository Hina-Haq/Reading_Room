<div align="center">
  <img src="./src/logo_dark.svg" alt="The Reading Room logo" width="180">

# The Reading Room

### An Unsupervised Machine Learning Book Recommender

A book recommender built with web scraping, API collection, unsupervised machine learning, and Streamlit.

**Team:** Gabriela Cascione · Hina Haq
</div>

---

## Index

- [Project Overview](#project-overview)
- [The Problem](#the-problem)
- [Our Solution](#our-solution)
- [Data Sources](#data-sources)
- [Dataset Overview](#dataset-overview)
- [Project Workflow](#project-workflow)
- [Data Cleaning](#data-cleaning)
- [Machine Learning Approach](#machine-learning-approach)
- [The App](#the-app)
- [Project Structure](#project-structure)
- [Tools Used](#tools-used)
- [How to Run](#how-to-run)
- [Results](#results)
- [Challenges](#challenges)
- [Next Steps](#next-steps)
- [Links](#links)
- [Team](#team)

---

## Project Overview

**The Reading Room** is an unsupervised machine learning project that recommends books based on similarity in genre, description, and metadata.

The project combines web scraping, API collection, data cleaning, feature engineering, clustering, and a Streamlit app to create an interactive book discovery experience.

---

## The Problem

Readers face too many choices and often do not know where to begin.

Generic recommendation systems do not always reflect personal taste, mood, or reading interests, so this project explores whether book metadata and text similarity can support better recommendations.

---

## Our Solution

We built a book recommender system using data collected from **Goodreads** and **Open Library**.

The final solution includes:
- a combined and cleaned dataset,
- unsupervised clustering for grouping books,
- text-based similarity for recommendations,
- and a Streamlit app for interactive exploration.

---

## Data Sources

We collected data from two main sources:

- **Goodreads** through web scraping
- **Open Library** through API collection

The project includes:
- **1,004 books from Goodreads**
- **1,000 books from Open Library**

This produced a final combined dataset of **2,004 books**.

---

## Dataset Overview

The dataset includes features such as:

- Title
- Author
- Year published
- Genres
- Description
- Average rating
- Number of ratings
- Pages
- ISBN
- Cover image URL
- Language
- Publisher
- Series
- External links

The final cleaned and concatenated file used by the Streamlit app is:

```text
books_streamlit.csv
```

This is the final project dataset stored in the GitHub repository and used directly in the app.

---

## Project Workflow

The project followed these steps:

1. Scrape book data from Goodreads.
2. Collect book data from Open Library through API requests.
3. Combine both sources into one dataset.
4. Clean and standardise metadata, text, and numeric fields.
5. Engineer features for modelling.
6. Apply unsupervised clustering.
7. Prepare the final app-ready dataset.
8. Build the Streamlit recommender app.

---

## Data Cleaning

Data cleaning was a central part of the project.

Main cleaning tasks included:
- handling missing values,
- cleaning inconsistent author and title fields,
- standardising genres,
- cleaning noisy descriptions,
- extracting years and page counts from text,
- improving cover image quality,
- and translating or normalising multilingual titles, authors, and descriptions.

The final preparation work also refined the app-ready dataset and produced the polished `books_streamlit.csv` file.

---

## Machine Learning Approach

This project uses **unsupervised machine learning**, meaning the model finds patterns in the data without a target label.

### Main modelling steps

- **TF-IDF** transformed book descriptions into numeric text features.
- **PCA** reduced dimensionality.
- **MultiLabelBinarizer** encoded genres.
- **MinMaxScaler** scaled numeric features such as ratings and pages.
- **K-Means** created the final book clusters.

### Final model choice

The final clustering model was **K-Means with k=6**.

Although k=4 achieved the highest silhouette score of 0.179 and k=6 scored 0.166, k=6 was selected because it produced richer and more useful cluster themes for recommendation.

---

## The App

The Streamlit app allows users to discover books in an interactive way.

Main features include:
- searching for a book they already like,
- receiving similar recommendations,
- browsing by genre,
- getting a random surprise recommendation,
- reading short descriptions with expandable details,
- and opening Goodreads or Google Books links.

The app reads directly from `books_streamlit.csv` and builds recommendations using cleaned genre and description-based similarity.

---

## Project Structure

```text
The-Reading-Room/
│
├── src/
│   └── logo_dark.svg
├── API_scraping.ipynb
├── Web_scraping.ipynb
├── Concat_feature_fixing_reading_room.ipynb
├── Prep_and_ML.ipynb
├── Database_Streamlit_Cleaning.ipynb
├── books_streamlit.csv
├── app.py
├── the_reading_room_presentation.pptx
└── README.md
```

### File guide

- `Web_scraping.ipynb`  
  Goodreads web scraping workflow.

- `API_scraping.ipynb`  
  Open Library and API-based data collection.

- `Concat_feature_fixing_reading_room.ipynb`  
  Dataset merging and feature fixing.

- `Prep_and_ML.ipynb`  
  Feature preparation and clustering workflow.

- `Database_Streamlit_Cleaning.ipynb`  
  Final cleaning and app-ready data preparation.

- `books_streamlit.csv`  
  Final cleaned and concatenated dataset used in the app.

- `app.py`  
  Streamlit recommendation app.

- `the_reading_room_presentation.pptx`  
  Final presentation.

---

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Selenium
- BeautifulSoup
- Requests
- Streamlit
- Jupyter Notebook

---

## How to Run

1. Clone the repository.
2. Install the required Python libraries.
3. Make sure `books_streamlit.csv` is in the project folder.
4. Run the Streamlit app:

```bash
streamlit run app.py
```

The app loads the cleaned dataset and generates recommendations based on similarity between books.

---

## Results

The project produced:
- a combined dataset of **2,004 books**,
- cleaned and standardised metadata from two different sources,
- meaningful book clusters,
- and a working Streamlit recommender app.

The final system combines clustering and text similarity to help users move from a familiar book to new recommendations with related content and themes.

---

## Challenges

Some of the main challenges were:
- scraping restrictions on some book websites,
- JavaScript-rendered or blocked pages,
- inconsistent genre labels,
- multilingual metadata,
- missing values,
- low-resolution cover images,
- and noisy text fields.

These issues made data cleaning and feature preparation especially important.

---

## Next Steps

Possible future improvements include:
- expanding the dataset beyond 2,004 books,
- comparing K-Means with hierarchical clustering,
- collecting user feedback on recommendations,
- and testing richer NLP approaches such as Word2Vec or BERT embeddings.

---

## Links

- **Deployed Streamlit App:** [Add app link here]
- **Presentation:** [Add presentation link here]
- **GitHub Repository:** [Add GitHub repository link here]

---

## Team

**Gabriela Cascione**  
**Hina Haq**
