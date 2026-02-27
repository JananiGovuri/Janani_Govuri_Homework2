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
import numpy as np

cm = np.array([
    [5,10,5],
    [15,20,10],
    [0,15,10]
])

classes = ["Cat","Dog","Rabbit"]

precisions = []
recalls = []

for i in range(3):
    TP = cm[i,i]
    FP = sum(cm[i,:]) - TP
    FN = sum(cm[:,i]) - TP
    
    precision = TP/(TP+FP)
    recall = TP/(TP+FN)
    
    precisions.append(precision)
    recalls.append(recall)
    
    print(classes[i], precision, recall)

print("Macro Precision:", np.mean(precisions))
print("Macro Recall:", np.mean(recalls))

total_TP = sum(cm[i,i] for i in range(3))
micro = total_TP/90
print("Micro Precision:", micro)
print("Micro Recall:", micro)
