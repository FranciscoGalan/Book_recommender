# Goodreads Book Recommender

A data analysis pipeline which recommends a list of books based on a Goodreads user's reviews, his or her friend's, and the books' average ratings.

*Goodreads is a website in which users can sign up and register books to generate library catalogs and reading lists.*

<br/>

## What is does

The Book Recommender suggests which books a [Goodreads](https://www.goodreads.com/) 's user could read next!

To demonstrate, I used my own [profile information]() and selected the profiles of some of my friends and people I follow. The Recommender now performs the following steps:

1. Extracts the user information using Goodread's Web API.
2. Prepares data for cleaning and analysis.
3. Cleans and formats book data.
4. Recommends a list of books.

According to the analysis, these are the books I should read next:

![](https://github.com/FranciscoGalan/Goodreads_Book_Recommender/blob/main/Media/recommended_books_francisco_galan.PNG)

Not bad. These recommendations are based partly on the **correlations** I have with some of my contacts. The idea is to find contacts with similar tastes to mine. Such  contacts probably liked books that I will also like. Conversely,  contacts with a negative correlation probably liked books that I won't like.

| Contact    | Taste correlation |
| ---------- | ----------------- |
| Vanessa    | 1.000000          |
| Nicolas    | 0.361499          |
| Andrea     | 0.316139          |
| Mario      | 0.000000          |
| Cova       | 0.000000          |
| Eduardo    | -0.069824         |
| Fernando   | -0.191663         |
| Stefan     | -0.244444         |
| Maria      | -0.291748         |
| Bill Gates | -0.555556         |

The Book Recommender also considers how high are the **mean ratings** of my contacs. This should make sense: if a contact rates most books with two stars, her five-star ratings  should count more than those of a contact that rates most books with five stars.

| Contact    | Mean rating | Standard deviation |
| ---------- | ----------- | ------------------ |
| Cova       | 4.857143    | 0.478091           |
| Eduardo    | 4.101796    | 1.015748           |
| Mario      | 3.966102    | 0.927847           |
| Fernando   | 3.931818    | 0.868285           |
| Nicolas    | 3.819149    | 0.983332           |
| Vanessa    | 3.810811    | 1.081294           |
| Andrea     | 3.757282    | 0.856815           |
| Stefan     | 3.732394    | 0.815762           |
| Bill Gates | 3.538153    | 0.933014           |
| Maria      | 3.340909    | 0.914927           |



## How to use it

In the [**Notebook main.ipynb**](https://nbviewer.jupyter.org/github/FranciscoGalan/Goodreads_Book_Recommender/blob/main/main.ipynb) you can find all the steps of the pipeline.

#### 1. Extract users' information

To communicate with its Web API, Goodreads requires developers to get a [key](https://www.goodreads.com/api). I have hidden mine in the notebook, but it should work with yours.  Just change the value of the `CONSUMER_KEY` variable. 

Then,  use the `extract_info` function for each of the users whose information you want to get. If your request was successful, the cell should print "Status code:  200".

#### 2. Prepare data

You'll have to replace some of the variable names, depending on the users you chose. Besides that, you should be able to execute most of the cells without any problem.  

#### 3. Clean and format data

The `clean_title` function eliminates duplicate books (which, for example, might only vary slightly in their wording).  I believe it works for most books, but you might consider playing with it if you still get duplicates. 

#### 4. Recommend books

Execute all the cell to get your final recommendations. You can tweak the relative weight of correlations or ratings in the `correlation_weighted` and `weighted_rating` functions, respectively. 

*Happy reading!*