# Nepali Next Word Prediction


## Overview

This repository contains an implementation of Nepali next word prediction using n-gram modeling and Laplace smoothing. The model is trained on a dataset consisting of news corpus from 2013 to 2023.

## Tasks Completed

1. Text Preprocessing:
Text preprocessing is a crucial step to prepare the raw data for modeling. The following steps were taken:

- Tokenization:
     The Nepali text was tokenized to break it down into individual words.
- Lowercasing:
    All words were converted to lowercase to ensure uniformity and avoid duplication based on case differences.
- Special Character Removal:
   Special characters, punctuation, and irrelevant symbols were removed to focus on meaningful words.
- Stopword Removal:
   Commonly used stopwords in Nepali were removed to reduce noise and improve model efficiency.

2. Vocabulary Building:
Building an effective vocabulary is essential for accurate predictions. The process involved:
- Frequency-based Filtering:
   Words were ranked based on their frequency of occurrence, and only the most relevant ones were retained.
- Minimum Occurrence Threshold:
   Words with very low frequencies were excluded to maintain a manageable vocabulary size.

3. n-gram Dictionary Creation:
The NLTK library was utilized for creating bigram and trigram dictionaries. The steps included:
- Tokenization:
   Tokenized sentences were used to extract bigrams (pairs of consecutive words) and trigrams (triplets of consecutive words).
- Dictionary Creation:
   Dictionaries were constructed to store the frequencies of bigrams and trigrams in the dataset.

4. Laplace Smoothing:
Laplace smoothing, also known as add-one smoothing, was implemented to handle unseen n-grams and enhance generalization. The implementation involved:
- Adding Pseudo-Counts:
   A small constant (usually 1) was added to the observed frequencies of n-grams, preventing zero probabilities for unseen n-grams.
- Probability Adjustment:
   Adjustments were made to the probabilities of all n-grams, ensuring a more robust language model.

5. Prediction Mechanism:
The model predicts the next word in a single-word state using trigrams. The steps include:
- Input Processing:
   The input sentence is tokenized, and the last two words are extracted to form a trigram context.
- Probability Computation:
   The probabilities of all possible next words are computed based on the trigram context and the Laplace-smoothed n-gram frequencies.
- Selection of Next Word:
   The word with the highest probability is selected as the predicted next word.


## Deployment

The model is deployed on [Hugging Face Spaces](https://huggingface.co/spaces/rupeshghimire7/ngram-nepali-next-word-prediction).

## Getting Started

To run the notebook locally, follow these steps:

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/Nepali-Next-Word-Prediction.git
   cd Nepali-Next-Word-Prediction
   ```
   
2. Open the Notebook
   
   ```bash
   jupyter notebook Nepali_Next_Word_Prediction.ipynb
```
