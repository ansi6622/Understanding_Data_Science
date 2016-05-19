# Functions to Know

Python 2.7

### Mean
 - Add up the values in a data set and divide by the number of values.

<img src="https://github.com/gravity226/Understanding_Data_Science/blob/master/imgs/mean_pic.png" height="100">

(img Reference: http://www.ablongman.com/graziano6e/text_site/MATERIAL/statconcepts/central.htm)

Example 1
``` python
# if you don't import division then you'll need to convert numbers to decimals before dividing
from __future__ import division

data = [1, 4, 2, 7, 9]

mean = sum(data) / len(data)

print mean
```
``` output
> 4.6
```

Example 2
``` python
import numpy as np
data = np.array([1, 4, 2, 7, 9])

print data.mean()
```
``` output
> 4.6
```

Example 3
``` python
import pandas as pd
data = pd.DataFrame([1, 4, 2, 7, 9])

print data.mean().values
```
``` output
> [ 4.6]
```

Potential problems with using the mean:
 - If there are outliers your mean will be skewed.

Example 4
``` python
import numpy as np
data = np.array([3, 4, 7, 2, 4, 43])

print data.mean()
```
``` output
> 10.5
```

### Median
 - The middle value in your data set.

Example 1
``` python
data = [23, 12, 27, 99, 14, 37, 15]
data = sorted(data)

print data[int(len(data) / 2)]
```
``` output
> 23
```

If you have an even number of sample values then 2 numbers should be returned

Example 2
``` python
data = [1, 2, 1, 6, 3, 0, 5, 5]
data = sorted(data)

middle = int(len(data) / 2)
if len(values) % 2. == 0:
    print data[middle - 1: middle + 1]
else:
    print data[middle]
```
``` output
> [2, 3]
```

Example 3
``` python
import numpy as np

data = [1, 2, 1, 6, 3, 0, 5, 5]

print np.median(data)
```
``` output
> 2.5
```

Example 4
``` python
import pandas as pd

data = pd.DataFrame([1, 2, 1, 6, 3, 0, 5, 5])

print data.median().values
```
``` output
> [ 2.5]
```

### Mode
 - The value that appears most in a data set

Example 1
``` python
data = [1, 0, 3, 0, 5, 3, 1, 0]

mode = max(data, key=data.count)

print mode
```
``` output
> 0
```

If your data set has multiple numbers with the same count, the above example will only return one number.

Example 2
``` python
data = [1, 2, 3, 2, 5, 1, 0]
max_count = max(list(map(data.count, data)))

mode = list(set(filter(lambda n: data.count(n) == max_count, data)))

print mode
```
``` output
> [1, 2]
```
Reference:<br />
http://www.python-course.eu/lambda.php<br />
http://stackoverflow.com/questions/10797819/finding-the-mode-of-a-list-in-python<br />

Example 3
``` python
import pandas as pd
data = pd.DataFrame([1, 2, 3, 2, 5, 1, 0])

print data.mode().values
```
``` output
> [[1]
   [2]]
```

### Standard Deviation
 - A measure of how spread out your data set is.

<img src="https://github.com/gravity226/Understanding_Data_Science/blob/master/imgs/sd_pic.gif" height="200">

(img Reference: https://thekubicle.com/lessons/variance-and-standard-deviation)
