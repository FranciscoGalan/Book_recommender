# Goodreads Book Recommender

A data analysis pipeline which recommends a list of books based on a Goodreads user's reviews, his or her friend's, and the books' average ratings.

*Goodreads is a website in which users can sign up and register books to generate library catalogs and reading lists.*



## What is does

The Book Recommender suggests which books a [Goodreads](https://www.goodreads.com/) 's user could read next!

To demonstrate, I used my own profile information and selected the profiles of some of my friends and people I follow:







The Recommender now performs the following steps:

1. Extracts user information using Goodread's Web API.
2. Prepares data for cleaning and analysis.
3. Cleans and formats book data.
4. Recommends a list of books.

According to it, these are the books I should read next:





Not bad. These recommendations are based partly on the correlations I have with some of my friends:





The Book Recommender also considers how high are the mean scores of my friends. 



## How to use it

In the [Notebook main.ipynb](https://nbviewer.jupyter.org/github/FranciscoGalan/Goodreads_Book_Recommender/blob/main/main.ipynb) you can find all the process.