# trait evolution under OU model with shifts

## Background

The bootstrap method is now widely used in many research projects, especially in some cases   
when the sample size is small. The bootstrap method relies on randomly sampling with replacement  
and used for generating the estimators based on the sampling from certain distribution.   
The estimators produced by bootstrap are more accurate than directly measuring with sample   
variance and sample distribution.  


The bootstrap method is also beneficial for biostatistics, especially in the study of the   
evolutionary tree. In the real world, the data that has been collected is rare for each species,   
so using bootstrap method can produce a larger sample size and more accurate results for  
further analysis. In my research, I focused on the methodology of the bootstrap method on the  
phylogenetic tree which is a diagram showing the evolutionary relationships among different species.  

## Overview of the research

I conduct this research project with the help from Professor Cecile Ane.  
My research project title is “the procedure of bootstrap for high support of shift detection   
on phylogenetic tree”. The shift means the place on the phylogenetic tree where dynamic  
diversification occurs.Higher precision for detecting the shift is important because it  
justifies the places where the significantly morphological changes happened on the tree. Furthermore,   
it helps biologists figure out the relations with certain species which are morphologically similar  
and explore how they evolve into current states. The shifts show the process on how they evolve,  
and it is essential to make the detection as precise as possible.  
In the first part of experimental research, I used Lizard data from `l1ou` package.   
Later, after I derive a more “accurate” procedure for shift detection and methodology for bootstrap,   
I will apply it on the flower samples.  
