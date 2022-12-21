# Text_GCN_Classification

## AI Course Project

The text-based graph convolutional network (GCN) model is an interesting and novel state-of-the-art semi-supervised learning concept that is proposed recently, which is able to very accurately predict the labels of some unknown textual data given related known labeled textual data. It does so by embedding the entire corpus into a graph with documents and words as nodes, with each document-word & word-word edges having some predetermined weights based on their relationships with each other (eg. Tf-idf). A GCN is then trained on this graph with documents nodes that have known labels, and the trained GCN model is then used to infer the labels of unlabelled documents.

We implement text-GCN here using the Holy Bible as the corpus. The Holy Bible consists of 66 Books (Genesis, Exodus, etc) and 1189 Chapters. The goal here is to train a language model that is able to correctly classify the Book that some unlabelled Chapters belong to, given the labels of other Chapters. (Since we actually do know the exact labels of all Chapters, we intentionally mask the labels of some 10-20 % of the Chapters, which will be used as test set during model inference to measure the model accuracy) To do that, the language model needs to be able to distinguish between the contexts associated with the various Books (eg. Book of Genesis talks more about Adam & Eve while Book of Ecclesiastes talks about the life of King Solomon). The good results of the text-GCN model show that the graph structure is able to capture such context nicely, where the document (Chapter)-word edges encode the context within Chapters, while the word-word edges encode the relative context between Chapters.

## Results


<img src="https://github.com/AnkitHinge-007/Text_GCN_Classification/blob/main/data/combined_plot_accuracy_vs_epoch.png" width="400" height="400" /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="https://github.com/AnkitHinge-007/Text_GCN_Classification/blob/main/data/loss_vs_epoch.png" width="400" height="400" />

<img src="https://github.com/AnkitHinge-007/Text_GCN_Classification/blob/main/data/untrained_accuracy_vs_epoch.png" width="400" height="400" /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="https://github.com/AnkitHinge-007/Text_GCN_Classification/blob/main/data/test_true_idxs_dist.png" width="400" height="400" />
