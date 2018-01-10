[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

Other births are 0.089 standard deviations heavier than first births.  This is a larger difference than the 0.029 standard deviations higher average for first pregnancy lengths than other birth pregancy lengths 
See code below.  Believe ThinkStats code has minor issue as len is used instead of count, so NA not ignored.  

```python

import numpy as np

def cohens_d (series1, series2):
    """
    Calculate cohens d, the difference in means divided by pooled standard
    deviation
    
    Args:
        series1: numpy series of first population
        series2: numpy series of second population
    
    Return:
        cohens_d: float, cohens d value
    """
    
    mean_diff = series1.mean() - series2.mean()
    
    pooled_var = (series1.count() * series1.var() + series2.count() * 
                  series2.var()) / (series1.count() + series2.count())
    
    cohens_d = mean_diff / np.sqrt(pooled_var)
    
    return cohens_d 


def calc_cohens_birthsdata (df):
    """
    Pass the births dataframe from ThinkStats2 and get cohens_d
    for birth weights
    """
    #Create two separate datafranes for first children and others
    first_births = df[df['birthord'] == 1]
    other_births = df[df['birthord'] != 1]
    
    return cohens_d(first_births['totalwgt_lb'], other_births['totalwgt_lb'])
```
