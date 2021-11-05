# RLS : recursive_least_square algorithm 

```Python
import numpy as np
from numpy.linalg import inv


def RLS(P, x, next_a, next_b):
    next_P = P - (P@next_a@next_a.T@P)/(1+next_a.T@P@next_a)
    next_x = x + next_P@next_a*(next_b-next_a.T@x)
    return next_P, next_x
```
