# Learning Matplotlib 📊

A comprehensive collection of matplotlib examples and techniques for data visualization in Python.

## 📚 Table of Contents

- Bar Plots
- Histogram Plots
- Line Plots
- Pie Charts
- Scatter Plots

## 📊 Bar Plots

### Basic Bar Plot Setup
```python
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd

plt.style.use('dark_background')

subjects = ['Maths', 'English', 'Science', 'Social Studies', 'Computer']
marks = [89, 90, 45, 78, 99]
```

### Simple Bar Charts
```python
# Basic bar plot
plt.bar(subjects, marks)
plt.show()

# Single color bar plot
plt.bar(subjects, marks, color='green')
plt.show()

# Multi-color bar plot
colors = ['red', 'blue', 'green', 'orange', 'purple']
plt.bar(subjects, marks, color=colors)
plt.show()
```

### Customizing Bar Plots
```python
# Adjust bar width
plt.bar(subjects, marks, color=colors, width=0.6)
plt.show()

# Add edge colors
plt.bar(subjects, marks, color=colors, edgecolor='white')
plt.show()

# Customize edge properties
plt.bar(subjects, marks, color=colors, edgecolor='white', linewidth=4)
plt.show()

# Add line styles
plt.bar(subjects, marks, color=colors, edgecolor='white', linewidth=4, linestyle='--')
plt.show()

# Horizontal bar plot
plt.barh(subjects, marks, color=colors)
plt.show()
```

### Multiple Bar Series
```python
subjects = ['Maths', 'English', 'Science', 'Social Studies', 'Computer']
marks1 = [89, 90, 45, 78, 99]
marks2 = [78, 56, 34, 90, 12]

# Overlapping bars
plt.figure(figsize=(8,8))
plt.bar(subjects, marks1)
plt.bar(subjects, marks2)
plt.xlabel('Subjects')
plt.ylabel('Marks')
plt.show()

# Side-by-side bars
subjects_len = np.arange(len(subjects))
width = 0.4

plt.figure(figsize=(8,8))
plt.bar(subjects_len, marks1, width=width)
plt.bar(subjects_len + width, marks2, width=width)
plt.xlabel('Subjects')
plt.ylabel('Marks')
plt.show()

# With transparency
plt.figure(figsize=(8,8))
plt.bar(subjects_len, marks1, width=width, color=colors)
plt.bar(subjects_len + width, marks2, width=width, color=colors, alpha=0.5)
plt.xlabel('Subjects')
plt.ylabel('Marks')
plt.show()
```

### Real Data Example
```python
# Using supermarket data
df = pd.read_csv('SUPERMARKET.csv')
payment_df = pd.DataFrame(df['Payment'].value_counts())

colors = ['red', 'blue', 'green']
plt.bar(payment_df.index, payment_df['count'], color=colors)
plt.show()
```

## 📈 Histogram Plots

### Basic Histogram
```python
plt.style.use('dark_background')

# Generate sample data
marks_50_students = np.random.randint(0, 100, (50))

# Simple histogram
plt.hist(marks_50_students)
plt.show()
```

### Customizing Histograms
```python
# Custom bins
bins = np.arange(0, 100, 5)
plt.figure(figsize=(6,6))
plt.hist(marks_50_students, bins=bins)
plt.xticks(np.arange(0, 100, 5))
plt.show()

# Color customization
plt.figure(figsize=(6,6))
plt.hist(marks_50_students, bins=bins, color='orange')
plt.xticks(np.arange(0, 100, 5))
plt.show()

# Horizontal orientation
plt.figure(figsize=(6,6))
plt.hist(marks_50_students, bins=bins, color='orange', orientation='horizontal')
plt.yticks(np.arange(0, 100, 5))
plt.show()

# Adjust bar width
plt.figure(figsize=(6,6))
plt.hist(marks_50_students, bins=bins, color='orange', rwidth=0.6)
plt.xticks(np.arange(0, 100, 5))
plt.show()

# Step histogram
plt.figure(figsize=(6,6))
plt.hist(marks_50_students, bins=bins, color='orange', histtype='step')
plt.xticks(np.arange(0, 100, 5))
plt.show()
```

### Multiple Histograms
```python
marks_50_students1 = np.random.randint(0, 100, (50))
marks_50_students2 = np.random.randint(0, 100, (50))

bins = np.arange(0, 100, 5)
plt.figure(figsize=(6,6))
plt.hist([marks_50_students1, marks_50_students2], bins=bins, color=['orange', 'blue'])
plt.xticks(np.arange(0, 100, 5))
plt.xlabel('Marks')
plt.ylabel('Frequency')
plt.title('Marks of Students of 2 Classes')
plt.show()
```

## 📉 Line Plots

### Basic Line Plot
```python
rollno = [1,2,3,4,5,6,7,8,9,10]
marks = [10, 20, 30, 40, 50, 60, 70, 80, 90, 100]

# Simple line plot
plt.plot(rollno, marks, 'r-')
plt.show()
```

### Line Style Customization
```python
# Different line styles
plt.plot(rollno, marks, linestyle='-')  # Solid line
plt.plot(rollno, marks, linestyle='--', color='#728569')  # Dashed line
plt.plot(rollno, marks, linestyle=':', color='orange')  # Dotted line
plt.plot(rollno, marks, linestyle=':', linewidth=15)  # Thick dotted line
```

### Enhanced Line Plots
```python
study_hours = [2,3,4,4, 5, 6, 7, 7, 8, 9, 9, 10, 11, 11, 12]
marks = [6, 10, 15, 20, 34, 44, 55, 60, 55, 67, 70, 80, 90, 99, 100]

# Detailed line plot with custom axes
plt.figure(figsize=(8,8))
plt.xticks(np.arange(0, 15, 1))
plt.yticks(np.arange(0, 100, 5))
plt.plot(study_hours, marks, 'r-')
plt.xlabel('Study Hours')
plt.ylabel('Marks')
plt.show()

# Line plot with markers
plt.figure(figsize=(8,8))
plt.xticks(np.arange(0, 15, 1))
plt.yticks(np.arange(0, 100, 5))
plt.plot(study_hours, marks, 'r-')
plt.plot(study_hours, marks, 'bo')
plt.xlabel('Study Hours')
plt.ylabel('Marks')
plt.show()
```

## 🥧 Pie Charts

### Basic Pie Chart
```python
classes = ['Physics', 'Chemistry', 'Maths', 'Science', 'SST']
marks = [89, 45, 78, 23, 90]

# Simple pie chart
plt.pie(marks, labels=classes)
plt.show()
```

### Pie Chart Customization
```python
colors = ['red', 'blue', 'green', '#9803fc', '#03c2fc']

# Colored pie chart
plt.pie(marks, labels=classes, colors=colors)
plt.show()

# With percentages
plt.pie(marks, labels=classes, colors=colors, autopct='%0.1f%%')
plt.show()

# Exploded slice
explode_values = [0.1, 0, 0, 0, 0]
plt.pie(marks, labels=classes, colors=colors, autopct='%0.1f%%', explode=explode_values)
plt.show()

# With shadow
plt.pie(marks, labels=classes, colors=colors, autopct='%0.1f%%', explode=explode_values, shadow=True)
plt.show()

# Custom radius
plt.pie(marks, labels=classes, colors=colors, autopct='%0.1f%%', explode=explode_values, radius=1.6)
plt.show()
```

### Advanced Pie Chart Styling
```python
# Custom text properties
textprops = {'fontsize':14, 'color':'k'}
plt.pie(marks, labels=classes, colors=colors, autopct='%0.1f%%', explode=explode_values, radius=1.6, textprops=textprops)
plt.show()

# Custom wedge properties
wedgeprops = {'linewidth':3, 'linestyle':'--', 'edgecolor':'white'}
plt.pie(marks, labels=classes, colors=colors, autopct='%0.1f%%', explode=explode_values, radius=1.6, textprops=textprops, wedgeprops=wedgeprops)
plt.show()

# Complete pie chart with title and legend
plt.figure(figsize=(6,6))
plt.pie(marks, labels=classes, colors=colors, autopct='%0.1f%%', explode=explode_values, textprops=textprops)
plt.title('Subjects and Average Scores')
plt.legend()
plt.show()
```

### Real Data Pie Chart
```python
# Using supermarket data
df = pd.read_csv('SUPERMARKET.csv')
payment_df = pd.DataFrame(df['Payment'].value_counts())

plt.pie(payment_df['count'], labels=payment_df.index, colors=['red', 'blue', 'green'], autopct='%0.2f%%')
plt.show()
```

## 🔸 Scatter Plots

### Basic Scatter Plot
```python
rollno = [1,2,3,4,5,6,7,8,9,10]
marks = [10, 20, 30, 40, 50, 60, 70, 80, 90, 100]

# Simple scatter plot
plt.scatter(rollno, marks)
plt.show()

# Colored scatter plot
plt.scatter(rollno, marks, color='green')
plt.show()

# Custom markers
plt.scatter(rollno, marks, color='green', marker='*')
plt.show()

# Large figure
plt.figure(figsize=(12,8))
plt.scatter(rollno, marks, color='blue', marker='*')
plt.show()

# Large markers
plt.figure(figsize=(8,8))
plt.plot(rollno, marks, 'bo', markersize=20)
plt.show()
```

### Multiple Dataset Scatter Plots
```python
temperature_pune = [25,34,21,45,28,6,43,18,7,2]
humidity_pune = [28, 25,29,20, 26, 50, 19, 29, 52, 55]
temperature_bangalore = [34,35,36,37,28,27,26,25,31,20]
humidity_bangalore = [40, 38, 36, 35, 42, 44, 41, 40, 34, 45]

# Single city scatter plot
plt.figure(figsize=(8,8))
plt.plot(temperature_pune, humidity_pune, 'ro', markersize=15)
plt.show()

# With custom axes
plt.figure(figsize=(8,8))
plt.xticks(np.arange(0, 60, 5))
plt.yticks(np.arange(10, 60, 5))
plt.plot(temperature_pune, humidity_pune, 'ro', markersize=15)
plt.xlabel('Temperature')
plt.ylabel('Humidity')
plt.show()

# Multiple cities comparison
plt.figure(figsize=(8,8))
plt.xticks(np.arange(0, 60, 5))
plt.yticks(np.arange(10, 60, 5))
plt.plot(temperature_pune, humidity_pune, 'ro', markersize=15)
plt.plot(temperature_bangalore, humidity_bangalore, 'bo', markersize=15)
plt.xlabel('Temperature')
plt.ylabel('Humidity')
plt.show()
```

### Real Dataset Scatter Plots
```python
# Using Iris dataset
df = pd.read_csv('IRIS.csv')

# Basic scatter plot
plt.scatter(df['sepal_length'], df['petal_length'])
plt.show()

# Alternative syntax
plt.plot(df['sepal_width'], df['petal_width'], 'go')
plt.show()

# Enhanced scatter plot
plt.figure(figsize=(8,8))
plt.xticks(np.arange(1, 10, 0.5))
plt.yticks(np.arange(1, 10, 0.5))
plt.plot(df['sepal_length'], df['petal_length'], 'ro', alpha=0.5, markersize=8)
plt.xlabel('Sepal Length')
plt.ylabel('Petal Length')
plt.show()
```

## 📋 Sample Datasets Used

This repository includes examples with the following datasets:
- **Student Marks Data**: Subject-wise performance data
- **Supermarket Data**: Transaction and payment method data
- **Iris Dataset**: Flower measurements for species classification
- **Weather Data**: Temperature and humidity measurements

## 🛠️ Required Libraries

```python
pip install matplotlib numpy pandas
```

## 💡 Key Learning Points

1. **Bar Plots**: Categorical data visualization with customization options
2. **Histograms**: Distribution analysis with binning and styling
3. **Line Plots**: Trend analysis with various line styles and markers
4. **Pie Charts**: Proportional data representation with advanced styling
5. **Scatter Plots**: Relationship analysis between variables
6. **Styling**: Dark background themes and color customization
7. **Figure Management**: Size control and axis customization
8. **Real Data Integration**: Working with CSV files and pandas DataFrames

## 🎯 Plot Types Summary

| Plot Type | Best For | Key Parameters |
|-----------|----------|----------------|
| Bar Plot | Categorical comparisons | `color`, `width`, `edgecolor` |
| Histogram | Data distributions | `bins`, `rwidth`, `histtype` |
| Line Plot | Trends over time | `linestyle`, `linewidth`, `marker` |
| Pie Chart | Proportional data | `autopct`, `explode`, `colors` |
| Scatter Plot | Variable relationships | `marker`, `markersize`, `alpha` |

## 🎨 Styling Options

- **Colors**: Named colors, hex codes, RGB tuples
- **Markers**: `'o'`, `'*'`, `'s'`, `'^'`, `'+'`, etc.
- **Line Styles**: `'-'`, `'--'`, `':'`, `'-.'`
- **Transparency**: `alpha` parameter (0-1)
- **Size Control**: `figsize`, `markersize`, `linewidth`

---

*Happy plotting with matplotlib! 📊🎨*
