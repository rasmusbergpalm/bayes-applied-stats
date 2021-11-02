# Week 3 
**Multiple regression, confounding, DAGs, bias and backdoors**

1. Solve exercise 5H1, from the book (page 164). Load the data with
   ```python
   import pandas as pd
   data = pd.read_csv('https://raw.githubusercontent.com/rmcelreath/rethinking/master/data/foxes.csv', sep=";")
   ```
2. Solve exercise 5H2, from the book (page 164). Use `az.plot_forest([m1_posterior, m2_posterior, m3_posterior], model_names=["m1", "m2", "m3"])` to compare the three posteriors.
3. Define the following concepts and explain how they can lead to false causal inferences:
   1. Spurious associations
   2. Masked relationships
   3. Multi-colinearity
   4. Post treatment bias
4. In the 40s and 50s tobacco use was recognized as a major cause of lung cancer. It was a hard won battle of science against the tobacco industry, with a massive public health impact [1]. 
At the time however, tobacco companies offered another plausible theory, namely that of increased environmental pollution from e.g. coal plants, car exhaust and tarred roads as being the cause of increased cases of lung cancer. 
Conveniently, this pollution exposure was hard to measure. Can we still estimate the effect of smoking despite this unmeasured pollution?  
    1. Create a DAG using [daggity.net](http://www.dagitty.net/dags.html) to estimate the total effect of smoking on lung cancer. Show the DAG as an image. The DAG should contain the following variables:  
        - Lung cancer (yes/no) - **Outcome**
        - Smoking (Estimated total lifetime tobacco use) - **Exposure**
        - Pollution (Total lifetime pollution exposure) - **Unobserved**
        - Gender
        - Age
        - [Socioeconomic Status](https://en.wikipedia.org/wiki/Socioeconomic_status)
    1. What are the testable independence assumptions the model implies? Do they seem reasonable?
    1. Can you estimate the total effect of smoking on lung cancer given this model? If so, what is the minimal adjustment set needed to estimate the total effect of smoking on lung cancer?
    1. Add a single arrow to the DAG such that it becomes impossible to estimate the effect of smoking on lung cancer.      

[1] - https://tobaccocontrol.bmj.com/content/21/2/87 - Unfortunately, 1.5 million people still die every year from lung cancer caused by tobacco use. 
