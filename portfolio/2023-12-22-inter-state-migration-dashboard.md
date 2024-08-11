---
layout: page
title: Inter-State Migration Dashboard
subtitle: Incoming and Outgoing migration from States using Census of India 2011 data
tags:
  - dashboard
  - R
  - migration
  - visualization
  - data analysis
  - statistics
published: true
---

**An interactive dashboard created using R Shiny**

Migration data is from the Census of India website and the data was analysed for the [publication:](https://www.nature.com/articles/s41558-021-01105-7) and another publication using the data is under progress as well.

For now, I have used a simple state-wise incoming and outgoing migration visualization for inter-state migration data for India. 

[Click here to access the Shiny App](https://sumandharmasthala.shinyapps.io/MigDashboard/)

A screenshot of the app with one state selected is below. You can exlore 'To' and 'From' migration patterns for different states from the shiny dashboard (from link) above. 
![image](/assets/img/OutMig_fromUP.png)
 
Please note that the incoming migrants (dots and lines) are to each district in the state while the outgoing migrant data is only available for each state (so the centroid of the state is considered).
