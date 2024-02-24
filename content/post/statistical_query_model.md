---
title: "TIL - Statistical Query Model"
date: 2024-02-24
description: A tiny explainer on the statistical query model for training ML models privately
tags: ["TIL", "Machine Learning", "Differential Privacy"]
---

Statistical Query Model of learning is a method of learning where the model is trained not on individual examples from the training set, but on the statistical properties obtained from them. In this case, the model learns by querying an oracle, which answers statistical queries of the data distribution of the training examples, averaged over the entire training dataset. This is useful in handling noisy datasets, since the oracle does not give fully accurate answers, but accurate 'on average' with a certain tolerance. Computational complexity is determined by the amount of queries the model has to make to the oracle. 

To understand this, let's take an example. If you are using the MNIST dataset, using the traditional approach, you'd take the pixel colour values as input, an input with size 768. Using SQM, you'd query an oracle which would answer certain queries given the label as input - for example, given the digit label, the oracle might answer with the average intensities of pixels in all the images of the specific digit. Another example of a **query** can be - 'Estimate the probability that a given random image is "2" and has pixels darker than a certain threshold in the top-left corner', to which the oracle could give a **response** like - 0.15 ± 0.02, which can be interpreted as - 'Around 15% of the images have the label "2" with dark top-left corners, with a 2% possible error in estimate.' Some other examples of queries are - 'For two randomly chosen images, if one has a higher average pixel intensity, what is the probability that it also has a higher digit label?', 'Given a randomly chosen image with strong edge detection on the right side, what is the probability it's a "7"?', 'For two randomly chosen images, both "3"s, what is the probability that one has more pixels activated in the lower half?' Therefore, it is essential to construct these queries such that your model learns useful insights out of the training data, while asking a limited number of questions to the oracle.

SQ Models have interesting properties, one of which was exploited in mid-2000s to enable a lot of traditional learning algorithms to directly parallelize on multicore architectures (See - [Chu et al](https://proceedings.neurips.cc/paper_files/paper/2006/file/77ee3bc58ce560b86c2b59363281e914-Paper.pdf)). Given that the model is never exposed to the original training data or specific examples, it makes an attractive learning method to train algorithms maintaining differential privacy. 

---

To learn more, here are some resources:

- The original paper introducing SQ Model - [https://www.cis.upenn.edu/~mkearns/papers/sq-journal.pdf](https://www.cis.upenn.edu/~mkearns/papers/sq-journal.pdf)
- Another explainer - [http://vtaly.net/papers/Kearns93-2017.pdf](http://vtaly.net/papers/Kearns93-2017.pdf)
- CMU Lecture on Differential Privacy and SQ Learning - [https://www.cs.cmu.edu/~avrim/ML07/lect1207.pdf](https://www.cs.cmu.edu/~avrim/ML07/lect1207.pdf)