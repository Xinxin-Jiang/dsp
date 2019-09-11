[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)
#### Construct the actual distribution for #children under 18 in the respondents' households.  
> (Use the NSFG variable `numkdhh`)
```python
unbiased_pmf = thinkstats2.Pmf(resp.numkdhh, label='actual')
```
#### Assume we surveyed the children and asked #children under 18 in their household. Compute the biased distribution.
```python
biased_pmf = unbiased_pmf.Copy(label='biased')
for x, p in biased_pmf.Items():
    biased_pmf[x] *= x
    biased_pmf.Normalize()
```
#### Plot the actual and biased distributions. Compute their means.
```python
thinkplot.Pmf(biased_pmf)
thinkplot.Pmf(unbiased_pmf)
thinkplot.preplot(2)
thinkplot.Config(xlabel='Household Size', ylabel='frequency')
unbiased_pmf.Mean()
biased_pmf.Mean()
```
![sdf](../../../img/actual_vs_biased.png)
The actual mean is 1.024. The biased mean from survey is 2.404, more than twice of the actual.
