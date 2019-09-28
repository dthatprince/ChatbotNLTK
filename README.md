#   Building a Chatbot with Python using NLTK 

# Note:
For this example, I will be using the Wikipedia article on global warming (https://en.wikipedia.org/wiki/Global_warming). To scrape the article, we will use the BeautifulSoap library for Python. The download instructions for the library are available here.(https://pypi.org/project/beautifulsoup4/)


# Downloading Required Libraries: 

Before we can proceed with the code, we need to download the following libraries:

1.  Chatbot development falls in the broader category of Natural Language processing.

2.  We will be using a natural language processing library NLTK to create our chatbot.  The installation instructions for NLTK can be found at this official link.
    
3.  The BeautifulSoap library scrapes the data from a website in HTML format. To parse the HTML, we will use the LXML library. The download instructions for the library are available at official link.


# Generating Response:

Next, we need to create a method for general response generation.
- To do so we need to convert our words to vectors or numbers and then apply cosine similarity (https://en.wikipedia.org/wiki/Cosine_similarity) to find the similar vectors.
- The intuition behind this approach is that the response words should have the highest cosine similarity with user input words.
To convert word to vectors we will use TF-IDF approach(https://python.gotrained.com/tf-idf-twitter-sentiment-analysis/).
- We can use "TfidfVectorizer" from the "sklearn.feature_extraction.text"  module to convert words to their TF-IDF counterparts.
Similarly, to find the cosine similarity, the "cosine_similarity" method from the "sklearn.metrics.pairwise" class can be used.

The "give_reply" function simply takes user input as a parameter, lemmatizes, removes punctuations, and then create TFIDF vectors from the words in the sentence. TFIDF vectors for the already existing sentences in the article is also created. 
Next, cosine similarity between vectors of the words in the sentence entered by the user and the existing sentences is found and the sentence with the highest cosine similarity is returned as a response.
In case if no cosine similarity is found between user input and any sentence in the article, the response is generated that the sentence is not understood.

