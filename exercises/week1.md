# Week 1 exercises

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
  
    1. Build a statistical model of the data: Use a [Binomial](https://en.wikipedia.org/wiki/Binomial_distribution) distribution as your likelihood and a [Beta](https://en.wikipedia.org/wiki/Beta_distribution) (alpha=1, beta=5) prior.
    1. Use grid approximation to compute the posterior of the proportion of people getting Covid-19 for a group receiving the placebo and a group receiving the BNT162b2 vaccine candidate respectively. Use the same prior for both models. Plot the two posteriors in the same plot. 
    1. What is the 98% HPDI of each posterior distribution?
    1. Under your model (small world) what is the 98% percentile interval of the number of cases of Covid-19 in a population of 5,8M people (the population of Denmark) for an unvaccinated and a vaccinated population respectively?
    1. Discuss how this compare to the actual number of positive test cases in Denmark, which is 296,196 per July 6th 2021 (large world).