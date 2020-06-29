[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

**Exercise 4**  *Using the variable `totalwgt_lb`, investigate whether first babies are lighter or heavier than others. Compute Cohen’s* *d* *to quantify the difference between the groups. How does it compare to the difference in pregnancy length?*



From the text, we are given the function for Cohen effect size

```python
def CohenEffectSize(group1, group2):
    """Computes Cohen's effect size for two groups.
    
    group1: Series or DataFrame
    group2: Series or DataFrame
    
    returns: float if the arguments are Series;
             Series if the arguments are DataFrames
    """
    diff = group1.mean() - group2.mean()

    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)

    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / np.sqrt(pooled_var)
    return d
```

​	*First, compute the means of first babies and subsequent*

`firsts.totalwgt_lb.mean(), others.totalwgt_lb.mean()`

​	*which gives 7.20 lbs for a first born and 7.36 lbs for later children*

```python
(7.201094430437772, 7.325855614973262)
```

​	*Now, calculate the Cohen effect size*

`CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)`

`-0.088672927072602`

​	*Computing pregnancy length means for first baby and later*

`firsts.prglngth.mean(), others.prglngth.mean()`

```python
(38.60095173351461, 38.52291446673706)
```

​	*The difference between the two is*

`firsts.prglngth.mean() - others.prglngth.mean()`

```python
0.07803726677754952
```

​	*For Cohen effect size*

`CohenEffectSize(firsts.prglngth, others.prglngth)`

```python
0.028879044654449883
```

**The effect of birth order is about 3 times stronger than the difference in pregnancy length**
