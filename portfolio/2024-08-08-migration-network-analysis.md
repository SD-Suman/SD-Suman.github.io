---
layout: page
title: Which cities have the potential for growth according to migration patterns?
subtitle: In-degrees and pagerank analysis
tags:
  - network analysis
  - map
  - visualization
  - data analysis
  - statistics
  - python
published: true
---

%## Which cities have the potential for growth according to migration patterns? 

I analysed the 2001 and 2011 migration data by first converting it into a bipartite network - as the data available is state to district migration making it a directed bipartite graph. As I also have the migration flow values, which I used as weights, I now had a weighted directed bipartite graph. 

The data cleaning and getting nodes and their coordinates in one Excel file and edge list with weights with the same IDs in the node file with new IDs given to states was a task in itself. While that was fun, network analysis and especially looking up kinds of analysis that will help me find what I want answered was even more fun. 

The question I wanted to be answered was: Which districts, according to migration patterns of 2011 and 2001 combined, have growth potential? The results gave me two different kinds of districts which have potential - ones which can develop on their own without any help - as it is happening already with large in-migration as a proxy and another set which are so behind (given by proxy of migration data again) that migration has decreased to the districts between 2001 and 2011. Here migration is assumed to be positive as incoming migration means there are employment opportunities, as that is the major reason for migration in India.

I chose PageRank (PR) analysis to find the potential districts. PR was developed by Google for recognizing prominent pages in a website. Generally, if there are lots of edges connected to a node, that is identified as a prominent node (degree centrality) but in PR, a node is prominent even if there is say just one node connecting to it but that connection has some centrality or its inherent prominence, in turn increasing the prominence of this node with only one in-degree. In migration patterns, PR, especially in a directional bipartite graph, would give me the relative importance of a node as the PR values add up to 1. In other words, I have 640 districts, and if a random walked chose to migrate to any district, the probability of him going to any of the districts is 0.0015625 (1/640). In my PR analysis, the values based on migration patterns of 2011 and 2001 ranged from 0.000664 to 0.006547 showing how different districts (nodes) have different 'prominence'. 

The highest PR value was for Bangalore. I got high PR values for districts which have not seen much in-migration but may have a lot of out-migration (there is no data for out-migration in the Census). To see which are the two different kinds of districts of 'prominence': one which is already prominent, and another which needs to be focused on and developed are got by weighted in-degree values. PR values and weighted in-degree values have a correlation coefficient of 0.33, which is 



![image](/assets/img/WID_PR.png)
