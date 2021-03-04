# Document-Retrieval-and-Question-Answering-with-BERT

In first part of this repository we developed, with 2 different techniques, a Document Retrieval System, which aims to return titles of scientific
papers containing the answer to a given user question. 

For example, for the question “What are the coronaviruses?”, your system can return the
paper title “Distinct Roles for Sialoside and Protein Receptors in Coronavirus Infection”
since this paper contains the answer to the asked question.

Note that our dataset is the initial-first release of CORD-19 dataset, 2020-03-13, which is the smallest possible dataset with 9000 articles. 
You can find it here: [CORD-19_Releases](https://ai2-semanticscholar-cord-19.s3-us-west-2.amazonaws.com/historical_releases.html)

To achieve the goal of this exercise, we first read [Sentence Embeddings using Siamese BERT-Networks](https://arxiv.org/pdf/1908.10084.pdf), in order to understand how to create sentence embeddings. We decided to transform sentences to embeddings, with the help of [SBERT Library](https://www.sbert.net/). So the main concept behind our retrieval system was to compare sentence embeddings (question's and possible answer's embedding) by cosine similarity. 

You can check thoroughly in this [notebook](https://github.com/spympr/Document-Retrieval-and-Question-Answering-with              BERT/blob/main/Document_Retrieval_System/Document_Retrieval_with_BF.ipynb) 

[othernotebook](https://github.com/spympr/Document-Retrieval-and-Question-Answering-with BERT/blob/main/Document_Retrieval_System/ Document_Retrieval_with_Heuristic.ipynb)

