---
layout: post
title: A quick look at Natural Language Processing
subtitle: Quick introduction to NLP 
tags:
  - Python
  - NLP
published: true
---

I worked on building Recommender systems in one of my jobs as a data scientist, which was exciting, to say the least. It was an exploration into unknown tools, methods and a whole different dimension of ML that I could not have even imagined before. I only knew of quantitative, spatial and time series data science before stepping into NLP but this depth into ML shows how qualitative text data can be used as quantitative when we 'vectorize' it and then there is 'semantics' which deciphers its meaning in a way only a machine can. Using NLP, I built a few recommender systems and devised quantitative tools to evaluate each against each other. So here is a little introduction to Natural Language Processing which may help people step into it. 

Pre-requisites:
- It is necessary to know about Linguistic processing and text analysis. Such as that
    - 'Syntax' means the study of sentences, phrases, words and their structure such as grammatical combination, order of words used.
    - 'Semantics' means the study of meaning in languages such as Compositional (relationship among words and their combinations) and Lexical (meaning of words using morphology, syntax, etc.)
    - Parts of Speech (noun, verb, adjective, preposition, etc.) 
- It helps to know basic string manipulation (join, split, replace, etc.), use of 'regex' (regular expression, \r'text'), escape characters and others before starting the steps of cleaning and processing.
- Finally, there are challenges in NLP where entities such as sarcasm, puns, context etc. are involved which are difficult sometimes even for humans. So it is best to proceed knowing limitations too for it is not only garbage in, garbage out, but even with non-garbage (clean) data, not knowing such intricacies could give us results which are false and unusable.
- In specific cases what the word 'corpus' means as it has different meanings attached to it, sometimes simultaneously: such corpus means cleaned text, or it could mean a huge collection of text available (training data) such as domain-specific text warehouse/universe/corpus (such as ones available in topic modelling packages) or in case of NLTK, a collection of text/items/books such as chats, Gutenberg library and others. 

Basic steps in NLP

 - Deciding on the problem statement and types of tools that can be used
 - Data cleaning and Preparation
 - Use of inbuilt-packages
 - Building new packages if the existing ones are not adequate

1. Deciding on the problem statement
     I have worked on recommender systems and sentiment analysis using NLP. But there are also others which look at summarization, keyword extractions, semantics extraction, classifiers and others. For each of these, although data cleaning and processing steps may be similar, post-processing tools would differ greatly. For example for semantics/entity recognition, one can use Spacy, but for sentiment analysis, you could use nltk and for topic modelling, pre-trained models such as BERT would be useful. It helps to know the different tools already present.

2. Data cleaning and preparation
     This is the major chunk of processing of almost any ML project. The following are the steps that may be followed:
   
   - Removing Stop Words - Stopwords are the connecting words that add grammatical meaning but are not necessary for the machine in a lot of cases using the NLP. Removing them keeps the essence of the text and decreases processing time. Words such as: of, the, and, or, an, you, its, having, do, after, again, further, etc. There may be use cases where the stopwords are necessary, such as sentiment analysis, entity recognition, text summarization, etc. nltk library in Python has a built-in library to handle this but you can add case-specific stopwords as well.
  
   - Tokenization - This is breaking up text into sentences (sent_tokenize in nltk) or words (word_tokenize) and/or removing special characters (regex_tokenize in nltk), etc. There is also punkt tokenizer which uses punctuations well to give us sentences that make sense. eg. in a sentence with Mr. Snow, its considered as one single entity instead of mr, dot and snow. This depends on the use case such as topic modelling would use sentences and vectorizing (more on this later) would use word tokenization.
  
   - Stemming and/or Lemmatization - This is especially used in word-tokenized text for eventual vectorization. As jump, jumping, jumped all relate to jump but are different words, stemming would make them all jump. In the case of simply, simplify and simplicity into a single-stemmed word of 'simpl'. Lemmatization keeps the full word instead of stemmed simplified word and converts words such as ate, eat, eaten - all to 'eat'.
  
3. Processing (Use of built-in packages) OR in other words: the amazing world of existing packages
     Vectorization: This is one of the most useful feature - quantifying and qualitative text. Word vectorization means turning strings into numbers in n (whatever) dimensional space. There are several types of vectorizations and learning distance measures (euclidean, manhattan, cosine distances) for getting similarity out is essential.
   - Bag of Words - Here semantics go out of the window and words (stemmed or Lemmatized or both) are considered as 'tags'. Eg: CountVectorizer in sklearn.
   - TF-IDF (term frequency–inverse document frequency) which means rarer occurring words get more weight and vice versa. Eg. TfidfVectorizer in sklearn.
   - Word2Vec in gensim uses context/semantics to get similarity measures.
   - Word Embeddings (built-into gensim or run using keras): Converts text into matrix/numeric (vectorization) Skip Gram and CBOW methods are used to compute word embedding- It uses neural networks etc.
   -  n-gram vectorization: considers context in a proxy way - of taking consecutive n-word phrases and vectorizes the pair/group/party.
   -  Hashing: One of the simpler and faster (and consequently, not so great) and dirty (as the text itself is lost when it converts to vector) methods. However, there are use cases even for this, especially when speed is needed/computational resources are limited.
  
     Topic Modeling: This has trained on billions of documents and has a huge corpus containing all sorts of topics. It does a great job in (unsupervised) clustering documents/texts into topics and preserves the context/semantics. For example, apple, the store and apple, the fruit are considered and clustered in different clusters/topics based on their context. It also identifies synonymous and semantics in words such as nutrition: food, diet, sugar, etc. Eg. BERTopic Modeling. 

Packages in Python such as NLTK, Spacy, gensim, sklearn, scikit-surprise BERTopic, are some of the must-try packages for whatever use case in NLP and then deviate into specifics based on the case. Neural network methods (using keras), matrix factorization methods, and deep learning methods would be intermediate to advanced NLP processing tools which would give better results than the existing packages but are computationally taxing. 

