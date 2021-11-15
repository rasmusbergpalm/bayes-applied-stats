# Week 5
**Interactions and MCMC**

1. Answer 9E3 in the book. (page 303)
1. Answer 9E4 in the book. (page 303)
1. Answer 9E5 in the book. (page 303)
1. Answer 9E6 in the book. (page 303) 
1. Load the data in [week5.csv](week5.csv). Your task is to accurately model the fourth column of the data using the first three as predictors. Compare at least the following models: 
    - a linear model with no interactions, 
    - a linear model with all pair-wise interactions
    - a linear model with all pair-wise and triple-wise interactions. 
    
    Use MCMC for the inference (`pm.sample()`). Ensure that your inference is valid by considering effective sample sizes (ess), R-hat and trace plots (`az.plot_trace`, `az.summary`).  
    Which is better? How good a model can you find? Be creative. Hint: it's possible to find a **very** good model.
1. **BONUS** Answer 9H6 in the book (page 305). 
