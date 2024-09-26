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

A sample of 5 from the Positive, Negative, Neutral and Compound sentences are in the table below:

| Positive text                                           | Neutral text                                                                                                                                   | Negative text                                 | Compound text                                                                                                                                                                                                 |
|---------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| But godliness with contentment is great gain            | and I am full of tossings to and fro unto the dawning of the day                                                                                 | Jesus wept                                    | Great is my boldness of speech toward you great is my glorying of you I am filled with comfort I am exceeding joyful in all our tribulation                                                                   |
| A gracious woman retaineth honour and strong men retain riches | if a man speak surely he shall be swallowed up                                                                                                  | And Hezekiah wept sore                        | And there was given me a reed like unto a rod and the angel stood saying Rise and measure the temple of God and the altar and them that worship therein                                                     |
| Blessed be God                                          | And his mother said Blessed be thou of the LORD my son                                                                                          | Alas                                          | If the theft be certainly found in his hand alive whether it be ox or ass or sheep he shall restore double                                                                                                   |
| Rejoice evermore                                        | And the man brought the men into Josephs house and gave them water and they washed their feet and he gave their asses provender                  | And Hezekiah wept sore                        | She openeth her mouth with wisdom and in her tongue is the law of kindness                                                                                                                                     |
| can faith save him                                      | O wretched man that I am                                                                                                                        | Recompense to no man evil for evil            | Yea he loved the people all his saints are in thy hand and they sat down at thy feet every one shall receive of thy words                                                                                     |

---


