# book_recommendation_system_using_ML

The goal of this project is to build a basic recommendation engine that can suggest books to users. This is achieved by 
1.  **Data Loading and Preprocessing**: Loading book, user, and rating datasets, and cleaning them for inconsistencies.
2.  **User Filtering**: Identifying and retaining active users who have rated a significant number of books (more than 200 ratings).
3.  **Book Filtering**: Focusing on popular books that have received a substantial number of ratings (more than 50 ratings).
4.  **Matrix Formation**: Creating a pivot table (sparse matrix) where rows represent books, columns represent users, and values are the ratings given by users to books.
5.  **Model Training**: Utilizing a Nearest Neighbors model (specifically, `Brute-force` algorithm) to find the closest books in the rating matrix.
6.  **Recommendation Generation**: Providing a function to recommend a list of similar books given a book title.

## Dataset

The project uses three main datasets:

*   `Books.csv`: Contains information about books, including ISBN, title, author, publication year, and publisher.
*   `Users.csv`: Contains user demographic information, such as User-ID, location, and age.
*   `Ratings.csv`: Contains book rating information, linking User-ID, ISBN, and Book-Rating.

These datasets are downloaded from a Google Drive folder at the beginning of the notebook.

## Model

The recommendation model is based on **Collaborative Filtering** using `sklearn.neighbors.NearestNeighbors`. Specifically, a `NearestNeighbors` model with the `brute` algorithm is trained on the sparse book-user rating matrix. This model calculates the distances between books to find the most similar ones.

## How to Use

1.  **Run the notebook**: Execute all cells in the Jupyter/Colab notebook sequentially.
2.  **Get Recommendations**: Use the `recommend_book()` function by passing a book title as an argument to get a list of recommended books.

Example:

```python
recommend_book('The Hitchhiker\'s Guide to the Galaxy')
