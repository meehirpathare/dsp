
Exercise 1**  *In the BRFSS (see Section* [*5.4*](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#lognormal)*), the distribution of heights is roughly normal with parameters* µ = 178 *cm and* σ = 7.7 *cm for men, and* µ = 163 *cm and* σ = 7.3 *cm for women.*

*In order to join Blue Man Group, you have to be male between 5’10” and 6’1” (see* [*http://bluemancasting.com*](http://bluemancasting.com/)*). What percentage of the U.S. male population is in this range? Hint: use `scipy.stats.norm.cdf`.*

**import all needed packages**

```python
from __future__ import print_function, division

%matplotlib inline

import numpy as np

import nsfg
import first
import analytic

import thinkstats2
import thinkplot
```

**import data file**

```python
import scipy.stats
```

**input parameters**

```python
sigma = 7.7
mu = 178
dist = scipy.stats.norm(loc=mu, scale=sigma)
type(dist)
```

**calculate mean, std**

```python
dist.mean(), dist.std()
```

**eligible population**

```python
#5' 10''
low = dist.cdf(177.8)    
#6' 1''high = dist.cdf(185.4)   
low, high, high-low
```

**output:**

```
(0.48963902786483265, 0.8317337108107857, 0.3420946829459531)
```

**34% of the male population could be in the Blue Man Group**
