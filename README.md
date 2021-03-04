# Document-Retrieval-and-Question-Answering-with-BERT

In first part of this repository we developed, with 2 different techniques, a Document Retrieval System, which aims to return titles of scientific
papers containing the answer to a given user question. 

Note that our dataset is the initial-first release of CORD-19 dataset, 2020-03-13, which is the smallest possible dataset with 9000 articles. 
You can find it here: [CORD-19_Releases](https://ai2-semanticscholar-cord-19.s3-us-west-2.amazonaws.com/historical_releases.html)

To achieve the goal of this exercise, we first read [Sentence Embeddings using Siamese BERT-Networks](https://arxiv.org/pdf/1908.10084.pdf), in order to understand how to create sentence embeddings. We decided to transform sentences to embeddings, with the help of [SBERT Library](https://www.sbert.net/). So the main concept behind our retrieval system was to compare sentence embeddings (question's and possible answer's embedding) by cosine similarity. 

You can check thoroughly in this [notebook](https://github.com/spympr/Document-Retrieval-and-Question-Answering-with-BERT/blob/main/Document_Retrieval_System/Document_Retrieval_with_BF.ipynb), where we tried to find as answer, with brute-force approach, the most similar vector, by searching every sentence of every section of each paper. Besides that approach, you can observe a more clever approach (with heuristic) in this 
[notebook](https://github.com/spympr/Document-Retrieval-and-Question-Answering-with-BERT/blob/main/Document_Retrieval_System/Document_Retrieval_with_Heuristic.ipynb), where we gave emphasis initially in process to find most similar papers (10%) based only on title or/and abstract section. Then, we further searched papers we found, in body_text section so as to find the appropriate answer. With that approach we saved a lot of time and memory. 

> Here you can observe a couple of examples:
>
> 1. Example with decent performance:
> 
> Query: What was discovered in Wuhuan in December 2019? 
>
> Answer 1 : In December 2019, a cluster of pneumonia of unknown etiology was detected in Wuhan City, Hubei Province of China.
>
> From article with title: Clinical Medicine Characteristics of and Public Health Responses to the Coronavirus Disease 2019 Outbreak in China 
> 
> Cosine Similarity: 0.62 


> 2. Example with not so good performance:
> 
> Query: How does coronavirus spread?  
>
> Answer 4 : Recently, a novel coronavirus has been identified in patients with severe acute respiratory illness [1, 2] .
>
> From article with title: A novel coronavirus capable of lethal human infections: an emerging picture 
> 
> Cosine Similarity: 0.63

Note that all notebooks for both tasks are well reported and were implemented with ***Machine Learning Library Pytorch***. Running's procedure took place on ***Google Colab***, enhanced with ***Cuda GPU!***
