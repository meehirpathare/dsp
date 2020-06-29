
Exercise 1**  *How much did you weigh at birth? If you don’t know, call your mother or someone else who knows. Using the NSFG data (all live births), compute the distribution of birth weights and use it to find your percentile rank. If you were a first baby, find your percentile rank in the distribution for first babies. Otherwise use the distribution for others. If you are in the 90th percentile or higher, call your mother back and apologize.*

**first import needed modules**

```python
from __future__ import print_function, division

%matplotlib inline

import numpy as np

import nsfg
import first
import thinkstats2
import thinkplot
```

**load data:**

```python
live, firsts, others = first.MakeFrames()
```

**get cdf for non-first born (I'm a second child)**

```
other_cdf = thinkstats2.Cdf(others.totalwgt_lb, label='other')
```

**get percentile rank**

```python
other_cdf.PercentileRank(7.6)
```

53.423852249353193513
