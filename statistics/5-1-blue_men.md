[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

Solving for the pecentage of men with heights between 177.8 cm and 185.42 cm (conversion of 5'10" and 6'1" to centimeters).  "scipy.stats.norm is an object that represents a normal distribution; it provides a method, cdf, that evaluates the standard normal CDF" (ThinkStats, p.60) We can subtract the value of the standard normal cdf at the standardized value for 177.8 to get the probability a man has a height less than or equal to 5'10" from the standard normal cdf value at 185.42cm (probabilty man has height less than equal to 6'1") to get the probabilty height is between the two.  

Get appropriate z-value for each height h from (h-mu) / standard deviation:

**z-value for 177.8cm = (177.8 - 178) / 7.7 = -0.026**

**z-value for 185.42cm = (185.42 - 178) / 7.7 = 0.964**

```python
from scipy import stats
stats.norm.cdf(0.964) - stats.norm.cdf(-0.026)
```

About 34% of male population is between those two heights
