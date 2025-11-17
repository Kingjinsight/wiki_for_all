# Seaborn

A high level abstract of matplotlib, with built-in data type **Series** and **DataFrame**

## Parameter

- **data**: Tidy dataframe where each column is a variable and each row is an observation
- **hue**: Variable in data to map plot aspects to different colors
- **row, col**: Categorical variale that will determine the faceting of the grid
- **kind**: The kind of plot to draw
- **col_wrap**: how many subplot shows in one row
- **height**: height of each subplot
- **aspect**: Aspect ratio of each facet
- **errorbar**: a line that represents the variability or uncertainty around a point estimate on a graph, like a mean or median
- **legend**: "auto","brief", "full" or False
- **legend_out**: bool, if true, the figure size will be extended, and legend will be drawn outside the plot.
- **palette**: colors to use for the different levels of the `hue` variable

## Plots

- `sns.catplot()`: a quick way to generate multi-plot figure
- `sns.pairplot(data)`: used to find correlation between each variable.
- `sns.lineplot`

## Functions:

- `g.set_xticklabels(labels=[a,b,c], rotation=n)`: rotate x_tick in seaborn, set labels. 
