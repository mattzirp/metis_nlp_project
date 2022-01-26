# Recommending Beers Using An NLP Workflow with Reviews from RateBeer.com

#### Matthew Zirpoli

## Abstract
The goal of this project was to create a content-based beer recommendation system utilizing natural language processing techniques along with unsupervised/semi-supervised learning. I worked with a dataset from RateBeer, which was obtained as a raw, semi-structured text file containing about 2.9 million reviews posted to the RateBeer.com website. The data was imported to a structured format, then culled to a sampled set of 50,000 reviews. The review text was cleaned, preprocessed, and tokenized. After preprocessing, I used a Count vectorizer and CorEx with anchors to produce a semi-supervised topic model. The five produced topics were used as features along with the review scores to produce a content-based recommender that accepts a beer name as input and suggests five closely related beers for the user to try.

## Design
Craft beer represents one of the fastest growing segments of the alcohol industry, with over 300% increase in revenue since 2005. Despite it's success, or perhaps due to it, craft beer retains an air of exclusivity to it. In addition to this, even beer fans are faced with nearly endless options leading to choice overload. For this project, I created a content-based recommendation system which recommends beers to a person given a beer they already know they like. 

## Data
The dataset was obtained from the API team at [RateBeer.com](ratebeer.com). The set consists of over 2.9 million reviews and over 101,000 different beers. Features are related to the beer (name, brewer, style, alcohol by volume) and review (user, various scores, text of review). A subset of this data was used in the workflow, selecting a random sample without replacement of 50000 reviews for beers that had over 250 reviews. 

## Algorithms
**Processing Raw Data:** A .txt file was received with blocks of N lines of text representing each review record. Record blocks were parsed into a structured pandas dataframe with a column for each feature, and row for each record. Review scores were converted to float from fraction strings. Some text fields were cleaned of HTML characters and unnecessary punctuation. Review text data was preserved to allow for preprocessing with NLP libraries.

**Text Preprocessing:** Numbers, punctuation, and stop words were removed from the text,  which was then lemmatized and tokenized using the spaCy library.

**Topic Modeling:** Baseline models were created with different vectorizers, CountVectorizer and TF-IDF, tuning for min/max document frequency. NMF was base-lined, but ultimately a CorEx model was with an semi-supervised anchoring approach. The final model used CountVectorizer with minimum document frequency of 0.3 and maximum document

**Recommendation System:** The recommendation system was built using topics as features, along with review scores aggregated by mean for each unique beer. A single beer is provided as input and 5 similar beers are provided using euclidean distance calculations.

## Tools
- Numpy and Pandas for data manipulation
- spaCy for text processing
- scikit-learn for preprocessing, modeling, and distance calculation
- CorEx for semi-supervised topic modeling
- matplotlib for visualization

## Communication
The findings and slide deck accompanying this project's presentation are accessible via this GitHub repo.
