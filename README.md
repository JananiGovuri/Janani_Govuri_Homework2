# Janani_Govuri_Homework2
Natural Language Processing 
janani Govuri 
700773302
Homework 2: Bigram Language Model
This project implements a Bigram Language Model using Maximum Likelihood Estimation (MLE).
The model is trained on a small corpus containing three sentences with start and end tokens.

It computes unigram and bigram frequency counts from the training data.
Bigram probabilities are estimated using Count(w1, w2) / Count(w1).

A function is implemented to calculate the probability of any given sentence.
Sentence probability is computed as the product of all bigram probabilities.

The model is tested on two sentences from the corpus.
Both probabilities are calculated and compared.

The model prefers <s> I love NLP </s> because it has higher probability.
The longer sentence receives lower probability due to additional multiplications.

This implementation demonstrates understanding of n-gram models and MLE.
No smoothing is applied, so unseen bigrams result in zero probability.
