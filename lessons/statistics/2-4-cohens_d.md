[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

#### 1. Investigate whether first ba- bies are lighter or heavier than others, compute Cohen's d:
* First, calculate the mean birth weight for 2 groups & take the difference
* Second, compare the two means by computing Cohen's d. 

```python
firsts_mean_wgt = firsts['birthwgt_lb'].mean()
others_mean_wgt = others['birthwgt_lb'].mean()
wgt_lb_diff = firsts_mean_wgt - others_mean_wgt
wgt_oz_diff = wg_lb_diff*16  
```
Mean weight for first babies is 7.201lb; mean weight for others is 7.326lb. The difference is -0.125 lb, or -1.996oz.  
The mean weight for first babies is 1.996oz lower than others.

```python
n1 = len(firsts)
n2 = len(others)
var1 = firsts.totalwgt_lb.var()
var2 = others.totalwgt_lb.var()
var_pooled = (var1*n1+var2*n2)/(n1+n2)
std_pooled = thinkstats2.math.sqrt(var_pooled)
wgt_CohenD = wgt_diff/std_pooled
print(wgt_CohenD)
```
Cohen's d equals -0.089.  
The mean weight for first babies is 0.0887 standard deviations lower than others, which is small.

#### 2. How is that compare to the difference in pregnancy length?
Compare the absolute values of two Cohen's d's: 0.089 > 0.029.  
The difference in birth weight is larger than in pregnancy length. 
