
# Books Recommender System 

## Contents:
- [Problem Statement](#problem-Statement)
- [Data Dictionary](#Data-Dictionary)
- [Executive Summary](#Executive-Summary)


## Problem Statement

**How can we implement a recommendation system to predict books that a reader likes?**

## Data Dictionary

The data dictionary serves to explain the list of column headers found in the original datasets.

| No. | Column                    | Dataset            | Type    | Description                                                                                                  |
|-----|---------------------------|--------------------|---------|--------------------------------------------------------------------------------------------------------------|
| 1   | authors                   | books_enriched.csv | object  | names of all book contributors, including illustrators and collaborators                                     |
| 2   | average_rating            | books_enriched.csv | float64 | average rating                                                                                               |
| 3   | best_book_id              | books_enriched.csv | int64   | book id of its most popular edition from Goodreads. e.g. https://www.goodreads.com/book/show/2767052         |
| 4   | book_id                   | books_enriched.csv | int64   | unique ID for each book                                                                                      |
| 5   | books_count               | books_enriched.csv | int64   | number of editions                                                                                           |
| 6   | description               | books_enriched.csv | object  | free text summarizing book's content                                                                         |
| 7   | genres                    | books_enriched.csv | object  | genre tags taken from top shelves users assigned to a book                                                   |
| 8   | goodreads_book_id         | books_enriched.csv | int64   | book id with reference to Goodreads website                                                                          |
| 9   | image_url                 | books_enriched.csv | object  | url link to book cover image                                                                                 |
| 10  | isbn                      | books_enriched.csv | object  | 9-digit Standard Book Numbering (SBN) or 10-digit International Standard Book Number (ISBN)                  |
| 11  | isbn13                    | books_enriched.csv | float64 | 13-digit ISBN, assigned after 1 Jan 2007                                                                     |
| 12  | language_code             | books_enriched.csv | object  | abbreviated language tags for all books                                                                      |
| 13  | original_publication_year | books_enriched.csv | float64 | year when the book was first published                                                                       |
| 14  | original_title            | books_enriched.csv | object  | original title when book first published                                                                     |
| 15  | pages                     | books_enriched.csv | float64 | total page count                                                                                             |
| 16  | publishDate               | books_enriched.csv | object  | publication date                                                                                             |
| 117 | ratings_1                 | books_enriched.csv | int64   | number of ratings with 1                                                                                     |
| 18  | ratings_2                 | books_enriched.csv | int64   | number of ratings with 2                                                                                     |
| 19  | ratings_3                 | books_enriched.csv | int64   | number of ratings with 3                                                                                     |
| 20  | ratings_4                 | books_enriched.csv | int64   | number of ratings with 4                                                                                     |
| 21  | ratings_5                 | books_enriched.csv | int64   | number of ratings with 5                                                                                     |
| 22  | ratings_count             | books_enriched.csv | int64   | total number of ratings received                                                                             |
| 23  | small_image_url           | books_enriched.csv | object  | url link to smaller book cover image                                                                         |
| 24  | title                     | books_enriched.csv | object  | book title                                                                                                   |
| 25  | work_id                   | books_enriched.csv | int64   | book id to reflect the list of editions of given title. e.g. https://www.goodreads.com/work/editions/2792775 |
| 26  | work_ratings_count        | books_enriched.csv | int64   | total number of ratings received                                                                             |
| 27  | work_text_reviews_count   | books_enriched.csv | int64   | number of written reviews received                                                                           |
| 28  | authors_2                 | books_enriched.csv | object  | all book contributors, including illustrators and collaborators                                              |
| 29  | user_id                   | ratings.csv        | int64   | user id                                                                                                      |
| 30  | book_id                   | ratings.csv        | int64   | book id                                                                                                      |
| 31  | rating                    | ratings.csv        | int64   | rating for given book                                                                                        |


## Executive Summary
3 types of recommendation systems were built:

**1. Content Based Recommendation**:  
Using book titles, authors, genres and descriptions as features to come up with book predictions of similar features.

**2. Collaborative Filtering Recommendation**:  
Tried both memory and model based approaches, by building our own matrix and using the  `Surprise`  library respectively.  We used Singular Value Decomposition as our chosen algorithm from `Surprise`, and obtained top predictions for a given user based on estimated ratings.

**3. Hybrid Recommendation**:  
Both content and collaborative filtering models were combined. Given an user ID and a book title, we produced book suggestions based on similar features and estimated ratings.

**Future Works**

1.  Include other sources such as text reviews or discussion, to provide more content-based features for modelling.
2. Consider using other recommendation system libraries and/or neural network models, such as  `LightFM`  or  `TensorFlow Recommenders`, for faster or more efficient models.