# Book-Recommendation-System
 An AI Based Book Recommendation System based on user reading preferences and history. Collaborative filtering (CF) is a technique used by recommender systems. Collaborative filtering has two senses, a narrow one and a more general one.We have 2 models in this repo. The main model will be called "THE PRIME MODEL" and the smaller model will be called "THE CHILD".
 
 ## Method Used
 We used the method of collaborative filtering to predict the books. <br>
 So what is Collaborative Filtering ?  <br>
In the newer, narrower sense, collaborative filtering is a method of making automatic predictions (filtering) about the interests of a user by collecting preferences or taste information from many users (collaborating). The underlying assumption of the collaborative filtering approach is that if a person A has the same opinion as a person B on an issue, A is more likely to have B's opinion on a different issue than that of a randomly chosen person. For example, a collaborative filtering recommendation system for preferences in television programming could make predictions about which television show a user should like given a partial list of that user's tastes (likes or dislikes).Note that these predictions are specific to the user, but use information gleaned from many users. This differs from the simpler approach of giving an average (non-specific) score for each item of interest, for example based on its number of votes.

In the more general sense, collaborative filtering is the process of filtering for information or patterns using techniques involving collaboration among multiple agents, viewpoints, data sources, etc. Applications of collaborative filtering typically involve very large data sets. Collaborative filtering methods have been applied to many different kinds of data including: sensing and monitoring data, such as in mineral exploration, environmental sensing over large areas or multiple sensors; financial data, such as financial service institutions that integrate many financial sources; or in electronic commerce and web applications where the focus is on user data, etc. The remainder of this discussion focuses on collaborative filtering for user data, although some of the methods and approaches may apply to the other major applications as well.

# Method Used in The Prime Model
The  dataset chosen for this model is from [UCSD](https://sites.google.com/eng.ucsd.edu/ucsdbookgraph/home) who scraped the entire [Goodreads](https://www.goodreads.com/) public profiles before they deprecated their API.This dataset is huge...  
The datasets are as follows: <br>
* [goodreads_books.json.gz](https://drive.google.com/uc?id=1LXpK1UfqtP89H1tYy0pBGHjYk8IhigUK): This file contains the details of about 7.5 million books. This dataset is so huge that it cannot be loaded into memory directly. It is about 2gb compressed and when decompressed it may go upto 10gb. So we had to read it line by line instead of loading it into memory directly which will crash your computer if you have 8gb ram systems.
* [goodreads_interactions.csv](https://drive.google.com/open?id=1zmylV7XW2dfQVCLeg1LbllfQtHD2KUon): This file contains details of the ratings given by each user to each book. This is the dataset used for recommendations based on collaborative filtering.This file is also huge with size of 4gb and about 22 million line of data. So it too had to read in the same way as the goodreads_books.json.gz file.
* [book_id_map.csv](https://drive.google.com/uc?id=1CHTAaNwyzvbi1TR08MJrJ03BxA266Yxr): This file matches the book_id from the goodreads_books.json.gz file to the book_id in the goodreads_interactions.csv file. It is used to link the correct review to the correct books.  
First in the prime model we built a search engine to search books which would then serve as the basis of our recommendation system. For this we used the method of Term Frequency-Inverse Document Frequency method. It effectively creates a matrix of similarity of the said books with all the other books in the dataset. The search engine is case insensitive and can tolerate errors in search. For the recommendation system we went with collaborative filtering method. The details are mentioned above.

# About the The Child and the Website
Duw to our technical issues and lack of time and know-how of the methods of connecting the website to the Prime model we were unsuccesful in connecting the website to the model. So we had to build a smaller "CHILD" model for the sake of demonstration and to present a working website albeit not a fancy one. We Initially had a beautiful website ready but like I said due to the lack of know-how we were unable to connect the website to the model. 
For the Child model we again went with collaborative filtering method itself. The issue with the Child model is that the search engine or rather the search function si not that sound.It is both case sensitive and title sensitive. We used 3 files for this: Books.csv for book details, Users.csv for user details and Ratings,csv for book ratings based on which the collaborative filtering model is built.

# How to Run the Website
Open app.py in pycharm or similar IDE. Then run the app.py file and a local address with a port will be displayed in the console. Copy and paste the Link in the browser of your choice and the website will then work. Simply clicking on the index.html in templates folder wont work.

## Files Breakdown
* The Prime Model: The file search.ipynb is the search engine. The  file collaborative_filtering.ipynb is the recommendation model.
* The OG Website: The OG website is in the flc folder. You can check that out. Our team put a lot of effort into it.
* The rest of the files belong to the Child model.


