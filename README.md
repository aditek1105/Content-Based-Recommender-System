1	Content Based Filtering Recommendation System using Count Vectorizer

The Content Based filtering works of off the concept of the user giving their preferences/views for items and recommends similar items based on the domain specific notion of the item content. This basic approach also extends naturally to cases where the item metadata is available. (e.g., music genres, movie genres etc).
1. Process of Implementation:
i.	The description is cleaned which includes removing all emoticons and other unwanted symbols.
ii.	The process of creating the list of key words from the description involves instantiating Rake. (short for Rapid Automatic Keyword Extraction algorithm, is a domain independent keyword extraction algorithm which tries to determine key phrases in a body of text by analysing the frequency of word appearance and its co-occurrence with other words in the text.)
iii.	For the generation of the bag of words, the data from the columns “title”, “channel_title” and “keywords” are combined to get the bag of words column which is basically a combination of the words from all these 3 columns which would help the recommender system in suggesting videos with a lot more accuracy.
iv.	The next process is to generate and instantiate the count matrix (a sparse matrix) which makes use of the CountVectorizer to generate a count_matrix.
v.	A cosine similarity matrix is generated from the count_matrix. This matrix helps in generating a similarity score for a video with all the videos in the dataset. The cosine similarity matrix contains values that range between 1 and -1 where 1 guarantees exact match and is highly recommended whereas -1 means a video that is not at all similar to the title given as input and is a poor recommended video to the input.
vi.	For the title given in as input, top ten video titles are suggested along with their scores in descending order. The resulting image which suggests videos similar to “Camila Cabello’s Havana” song is depicted below.

 
2. Result Visualization using UMAP:
1.	Uniform Manifold Approximation and Projection is a general-purpose manifold learning and a dimension reduction algorithm. It helps in transforming and visualizing the output.
2.	The sparse matrix that is generated after fitting and transforming the bag of words (description) is embedded. The UMAP follows the sklearn API and has a method fit() is used to fit the data. The resulting variable is of type UMAP object and for better visualization purposes, the metric is set to “Hellinger”.
3.	The resulting array has rows where each row of the array is a 2D representation of the corresponding video title.
4.	The embedding can be plotted as a scatter plot or a bokeh interactive plot.
5.	For this result, the labels are the category-id’s and each point in the plot signifies the video in the respective category.
          
3. Outcomes:
This exercise has helped in creating a system where based on the description content and the bag of words that was generated by the process helps the user in getting the similar recommendations of videos for the video title given as the input. 
The strengths of Content-Based Filtering were also evident while carrying out this exercise such as for example:
-	The model still will recommend correctly on the basis of the content of the descriptions.
- 	No need of other contextual features to carry out recommendation. Only a feedback matrix is required to train the model.
