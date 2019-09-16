[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)
### Q: Percentage of the U.S. male population between 5’10” and 6’1”?

* First, construct the height distribution for male using parameters (µ = 178 cm and σ = 7.7 cm).  
* Next, substract the portion of height below 5'10''(177.8cm) from the percentage of height below 6'1''(185.42cm)  
```python
dist=scipy.stats.norm(loc=178, scale=7.7)
dist.cdf(185.42)-dist.cdf(177.8)
```
The percentage of U.S. male between 5'10" and 6'1" is about 34.27%.
