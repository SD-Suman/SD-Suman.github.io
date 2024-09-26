---
layout: page
title: Emotional Arc of the most read book in the world
subtitle: Sentiment analysis on the Bible using NLP 
tags:
  - NLP
  - visualization
  - python
published: true
---

Inspired by Kurt Vonnegut's 'emotional arc', I thought I should look at the emotional arc of the most read book in the world. While building a recommendation system using NLP involves a lot of vectorization and distance calculations, sentiment analysis is relatively simpler. 

First the overall sentiments in the book shown by the humble pie:
![image](/assets/img/sentiment_pie.png)

Next the interesting distribution (kernel density) to look at the distribution of these sentiments. The compound can take super negative values (as seen below) if the compound leans more towards 'highly negative' and similar for positive. So the compound is balanced along with the presence of neutral. 
![image](/assets/img/sentiment_density.png)

Coming to the main part: the emotional arc of the book. Although emotional arc is seen for stories which are in sequence, and while the version I analysed - Gutenberg's KJV Bible - is not in a chronological order, the emotional arc still makes sense in that it shows the general sentiments (averaged over a segment size of 5 consecutive sentences and moving average window of 1000), we get the emotional arc of the Book - which is Rise-Fall-Rise and is one of the 6 popular arcs!

![image](/assets/img/sentiment_emotionalarc.png)


