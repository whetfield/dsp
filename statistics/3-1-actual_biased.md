[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

Actual mean is 1.024

```python
resp['numkdhh'].mean()
```

Biased mean is 2.404

```python
(resp['numkdhh'] * resp['numkdhh']).sum() / resp['numkdhh'].sum()
```


```python
#NSFG module from ThinkStats reads in DataFrame
resp = nsfg.ReadFemResp()

resp.numkdhh.hist(density = True,grid = False, bins = 6, label = "Actual", alpha = 0.2)
resp.numkdhh.hist(density = True,grid = False, bins = 6, weights = resp.numkdhh, alpha = 0.2, label = "Biased")
plt.ylabel('PMF')
plt.xlabel('Number of Children')
plt.legend(loc= 'upper right')
plt.show()
```
![graph](biased_actual.png "Graph")
