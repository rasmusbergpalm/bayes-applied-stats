# Week 4 
**Overfitting and model comparison**

Note: The `InferenceData` object returned by `quap` doesn't contain the log pointwise predictive densities which are needed for model comparison. So in this weeks exercise you should use `idata = pm.sample(return_inferencedata=True)` instead for finding the posterior. It uses Markov Chain Monte Carlo to approximate the posterior. We'll get to what that is in the next lecture, but for now just use it. 

Also, take a look at this [PyMC3 model comparison example](https://docs.pymc.io/en/stable/pymc-examples/examples/diagnostics_and_criticism/model_comparison.html) 

1. Explain what overfitting is and why models with more parameters are more susceptible to overfitting.
2. Explain why regularizing priors can prevent overfitting.
3. Explain why cross-validation (CV) is a good measure of how good the model is at modelling the data. 
4. Explain why CV, WAIC or PSIS-LOO-CV cannot be used to infer causation.
5. Create a DAG for the foxes dataset from last week.
6. Solve 7H5 (page 240) - Use both PSIS-LOO-CV `az.compare(..., ic='loo')` and WAIC `az.compare(..., ic='waic')`
