1)lag_plot is formed using this code .

import matplotlib.pyplot as plt import numpy as np

from custom_prng import MyPRNG # Removed import
Generate 10,000 random numbers
gen = MyPRNG(seed=2025) nums = [gen.next() for _ in range(10000)]

Plot histogram
plt.hist(nums, bins=50, density=True, alpha=0.7, color='royalblue') plt.title("PRNG Uniformity Check") plt.xlabel("Value") plt.ylabel("Density") plt.grid(True) plt.savefig("uniformity.png") plt.show()

2)Uniformity.

from pandas.plotting import lag_plot import pandas as pd

import numpy as np # Removed unused import
Lag plot to see dependency between successive numbers
plt.figure(figsize=(6,6)) lag_plot(pd.Series(nums), lag=1) plt.title("PRNG Lag Plot (Dependency Check)") plt.grid(True) plt.savefig("lag_plot.png") plt.show()
