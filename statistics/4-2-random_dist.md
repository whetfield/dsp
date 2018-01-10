[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)


```python
import random
thousand_rands = [random.random() for x in range (0,1000)]
plt.clf()
plt.hist(thousand_rands, density=True, alpha = 0.5, edgecolor = 'r', cumulative = False, histtype = "step", bins = 10)
plt.show()
```
![pmf]()
