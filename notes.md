### Exploratory Data Analysis 

* There are 1,944,210 row in this initial training partition with 92 columns 
    * You have date_id, time_id, symbol_id, weight, features (X), and then responder (Y)
* Finding that there are some features which have all NA values. Based on the training partition we have, we have: 
    * 00, 01, 02, 03, 04, 21, 26, 27, 31. We can easily drop these though
    * After you take these out, you see that the worst case scenario is missing 16.7% of the values. Which is not THAT bad. We could either impute these values or we can drop any that have missing at all
* Looking at the weights, seems that they are skewed toward the right with most of them at like 1.5 or something. 
    * I really wonder what the weight means though in real life. 
* Most of the features are floats with some integers in there though which is not bad. 
* When looking at these distributions, we just have so many shapes and sizes to work with. 
* The distribution of the responder variable looks very T-distributed which is interesting. It's probably some sort of return or something over a time step. 
* In terms of correlations, we are seeing that feature_06 has the highest pearson correlation with the target. This is followed by feature_07, feature_05, and then drops off to 68 and 51. 
    * Running a simple correlation plot, we can see that feature 6 and feature 7 are correlated to each other, signaling that they might be measuring similar things. 
* When you visually inspect these correlation, you see a TON of noise, but this is expected in financial data. You are trying to pick up a very small signal. However, if you can even eek out a positive r^2 that means you can make a lot of money if you trade a TON of times. 


Questions: 
* What are the correlations of the features with the target? --> responder_6? Are there any clear correlations that we can see? 
* What are the correlations of these with each other? Is there some collinearity that is going on? 
* What are the distributions like for each of these? 