# Experiment 19: Real-World and Interactive Visualization

**Author:** Ronit Mehta  
**PRN:** 25070123094  

---

## AIM
To implement real-world, advanced, and interactive data visualization techniques using Python libraries such as Plotly, SciPy, and Matplotlib-Venn to uncover complex relationships, hierarchies, and flows within datasets.

---

## Theory & Command Reference

This experiment shifts from basic static charts to highly interactive and specialized plots that are frequently used in real-world data science and business analytics dashboards.

### 1. Treemaps (Plotly Express)
Treemaps display hierarchical data as a set of nested rectangles, where the size of each rectangle is proportional to its value.
* `import plotly.express as px`: Imports the Plotly Express library for interactive high-level plotting.
* `px.treemap(df, path=['Column1'], values='Column2', title="...")`: Generates the treemap. `path` defines the hierarchy, and `values` defines the size of the blocks.
* `fig.show()`: Renders the interactive HTML-based Plotly figure.

### 2. Dendrograms (SciPy)
Dendrograms are tree-like diagrams that show the arrangement of clusters produced by hierarchical clustering algorithms.
* `from scipy.cluster.hierarchy import dendrogram, linkage`: Imports the necessary clustering algorithms and plotting tools from SciPy.
* `linked = linkage(data, method='ward')`: Performs hierarchical/agglomerative clustering. The 'ward' method minimizes the variance within clusters.
* `dendrogram(linked)`: Plots the hierarchical relationship as a tree diagram using Matplotlib.

### 3. Venn Diagrams (Matplotlib-Venn)
Venn diagrams illustrate the logical relationships and overlaps between different sets of data.
* `from matplotlib_venn import venn2`: Imports the function to draw a 2-set Venn diagram.
* `venn2([SetA, SetB], set_labels=('Label 1', 'Label 2'))`: Computes the intersection and symmetric differences of two Python `set` objects and plots the overlapping circles.

### 4. Sankey Diagrams (Plotly Graph Objects)
Sankey diagrams are flow diagrams in which the width of the arrows is proportional to the flow rate. They are excellent for visualizing energy, material, or cost transfers between processes.
* `import plotly.graph_objects as go`: Imports the lower-level Plotly Graph Objects for custom and complex chart types.
* `go.Sankey(node=dict(label=[...]), link=dict(source=[...], target=[...], value=[...]))`: Configures the Sankey chart. 
  * `node` defines the stages (e.g., Admission, First Year, Placed).
  * `link` connects the nodes via index values (`source` to `target`) and sets the volume of the flow (`value`).
* `fig = go.Figure(data=[...])`: Wraps the Sankey trace into a figure object for rendering.

### 5. 3D Scatter Plots (Plotly Express)
3D scatter plots allow for the visualization of three numerical variables simultaneously on the X, Y, and Z axes.
* `px.scatter_3d(df, x='Col1', y='Col2', z='Col3', title="...")`: Creates an interactive 3D scatter plot where the user can pan, zoom, and rotate the axes to inspect the data points from any angle.

### 6. Radar / Spider Charts (Plotly Graph Objects)
Radar charts compare multiple quantitative variables, making them perfect for displaying performance metrics or skill profiles.
* `go.Scatterpolar(r=values, theta=skills, fill='toself', name='...')`: Creates a radial plot trace. `theta` represents the categories (angles), `r` represents the magnitude, and `fill='toself'` shades the enclosed area.
* `fig.add_trace(...)`: Adds the configured Scatterpolar trace to the empty figure.

---


## Conclusion
In this experiment, we successfully explored advanced and interactive visualization techniques that go beyond standard 2D plots. Using **Plotly Express** and **Graph Objects**, we created interactive Treemaps, 3D Scatter Plots, Sankey Diagrams, and Radar charts, which are crucial for dashboarding and allowing users to explore data dynamically. Additionally, we integrated specialized mathematical visualizations like **Dendrograms** (via SciPy) for clustering analysis and **Venn Diagrams** to evaluate set overlaps. These tools are indispensable in real-world data science for presenting multi-dimensional, hierarchical, and flow-based data in an intuitive manner.
