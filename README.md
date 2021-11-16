# The plan...

The aim of this project is to create a constructive way of visually evaluating the various multilingual embeddings available. For the sake of this project, random sentences have been taken and translated to a few selected languages. However, the method can be used to evaluate domain specific sentences with languages of choice.

# Multilingual embeddings

These embeddings are particularly useful to apply NLP tools to data of documents of multiple languages without specifically mentioning the language. The output layer is a universal embeddings which can be further put to use for any text based projects like sentimental analysis, topic extraction..

# what's covered in the project

only two such embeddings are compared, but the process can be extended to any number of embeddings, the ones here are:
1. LaBse
2. sentence_transformers.

The evaluation is done three fold.

# PCA (dimensional reduction)

15 senteces in multiple languages are passed through the layers to get the embeddings. These embeddings are further reduced to 2 features using PCA. So we now have 15X4 sentences with their 2 features. If we plot these, ideally we should see 15 clusters with each cluster having 4 data points. The distinct these clusters are and less the spacing within the cluster the better.

![image](https://user-images.githubusercontent.com/37741896/141932308-8cbbaf9c-d1a7-4618-aa19-84ebf8c5317b.png)   ![image](https://user-images.githubusercontent.com/37741896/141932389-94769f73-4841-4c71-8002-9d2de5ee8297.png)

# cosine similarities (different sentences in same languages):

3 sentences of one language were taken and 3 different sentence pairings were created. Cosine similarites for these 3 pairs across 4 languages are plotted. Ideally, since the sentences are different, the similarities should be low and all languages need to have similar values.

![image](https://user-images.githubusercontent.com/37741896/141933170-d08c1196-9cf3-4500-b5f7-4f301a5b04ee.png)   ![image](https://user-images.githubusercontent.com/37741896/141933216-7c02bfc5-09b0-4e2c-9ff7-93c1599f5905.png)

# cosine similarites (same sentence in different languages):

3 sentence in 4 different languages was taken and 6 pairs are formed per sentence. For every pair out of the 18, cosine similarities is calculated and plotted. Ideally, since it's the same sentence in different languages, the similarites should be high and have same value for every pair per sentence.

![image](https://user-images.githubusercontent.com/37741896/141933639-fadc4847-a3fb-4f31-baaa-3bf870b0bf2f.png)   ![image](https://user-images.githubusercontent.com/37741896/141934025-0b689f5c-328a-4093-97a5-56f0b276d3ba.png)

Although the sentence transformer fares well in distinguishing different sentences as evident int the second plots (the low values), LaBse does a better job at clubbing the same sentence in multiple languages.
 


