
# Music Recommender System Documentation

1. Introduction:

The Music Recommender System is a Python-based application that utilizes Natural Language Processing (NLP) and collaborative filtering techniques to recommend music based on user input. The system is built using the pandas library for data manipulation, scikit-learn for text processing, and Streamlit for creating a user-friendly interface. The recommendation model is based on the similarity between song lyrics.

2. Data Loading and Cleaning:

The system loads music data from the "spotify_millsongdata.csv" file using the pandas library.
Initial exploration of the dataset is performed using df.head(), df.tail(), df.shape, and df.isnull().sum().
3. Data Sampling:

To reduce computation time, a random sample of 5000 rows is taken from the original dataset using df.sample(5000).
The 'link' column is dropped as it is not needed for the recommendation model.
4. Text Cleaning/Preprocessing:

The lyrics in the 'text' column are converted to lowercase using df['text'] = df['text'].str.lower().
Special characters and newlines are removed using regular expressions.
Tokenization and stemming are performed using the NLTK library to further preprocess the text data.
5. Text Vectorization:

The TfidfVectorizer from scikit-learn is used to convert the preprocessed text data into a TF-IDF matrix.
Cosine similarity is calculated between the song lyrics to determine their similarity.
6. Model Building:

A recommendation function is defined to provide song recommendations based on user input.
The function uses the cosine similarity matrix to find similar songs and returns a list of recommended songs.
7. Model Persistence:

The similarity matrix and the preprocessed dataset are saved using the pickle library for later use.
Pickle files are named 'similarity.pkl' and 'df.pkl'.
8. Spotify Integration:

The system integrates with the Spotify API using the Spotipy library.
The Spotify API is used to fetch album cover images for the recommended songs.
9. Streamlit User Interface:

The user interface is created using the Streamlit library.
Users can select a song from the dropdown list and click the "Show Recommendation" button to view recommended songs with their album covers.
10. Running the Application:

To run the application, ensure that the required libraries are installed (pandas, nltk, scikit-learn, streamlit, spotipy).
Spotify API credentials (CLIENT_ID and CLIENT_SECRET) are required for Spotify integration.
Execute the Streamlit application script, and the user interface will be accessible through a web browser.
11. Conclusion:

The Music Recommender System provides an interactive and visually appealing way for users to discover new music based on their preferences. The combination of NLP and collaborative filtering techniques enhances the accuracy and relevance of the recommendations. The system can be further extended and customized based on user feedback and additional feature enhancements.