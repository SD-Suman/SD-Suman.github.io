---
layout: page
title: Rail Routes are a Key driver of Migration flows
subtitle: It may be very obvious but I used causal inference and a lot of learning and data cleaning 
tags:
  - bipartite network
  - network analysis
  - visualization
  - python
  - migration network
  - railway
  - rail route
  - rail network
published: true
---


### A curiosity driven serendipitous journey

Correlation is not causation. The professor in the Coursera course I audited (I only audit courses because I take information from various courses and textbooks, blogs, videos and papers). says: 'There is no causation without manipulation'. But you can apply causal inference not just from the treatment and control groups by performing randomized controlled trials but also from the treatment and control groups from observed data. To learn, in addition to all the theories and concepts, I wanted to test the causal inference to a well-known (to me) dataset of migration flows and a fairly known phenomenon to see what the causal inference methods say. This is faster and a lot of things get clearer with real-world data. Although there are many methods, I started focusing on Instrumental Variables and Difference-in-differences and learnt about confounders, control and treatment and so on! For IV I needed to know more about confounders, blocking, unaccounted confounders etc. and for DiD, I needed to know more about control and treatment groups in observational data and for causal inference in general, I needed to know about Directed Acyclic Graph (DAG). I have worked with time-series analysis, I love statistics and there is causal inference in time series as well - grager causality. Causal inference as is every other awesome topic is an ocean in itself. I am at the shore but: Onwards and upwards! 

#### Data

The migration data is the one I have used earlier in a [publication](https://www.nature.com/articles/s41558-021-01105-7). It uses 2001 and 2011 data from the Census of India, cleaned and filtered, where I have only considered inter-state migration. This is then converted into a bipartite network using networkx (python) with spatial data, which shows flows from states (state centroids) to districts (district centroids). 

I first got the idea for doing the bipartite network analysis while taking (auditing) the NPTEL course on network analysis where the csv [data](https://github.com/udit1408/Recovery_algorithm) was mentioned. It is from this [article](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0141890) where it mentions the data is up to 2014 which helps my case because I have migration data from 2001 and 2011 only (although 2011 was released in 2019). 

While I wanted to do a multi-layered bipartite network analysis where I wanted to see how the rail is related to migration network, I ended up exploring the different methods and ended up using causal analysis for bipartite networks. 

The cleaning took a long time - where I ran into tiny (read tiny to identify and find solutions but took long to clean) issues such as equalizing different network types and making a bipartite set of the rail network, bringing my migration data into network form, converting rail station data into district and state target and source dataset, keeping the nodes same for all three networks: 2001 mig, 2011 mig and 2014 rail, and I ended up cutting off rail networks which connect outside of the country and I have also kept the largest connected component as the rest of the data is not relevant to my question of if the two are related. Stand alone migration flows and rail routes are of no consequence in a causal analysis (is my interpretation). 

So I cleaned the data into three very beautiful bipartite networks with same nodes - node set a (states) and node set b (districts). I performed a lot of network analysis and statistical analysis to get to know the data - some of which make great sense to show here for a better understanding of the method and data; causal inference of the network datasets. 

We will call the rail network Gr and migration network G1 (2001) and G11 (2011), where G stands for graph (common variable name used in networkx, even though it is B for bipartite, but as it is still a graph..). 

### Rail network is a key driver of interstate migration in India

For the rail routes to be related to migration flows, the data need not be correlated. I got a weak positive correlation coefficient of ~ 0.37 of both 




