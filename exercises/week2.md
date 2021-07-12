# Week 2 exercises

**Golem building, prior predictive checks and regression.**

1. Define simple statistical models for the following hypothetical situations. Write them in the standard notation. 
    1. You've performed an A/B test on a online webshop, testing two different versions of a checkout flow; 
    when a user first enters the webshop they are assigned randomly to variant A or B of the checkout flow.      
    You've recorded the number of users assigned to each variant and the number of those users that make a purchase for each of the two variants.
    1. The doctors at a hospital maternity ward hypothesize that the average birth weight of infants is lower if the mother smoked during pregnancy. 
    To investigate they have recorded the birth weight of every newborn (in grams, e.g. 3534 grams) and also noted the smoking habits of the mother during pregnancy (binary: smoker or not). 
        
1. Perform prior predictive checks for your two models above; Plot the distribution of simulated data under your priors. Refine your priors and likelihoods if needed.       

1. You're working at Tesla, and your job is to improve the range prediction for the Model 3 SR plus. The range prediction tells the driver how far they can expect to drive based on the current battery level. 
   You decide to model the maximum range (km) the car can drive given a full battery as a function of the average speed at which the car drives (km/h), since you know air resistance increases with speed.
   1. Define a statistical model for the data and write it in standard notation. Use your prior scientific knowledge of the world in your model!
   1. Perform prior predictive checks and calibrate your likelihood and priors so the prior predictive data looks reasonable.
   1. You collect the following dataset of average speed and max range given a full battery.
       ``` 
       average speed    [ 65.9  99.2  20.   53.3  36.1  30.2  40.5  58.   63.6  79.3  66.1  95.4  42.5 116.6  23.   93.8  65.9  81.5  35.4  41.8]
       max range        [422.3 333.8 456.5 420.2 447.7 457.9 432.3 434.1 423.4 392.6 419.6 347.  440.1 290.5 454.  362.8 404.  379.4 441.1 433.6]
       ```
       Find and plot the posterior using the quadratic approximation. Plot the pairwise posterior distributions as well (`arviz.plot_pair`).
   1. Use your model to estimate the range left if the car has 76% battery left. Describe your assumptions and report a 95% credible interval under your assumptions. 
   1. Elon Musk tells you that you must report a single number for the estimated range left. Pick a single number and argue why it's the right one.  
   
    