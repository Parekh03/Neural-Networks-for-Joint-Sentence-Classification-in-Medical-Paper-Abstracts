# Joint-Sentence-Classification-in-Medical-Paper-Abstracts-using-NLP

## Introduction
With over 50 million scholarly articles published, the yearly output continues to rise, with approximately half falling under the biomedical category. While these biomedical papers prove to be an immense source of vast knowledge, reading through the long abstracts and extracting the relevant information is difficult and exhausting. Hence there is need for a technique which can swiftly pinpoint relevant information, therefore minimizing the time spent on information retrieval. 
<br><br>
This project involves multiple Natural Language Processing (NLP) techniques to classify each sentence of a Medical Paper Abstract into an appropriate heading like objective, methods, background and results to reduce time to locate information.

## About the dataset

The dataset used in this project - **PubMed 200k RCT** is publicly available [here](https://github.com/Franck-Dernoncourt/pubmed-rct). 
<br>
Multiple variants of the dataset are available with difference in the number of abstracts and replacement of the numerics with @ sign.

**PubMed 200k RCT** consists of approximately 200,000 abstracts. Each sentence of an abstract is labeled with their role in the abstract using one of the following classes - background, objective, method, result or conclusion.

## Steps involved

### 1. Data Loading and Pre-processing
All the necessary libraries along with the dataset were loaded.
<br><br>
The dataset was thorougly visualised to gain insights. After that, it was converted into a format which can be conveniently used for performing various modelling experiments.

### 2. Text Vectorization and Embedding

**Text Vectorization** - A preprocessing layer which maps text features to integer sequences.

**Embedding** - A process of turning positive integers (indexes) into dense vectors of fixed size which can be updated while training the models. (Similar to weights).

In this step, text vectorizer and embedding layer with proper required parameters like max_tokens, output_sequence_length, input_dim, etc, were created and made to fit(adapt) on the training sentences.

![image](https://github.com/Parekh03/Neural-Networks-for-Joint-Sentence-Classification-in-Medical-Paper-Abstracts/assets/110220047/04cc1d54-73d2-41f9-ae2f-b5a5e3328166)


### 3. Modelling Experiments

**Model 0** (Baseline) - Naive Bayes with TF-IDF 

**Model 1** - Conv1D with token embeddings

**Model 2** - Universal Sentence Encoder (USE) with token embeddings

**Model 3** - Conv1D with character embedding

**Model 4** - USE with token embeddings + Bidirectional LSTM with character embeddings

**Model 5** - USE with token embeddings + Bidirectional LSTM with character embeddings + positional embeddings (Line number and total lines in an abstract)

### 4. Results
![image](https://github.com/Parekh03/Neural-Networks-for-Joint-Sentence-Classification-in-Medical-Paper-Abstracts/assets/110220047/af8523c9-097d-446d-9a15-6f887bd1400e)

![image](https://github.com/Parekh03/Neural-Networks-for-Joint-Sentence-Classification-in-Medical-Paper-Abstracts/assets/110220047/c54b06d8-8b37-46d7-ba5e-7388f3e0c08e)

### 5. Predictions using the best performing model (Model 5)

#### Abstract 1 : 
![image](https://github.com/Parekh03/Neural-Networks-for-Joint-Sentence-Classification-in-Medical-Paper-Abstracts/assets/110220047/1891afb4-8180-42ec-97fc-ba29003da366)

#### Prediction : 
![image](https://github.com/Parekh03/Neural-Networks-for-Joint-Sentence-Classification-in-Medical-Paper-Abstracts/assets/110220047/da5ea459-08ed-4276-9deb-e850c668d1d1)

#### Abstract 2 : 
![image](https://github.com/Parekh03/Neural-Networks-for-Joint-Sentence-Classification-in-Medical-Paper-Abstracts/assets/110220047/a83c9731-00ef-41f4-ba35-b10a9626a87a)

#### Prediction : 
![image](https://github.com/Parekh03/Neural-Networks-for-Joint-Sentence-Classification-in-Medical-Paper-Abstracts/assets/110220047/5f90e841-ded4-437e-b3ff-f60f16bee150)


## References/Resources
1. [Udemy - Tensorflow Developer Certificate](https://www.udemy.com/course/tensorflow-developer-certificate-machine-learning-zero-to-mastery/?kw=tensorflow+developer+certif&src=sac)
2. [MIT's video lecture on NLP](https://youtu.be/ySEx_Bqxvvo?si=-2BwahPRE4imhwiP)
3. [Tensorflow's documentation](https://www.tensorflow.org/)
4. [The Unreasonable Effectiveness of Recurrent Neural Networks](https://karpathy.github.io/2015/05/21/rnn-effectiveness/)
5. [Understanding LSTMs](https://colah.github.io/posts/2015-08-Understanding-LSTMs/)
6. [Understanding TF-IDF](https://monkeylearn.com/blog/what-is-tf-idf/)

