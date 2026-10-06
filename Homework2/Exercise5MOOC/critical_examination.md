# Critical examination of the Challenger O-ring analysis

## What is good about the original analysis

The original analysis follows a clear step-by-step approach. It first loads and inspects the data, then looks at the relationship between temperature and O-ring malfunction, and finally uses logistic regression to estimate the probability of malfunction. The choice of logistic regression is appropriate because the objective is to estimate a probability between 0 and 1. The binomial model is also reasonable under the assumption that the six O-rings have the same probability of malfunction and behave independently.

## What is wrong with the analysis

The main problem is the filtering step:

```python
data = data[data.Malfunction > 0]
```
The analysis then states that flights without incidents do not provide information about the influence of temperature or pressure. This assumption is incorrect. A flight with zero malfunction is still an observation and provides important information about the probability of failure under those temperature and pressure conditions.
By removing all the zero-malfunction flights, the analysis only considers flights where at least one failure has already occurred. This introduces a selection bias. In particular, many of the flights at higher temperatures had no malfunction, and removing them hides an important part of the relationship between temperature and failure. As a result, the original logistic regression finds almost no effect of temperature.
