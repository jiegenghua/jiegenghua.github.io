---
title: 'Machine learning metrics and loss functions'
date: 2024-12-01
permalink: /posts/2024/12/blog-post-21/
tags:
  - ML
  - Metrics
  - loss function
---
There are many metrics in machine learning to measure whether a model is good enough.
Here I will summarize them one by one.



Performance Metrics
-----
$ accuracy = \frac{number\; of \; correct \; predictions}{number \; of \; total \; predictions}=\frac{TP+TN}{TP+TN+FP+FN} $.
It can be used if the data are balanced.

-----
$TRP=sensitivity=Recall=\frac{TP}{TP+FN}=1-FNR$.

TPR: true positive rate, FNR: false negative rate

-----

$precision = \frac{TP}{TP+FP}$

-----
$F_1$ score is the harmonic average of recall and precision, taking values between 0 and 1.

$F_1 \; socre = \frac{2}{\frac{1}{recall}+\frac{1}{precision}}$.

It still works for imbalanced data.






Loss functions
-----
Mean squared error





Cross entropy error


















