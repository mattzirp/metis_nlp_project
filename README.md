# Recommending Beers Using An NLP Workflow with Reviews from RateBeer.com

#### Matthew Zirpoli

## Abstract
The goal of this project was to create a content-based beer recommendation system utilizing natural language processing techniques along with unsupervised/semi-supervised learning. I worked with a dataset from RateBeer, which was obtained as a raw, semi-structured text file containing about 2.9 million reviews posted to the RateBeer.com website. The data was imported to a structured format, then culled to a sampled set of 50,000 reviews. The review text was cleaned, preprocessed, and tokenized. After preprocessing, I used a Count vectorizer and CorEx with anchors to produce a semi-supervised topic model. The five produced topics were used as features along with the review scores to produce a content-based recommender that accepts a beer name as input and suggests five closely related beers for the user to try.

## Design


## Data
The dataset was obtained from the API team at [RateBeer.com](ratebeer.com). The set consists of over 2.9 million reviews and over 101,000 different beers. Features are related to the beer (name, brewer, style, alcohol by volume) and review (user, various scores, text of review). A subset of this data was used in the workflow, selecting a sample of 50000 reviews for beers that had over 250 reviews. 
## Algorithms

## Tools

## Communication
The findings and slide deck accompanying this project's presentation are accessible via this GitHub repo.
