---
layout: post
title: A quick look at Natural Language Processing
subtitle: Quick introduction to NLP 
tags:
  - Python
  - NLP
published: true
---

I worked on building Recommender systems in one of my jobs as a data scientist, which was exciting, to say the least. It was an exploration into unknown tools, methods and a whole different dimension of ML that I could not have even imagined before. I only knew of quantitative, spatial and time series data science before stepping into NLP but this depth into ML shows how qualitative text data can be used as quantitative when we 'vectorize' it and then there is 'semantics' which deciphers its meaning in a way only a machine can. Using NLP, I built a few recommender systems and devised quantitative tools to evaluate each against each other. So here is a little introduction to Natural Language Processing which may help people step into it. It helps to know basic string manipulation (join, split, replace, etc.), use of 'regex' (regular expression, \r'text'), escape characters and others before starting the steps of cleaning and processing. 

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
  
   - Tokenization - This is breaking up of text into sentences (sent_tokenize in nltk) or words (word_tokenize) and/or removing special characters (regex_tokenize in nltk), etc. There is also punkt tokenizer which uses punctuations well to give us sentences that make sense. eg. in a sentence with Mr. Snow, its considered as one single entity instead of mr, dot and snow. This depends on the use case such as topic modelling would use sentences and vectorizing (more on this later) would use word tokenization.
  
   - Stemming and/or Lemmatization - This is especially used in word tokenized text for eventual vectorization. As jump, jumping, jumped all relate to jump but are different words, stemming would make them all jump. In case of simply, simplify and simplicity into a single stemmed word of 'simpl'. Lemmatization keeps the full word instead of stemmed simplified word and converts words such as ate, eat, eaten - all to eat. 

  







Work Under Construction




   
