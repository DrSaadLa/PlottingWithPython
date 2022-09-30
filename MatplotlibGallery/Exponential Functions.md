```python
#=====================================================#
#            Title: Matplotlib Gallery                #
#            subtitle: Exponential Functions          #
#                                                     #
#            By: Dr Saad Laouadi                      #
#           Copyright: Dr. Saad Laouad                # 
#=====================================================#
```


```python
# Environment setup
# ------------------
import matplotlib
matplotlib.use("agg")
import matplotlib.pyplot as plt
import numpy as np

%matplotlib inline
```


```python
# setting the figure and axes
# ---------------------------
fig, ax = plt.subplots(figsize = (6, 4),
                       linewidth=6, 
                       frameon=True, 
                       edgecolor='gray', 
                       tight_layout=False)

# Hide the top and right spines
# -----------------------------
ax.spines[["top", "right"]].set_visible(False)

# move bottom and left spine to x = 0 and y = 0
# ---------------------------------------------
ax.spines['bottom'].set_position(('data', 0))
ax.spines['left'].set_position(('data', 0))

# Create the data
# ===============
x1 = np.linspace(-3, 5, 100)
x2 = np.linspace(-1.9, 5, 100)
x3 = np.linspace(-5, 0.9, 100)
x4 = np.linspace(-5, 3, 100)
x5 = np.linspace(-5, 2.08, 100)
x6 = np.linspace(-5, 5, 100)

# Plot the data
# =============
ax.plot(x1, 0.5**x1, label = r'${0.5}^x$')
ax.plot(x2, 0.333**x2, label = r'${0.33}^x$')
ax.plot(x3, 10**x3, label = r'${10}^x$')
ax.plot(x4, 2**x4, label = r'${2}^x$')
ax.plot(x5, np.exp(x5), label = r'${exp}^x$')
ax.plot(x6, 1.5**x6, label = r'${1.5}^x$')
ax.plot(x6, 1.2**x6, label = r'${1.2}^x$')


# Set the x and y ticks labels
# ----------------------------
ax.set_xticks([label for label in ax.get_xticks() if label!=0.0])
ax.set_yticks([label for label in ax.get_yticks() if label!=0.0 and label!=1.0])

# Setting the plot grid
# ----------------------
ax.grid(axis="x", color="green", alpha=.3, linewidth=1.1, linestyle=":")
ax.grid(axis="y", color="black", alpha=.5, linewidth=.5)


# Setting the Axes Limits
# -----------------------
ax.set_xlim(-5.6, 5.6)
ax.set_ylim(-0.99, 8.6)
ax.set_axisbelow(False)

# Polishing the plot
# ------------------
ax.set_title("Exponential Functions", fontsize=16,
             fontweight="heavy", 
             color="blue")

# Setting the ticks and ticks labels
# ----------------------------------
ax.tick_params(labelsize=12, labelcolor="blue",
               color="blue", width=2, pad=6)
for label in ax.get_xticklabels(which="both") + ax.get_yticklabels(which="both"):
    label.set_fontweight("heavy")
    label.set_bbox({"facecolor":"white", 
                   "edgecolor":"white",
                   "boxstyle":"circle"})
    
ax.legend()
plt.show()

# Saving the figure
# plt.savefig("exp_funcs.png", dpi=600)
```


    
![png](output_2_0.png)
    



```python

```
