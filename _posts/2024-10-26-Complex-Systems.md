---
layout: post
title: Complex Systems and Power Laws
subtitle: Simplified answer to the question - "What are Complex Systems?"
tags:
  - complexity
  - brief
published: true
---

## Complex Systems 

Towards the end of our Masters in Regional Planning, a question was asked by a guest lecture: what is regional planning? The class was silent with all brains going to every direction. Some of us, having studied planning for 6 years, had so many answers, we went silent. Complex system is one of those complex questions too. You know what it is, but there is just so much to be explained. 

#### Cellular Automata 

I came across complex systems during a bachelor's assignment on spontaneous planning. This was for a case when there are natural disasters and people from the areas had to be temporarily evacuated. The prediction for the areas, how it be done, and others could be simulated using complex system: particularly, cellular automata (CA) or even agent based modeling. CA could also be used to predict a city's growth (SLEUTH model: Slope, Land Use, Exclusion, Urban, Transportation, Hillshade) and used in so many more models.  

<!---
![image](/assets/img/CA.jpg)
--->

Imagine a part of the city outskirts - plan represented in (A) and neatly boxed into grids. Some of these grids are developed shown in black shaded portion, some are free to be developed. (B) shows the area of interest: one 'cell' where we want to know if that will be developed next. In an extremely simplified CA model, that depends on the cells immediately surrounding it and nothing else. So based on such rules complex models of this type of complex system is used in SLEUTH models for predicting a city's growth spatially. 

### Other complex system science fields:

**Agent based modeling** is another super exciting area where you could, for example, get the whole (maybe macroeconomics?) from the sum of its parts (microeconomics) and it would not be a simple addition. 

**Complex Networks** is a whole another field which looks at the connectedness - through edges and nodes.

Anything that considers non-linear dynamics, chaos, scale-free, unpredictable - or at least difficult to predict, with 'stochatic' elements is included in complex systems and has a large scope of application as most real world phenomenons are complex in nature. 

<!---
It has taken me long to understand some of the details and I am always learning something new (and also forgetting a few things along the way similar to my experience with statistics). While my journey has been self-taught, I believe, all you need is interest and time to pursue interesting things even if its not been a formal education.  
--->

## Fractals 
Fractals are repeated patterns but they have non-integer values as their dimention/scaling factor (alpha). 

## Power Laws

This took me a while to wrap my head around it but here are a few interesting things to know about power law distributions:

* It is 'scale-free'. Which means that:

	* There is no clustering of values around any moments (mean, median, mode, rate of decay etc.
    
	* It has infinite variance - long tails - tending to infinity - most values in the start and very few but very large values at the other end - primacy in cities - sizes of cities 

	* No typical range or numbers - of how small or large the numbers can be 

	* If you zoom in anywhere, the graph looks the same - what does this mean?

* It related to fractals in its self similarity characteristic - zoom in and see the same pattern 

* Central limit theorem doesn't apply to this distribution

* It has a large majority of small numbers, very few and far spread-out large numbers in distribution 

* Occurs in real world a lot (normal distribution is most common in controlled setting), especailly in dynamic systems which exhibits self similarity and other characteristics of complex systems such as feedback, extreme events, feedback dependent, etc. 


#### Formula of Power Law distribution:

P(x) = C*(x^-α)

α>0, and the negative power indicates that as x increases, P(x) decreases, leading to a rapidly declining probability for larger events.

And very interesting to note that α is typically a float value typically between 2 to 3 for real world cases [similar to fractals that have dimension D in the range typically between 0 and 3 as a fraction]. If α is closer to 1, the probability of large numbers occuring is less rarer than if α was >3. For Zipf's law (generally taken for rank of a city being inversely proportional to city size), the α is closer to 1 or an integer value; so cities are less complex than most real world pheonomenon!? This gives me hope for solving issues of settlements, if this were true! 
