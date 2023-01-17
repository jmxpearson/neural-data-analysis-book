---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---
# A little point process theory

```{code-cell}
:tags: [remove-cell]
import numpy as np
import matplotlib.pyplot as plt
import scipy.stats as stats
from myst_nb import glue
%config InlineBackend.figure_formats = ['svg']
plt.rcParams.update({
    "text.usetex": True,
    "font.family": "Helvetica"
})
np.random.seed(12345)
```

At its most basic, a point process is a statistical distribution whose samples are _collections of points_. This is somewhat more abstract than distribution that
produces real numbers (like the normal distribution) or integers (like the binomial distribution). In most examples we care about, the points are the times of events
like action potentials or lever presses, though they could also be collections of points in two or more dimensions (locations of cell bodies or foraging sites). 

In this chapter, we will concentrate exclusively on a single kind of very special point process: the Poisson process. This is partly because the Poisson process
is in some senses the _simplest_ type of point process, but it is also a very good approximation to many phenomena we care about. To define the point process, we 
will assume we know a single positive parameter $\lambda > 0$ called the _intensity_ or _rate_ of the process. We will also assume (for the moment) that this 
parameter is a constant, and we will work in one dimension, so that events can be ordered along a line.

Now, here's the definition: Take an interval of time of length $T$. 

```{code-cell}
:tags: [remove-input]
plt.figure(figsize=(6, 2))
plt.scatter(np.random.rand(50), np.random.rand(50));
plt.xlabel(r"$\mathrm{time}$")
ax = plt.gca()
ax.spines[['right', 'top', 'left']].set_visible(False)
```