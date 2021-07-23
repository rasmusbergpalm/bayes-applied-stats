# Week 1 exercises
**Model building, posterior inference, posterior differences, small and big worlds.**

1. Describe in your own words the following terms in a single sentence each: probability, data, small world, large world, model, prior, likelihood, posterior.

1. The following is an excerpt from the [2020 Pfizer Covid vaccine paper](https://www.nejm.org/doi/full/10.1056/nejmoa2034577).

    > BACKGROUND.
    Severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2) infection and the resulting coronavirus disease 2019 (Covid-19) have afflicted tens of millions of people in a worldwide pandemic. Safe and effective vaccines are needed urgently.
    >
    > METHODS.
    In an ongoing multinational, placebo-controlled, observer-blinded, pivotal efficacy trial, we randomly assigned persons 16 years of age or older in a 1:1 ratio to receive two doses, 21 days apart, of either placebo or the BNT162b2 vaccine candidate (...).
    >
    > RESULTS.
    A total of 43,548 participants underwent randomization, of whom 43,448 received injections: 21,720 with BNT162b2 and 21,728 with placebo. There were 8 cases of Covid-19 with onset at least 7 days after the second dose among participants assigned to receive BNT162b2 and 162 cases among those assigned to placebo.
  
    1. Build two separate statistical models (Golems) of the data, one for the vaccinated group, and one for the placebo group: Use a [Binomial](https://en.wikipedia.org/wiki/Binomial_distribution) distribution as your likelihood and a [Beta](https://en.wikipedia.org/wiki/Beta_distribution) (alpha=1, beta=5) prior for both models.
    1. Plot the beta(1, 5) prior. 
    1. Use grid approximation to compute the posterior of the proportion of people getting Covid-19 for both models. Plot the two posteriors in the same plot. 
    1. Sample 10,000 samples from each posterior. What is the 98% HPDI of each posterior distribution?
    1. Estimate the efficacy of the vaccine as 100*(1 - pv/pp), where pv and pp are probability of getting infected given the vaccine and pp is the probability of getting infected given placebo. To compute any posterior differences use samples from the two posteriors (See book page 162 - Rethinking: Differences and statistical significance.): 
        ```
       vaccine_posterior_samples # shape: (10_000,)
       placebo_posterior_samples # shape: (10_000,)
       eff = 100 * (1 - vaccine_posterior_samples/placebo_posterior_samples) # shape: (10_000,)      
       ```
       Plot this distribution over efficacy and report a 95% HPDI. 
    1. Under your model (small world) what is the 96% percentile interval of the number of cases of Covid-19 in a population of 5,8M people (the population of Denmark) for an unvaccinated and a vaccinated population respectively?
    1. Discuss how this compare to the actual number of positive test cases in Denmark as of July 6th 2021 which is 296,196 (large world).

    NOTE: This is not a very good model of the efficacy of vaccination, and were not using the exactly right numbers! 
    You should trust the paper which reports a 95% efficacy credible interval of 90.3 to 97.6 percent. 

**Bonus**: A much better model would model the **rate** of infections using e.g. a [Poisson distribution](https://en.wikipedia.org/wiki/Poisson_distribution) and a suitable prior. The relevant data in the paper. 

 