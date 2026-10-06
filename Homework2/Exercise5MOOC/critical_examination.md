# Critical examination of the Challenger O-ring analysis

## What is good about the original analysis

The original analysis follows a clear step-by-step approach. It first loads and inspects the data, then looks at the relationship between temperature and O-ring malfunction, and finally uses logistic regression to estimate the probability of malfunction. The choice of logistic regression is appropriate because the objective is to estimate a probability between 0 and 1. The binomial model is also reasonable under the assumption that the six O-rings have the same probability of malfunction and behave independently.

## What is wrong with the analysis

The main problem is the filtering step:

```python
data = data[data.Malfunction > 0]
