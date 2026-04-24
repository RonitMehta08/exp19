# Experiment 17: Basic Charts and Visual Encoding

**Author:** Ronit Mehta  
**PRN:** 25070123094  

---


## AIM
To implement basic charts and explore visual encoding techniques (such as color, size, and markers) using Python’s **Matplotlib** and **Seaborn** libraries for effective data visualization.

---

## Theory & Command Reference

Data visualization is the graphical representation of information. It uses visual elements like charts, graphs, and maps to provide an accessible way to see and understand trends, outliers, and patterns in data.

### 1. Library Initialization & Data Setup
* `import matplotlib.pyplot as plt`: Imports the core Matplotlib plotting framework.
* `import seaborn as sns`: Imports Seaborn, which provides a high-level interface for drawing attractive statistical graphics.
* `import pandas as pd`: Used to create and manage the DataFrames containing the sample data.
* `plt.figure(figsize=(width, height))`: Initializes a new figure with specified dimensions before plotting.

### 2. Line Charts (Trend Analysis)
Line charts are ideal for visualizing data that changes continuously over time or across sequential categories.
* **Matplotlib:** `plt.plot(x, y, marker='o', color='green', label='...')` plots a line graph. The `marker` argument adds specific shapes at data points (e.g., 'o' for circles, 's' for squares).
* **Seaborn:** `sns.lineplot(x='Column1', y='Column2', data=df)` creates a line plot directly from a DataFrame, automatically handling aggregations if multiple values exist for a single x-point.

### 3. Bar Charts (Categorical Comparison)
Bar charts are used to compare numerical values across different discrete categories.
* **Simple Bar:** `plt.bar(x, height, color='cyan', edgecolor='black')` creates a vertical bar chart.
* **Grouped Bar Chart:** Uses `np.arange(len(df))` to create a numeric x-axis. By shifting the bars left (`x - width/2`) and right (`x + width/2`), multiple categories can be compared side-by-side.
* **Data Labels:** Utilizing a `for` loop over `bars = plt.bar(...)` and calling `plt.text(x, y, label, ha='center', va='bottom')` adds exact value annotations on top of each bar.

### 4. Histograms (Frequency Distribution)
Histograms group continuous data into ranges (bins) to show the underlying frequency distribution.
* **Matplotlib:** `plt.hist(data, bins=n, color='...', edgecolor='...')` divides the data into `n` bins and plots the frequency.
* **Adding a Mean Line:** `plt.axvline(mean_value, color='red', linestyle='dashed')` draws a vertical line across the axes, highly useful for indicating the average value over a histogram.
* **Seaborn:** `sns.histplot(data['Column'], bins=n)` offers a streamlined way to plot histograms directly from DataFrames.

### 5. Scatter & Bubble Plots (Relationships)
Scatter plots show the relationship or correlation between two numerical variables. Visual encoding (color/size) adds further dimensions to the plot.
* **Basic Scatter:** `plt.scatter(x, y)` plots individual points.
* **Conditional Coloring:** Using list comprehensions like `['red' if r=='Fail' else 'green' for r in df['Result']]` allows you to pass a list of colors to the `c=colours` argument, encoding categorical data visually.
* **Seaborn Bubble Plot:** `sns.scatterplot(x='...', y='...', size='Var1', hue='Var1', sizes=(min, max), data=df, palette='viridis')`. This is a powerful command that plots a scatter graph but scales the size of the dots based on a variable (`size`), colors them based on a variable (`hue`), and applies a specific color map (`palette`).

---


## Conclusion
In this experiment, we successfully navigated the fundamentals of data visualization using Matplotlib and Seaborn. We started with **Line Charts** to observe trends across days, moved to **Bar Charts** (both simple and grouped) for categorical comparisons, and utilized **Histograms** to understand data distribution while highlighting the mean. Finally, we explored relationships using **Scatter Plots**, learning how to apply visual encoding by dynamically changing marker colors based on conditions, and utilizing Seaborn to create multi-dimensional **Bubble Plots**. These visualizations are critical tools for extracting and communicating actionable insights from raw data.
