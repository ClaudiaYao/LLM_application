## 🏄🏾‍♀️ 00-simple-local-rag.ipynb<br>
This sample comes from https://github.com/mrdbourke/simple-local-rag.git, almost change nothing and run all the steps. You will get a much clearer understanding of RAG. Compared to the all sealed up functions of LangChain. The author has YouTube video https://youtu.be/qN_2fnOPY-M.

## 🏌🏾‍♀️ 01-intent-identification.ipynb<br>
This sample is used to identify the topics of customer support scope. It refers to this Medium article: https://towardsdatascience.com/complete-guide-to-building-a-chatbot-with-spacy-and-deep-learning-d18811465876 and its github:
https://github.com/mtaruno/eve-bot/tree/master

This notebook simplified the whole process and try to classifiy topics of Apple Customer Support by using word vectorizing and KMeans classification. The result is not satisfactory, but could learn how to use Word2Vec,  Doc2Vec, and SentenceTransformer to embed/vectorize words and documents.

## 🚴🏾‍♂️ 02-Word2Vec_Doc2Vec_TSNE_demo.jpynb<br>
This sample is used to accelerate intent tagging. It use TfidfVectorizer to choose top ranking words, use Word2Vec and Doc2Vec to vectorize the words, and then use TSNE to generate a 2D diagram to visualize the layout of words. Although it is not a precise and fully automated intent identification process, it could accelerate manual tagging process and make your work much easier.