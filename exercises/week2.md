# Week 2 exercises
**Model building, prior predictive checks and regression.**

For this exercise you should use [PyMC3](https://docs.pymc.io/en/stable/) to define your models, [pymc3-quap](https://github.com/rasmusbergpalm/pymc3-quap) for estimating the posterior and [ArviZ](https://arviz-devs.github.io/arviz/) for visualization and reporting. You can use `pip install pymc3 pymc3-quap arviz` to install all three packages.

1.  You've performed an A/B test on a online webshop, testing two different versions of a checkout flow; 
    when a user first enters the webshop they are assigned randomly to variant A or B of the checkout flow.      
    You've recorded the number of users assigned to each variant and the number of those users that make a purchase for each of the two variants.
    1. Define a simple statistical model for the data. Write it in the standard notation.           
    1. Perform prior predictive checks for your model; Plot the distribution of simulated data under your prior. Refine your prior and likelihood if needed. Hint: use `pymc3.sample_prior_predictive`
    1. Assume you observe the following data: (Variant=A, N=983, n_purchase=19), (Variant=B, N=1023, n_purchase=27). Find the posteriors using `quap` and plot them using `arviz.plot_posterior` and `arviz.plot_forest`.
    1. What is the probability that variant B is better? (Leads to more purchases). If your manager asked, would you recommend adopting variant B? 
1. You're working at Tesla, and your job is to improve the range prediction for the Model 3 SR plus. The range prediction tells the driver how far they can expect to drive based on the current battery level. 
   You decide to model the maximum range (km) the car can drive given a full battery as a function of the average speed at which the car drives (km/h), since you know air resistance increases with speed.
   1. Define a statistical model for the data and write it in standard notation. Use your prior scientific knowledge of the world in your model!
   1. Perform prior predictive checks and calibrate your likelihood and priors so the prior predictive data looks reasonable. Hint: use `pymc3.sample_prior_predictive`
   1. You collect the following dataset of average speed and max range given a full battery. hint: Use `np.fromstring("1 2 3", sep=" ")` to load.
       ``` 
       average speed     65.9  99.2  20.   53.3  36.1  30.2  40.5  58.   63.6  79.3  66.1  95.4  42.5 116.6  23.   93.8  65.9  81.5  35.4  41.8
       max range        446.6 352.4 455.9 419.9 452.1 466.5 426.2 455.6 444.6 416.5 441.7 367.5 444.3 321.9 452.9 394.5 410.1 395.3 438.  430.4
       ```
       Find and plot the posterior using pymc3 and the  quadratic approximation. Plot the pairwise posterior distributions as well (`arviz.plot_pair`).
   1. What is the 94% HPDI of the range if the car is travelling at an average speed of 100 km/h?
   1. **Bonus**: Use your model to estimate the range left if the car has 76% battery left. Describe your assumptions and report a 98% credible interval under your assumptions. 
   1. **Bonus**: Elon Musk tells you that you must report a single number for the estimated range left at 76% battery. Pick a single number and argue why it's the right one.  
   
    
