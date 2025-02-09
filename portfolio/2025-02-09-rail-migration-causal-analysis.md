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
  - self driven project
published: true
---


### A curiosity driven self-driven serendipitous journey

Correlation is not causation. The professor in the Coursera course I audited (I only audit courses because I take information from various courses and textbooks, blogs, videos and papers). says: 'There is no causation without manipulation'. But you can apply causal inference not just from the treatment and control groups by performing randomized controlled trials but also from the treatment and control groups from observed data. To learn, in addition to all the theories and concepts, I wanted to test the causal inference to a well-known (to me) dataset of migration flows and a fairly known phenomenon to see what the causal inference methods say. This is faster and a lot of things get clearer with real-world data. Although there are many methods, I started focusing on Instrumental Variables and Difference-in-differences and learnt about confounders, control and treatment and so on! For IV I needed to know more about confounders, blocking, unaccounted confounders etc. and for DiD, I needed to know more about control and treatment groups in observational data and for causal inference in general, I needed to know about Directed Acyclic Graph (DAG). I have worked with time-series analysis, I love statistics and there is causal inference in time series as well - grager causality. Causal inference as is every other awesome topic is an ocean in itself. I am at the shore but: Onwards and upwards! 

#### Data

The migration data is the one I have used earlier in a [publication](https://www.nature.com/articles/s41558-021-01105-7). It uses 2001 and 2011 data from the Census of India, cleaned and filtered, where I have only considered inter-state migration. This is then converted into a weighted bipartite network using networkx (python) with spatial data, which shows flows from states (state centroids) to districts (district centroids). 

I first got the idea for doing the bipartite network analysis while learning about [network analysis](https://www.youtube.com/watch?v=CbbkES6r-Fo) where the csv [data](https://github.com/udit1408/Recovery_algorithm) was mentioned. It is from this [article](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0141890) where it mentions the data is up to 2014 which helps my case because I have migration data from 2001 and 2011 only (although 2011 was released in 2019). 

While I wanted to do a multi-layered bipartite network analysis where I wanted to see how the rail is related to migration network, I ended up exploring the different methods and ended up using causal analysis for bipartite networks. 

The cleaning took a long time - where I ran into tiny (read tiny to identify and find solutions but took long to clean) issues such as matching and equalizing different network types and making a bipartite set of the rail network to make an analysis possible, bringing my migration data into network form, converting rail station data into district and state target and source dataset, keeping the nodes same for all three networks: 2001 mig, 2011 mig and 2014 rail, and I ended up cutting off rail networks which connect outside of the country and I have also kept the largest connected component as the rest of the data is not relevant to my question of if the two are related. Stand alone migration flows and rail routes are of no consequence in a causal analysis (is my interpretation). 

So I cleaned the data into three very beautiful weighted bipartite networks with same nodes - node set a (states) and node set b (districts). The weights for G1 and G11 are the number of people migrating and Gr is the number of trains connecting the pair of nodes (stations, which were then converted into state to district network). I performed a lot of network analysis and statistical analysis to get to know the data - some of which make great sense to show here for a better understanding of the method and data: causal inference of the network datasets. 

We will call the rail network Gr and migration network G1 (2001) and G11 (2011), where G stands for graph (common variable name used in networkx, even though it is B for bipartite, but as it is still a graph..). 

![image](/assets/img/causalrailmig/Clusteringc.png)

Analysing the three graphs individually, in the above plot, we can see nodes with yellow colors indicate higher clustering, meaning they have more similar connections to their neighboring nodes (state and district pairs) and are likely connected to similar destinations or origins. Nodes with bluer colors exhibit lower clustering, suggesting more dissimilar patterns in their connections compared to their neighbors, possibly indicating unique or isolated migration patterns or connections.

The weighted bipartite networks themselves look like this:
![image](/assets/img/causalrailmig/weightedbipartiteNs.png) where the weights are given by edge color and nodes are all the same blue. 

### Rail network is a key driver of interstate migration in India

For the rail routes to be related to migration flows, the data need not be correlated. I got a weak positive correlation coefficient of ~ 0.37 of both Gr with G1 and Gr with G11, while G1 and G11 are similar but G11 is of far greater magnitude; an r squared value (coefficient of determination) of ~ 0.14. 

Control and treatment in observed data here is visualized below:

![image](/assets/img/causalrailmig/controlandtreatment.png)

Here while the edge weights show the weights (flow of people or number of trains connecting the two node pairs), the red show the node has rail connectivity and blue nodes do not have rail connectivity. Here it is assumed that this is the case even before 2001. The 2014 rail data is also assumed to be present before 2011 - as in that there is not much changed between 2011 and 2014 - this is a very important assumption as the whole causal interpretation falls to ruin if we consider the rail routes were different before 2014. Here control are the nodes which are not connected by rail - between the year 2001 and 2011. And treatment are the ones that are. We are assuming that the rail data is also the same as 2014 between the year 2001 and 2011. As rail routes do not change drastically (given terrain and other physical features), this assumption most probably holds true.

#### Results 

I got a Difference in Differences result of 225.36 with a regression analysis with interaction terms result of following values where regression was controlled for treatment and control (binary 1 and 0), for year/time 2011 and 2001 (binary 1 and 0) and ineraction term (treatment x time) which gives the DiD effect. 

DiD Estimate: 4643.392623492884
Standard Error: 825.3869288494859
95% Confidence Interval: (3025.634242947892, 6261.151004037876)
The DiD estimate is statistically significant.

![image](/assets/img/causalrailmig/DiDParallelTrendsplot.png)



![image](/assets/img/causalrailmig/did95ci.png)



![image](/assets/img/causalrailmig/migflowsbeforeandaftertreatment.png)

I then looked at controlling for population of nodes as a confounding variable but got amazing results again:









