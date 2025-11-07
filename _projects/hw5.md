---
name: Two Visualizations of the Same Dataset
tools: [Python, Altair, Vega-Lite]
image: assets/hw5/thumb.png
description: Two interactive visualizations built using Altair for IS445 HW5.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
---
# HW5 — Two Visualizations of the Same Dataset

## Visualization 1: Scatterplot with Brush Interaction
This visualization shows the relationship between X and Y variables in the dataset.
I used **Altair** with quantitative encodings for both axes and a brush selection for
interactive filtering. Color encodes the “Category” variable using a perceptually uniform palette.

<vegachart schema-url="{{ site.baseurl }}/assets/hw5/chart1.json" style="width: 100%"></vegachart>

*Data Transformation:*  
The data were filtered to include records from 2020–2024 and a derived “average_value” field was computed.

---

## Visualization 2: Bar Chart with Dropdown Filter
This chart displays counts of observations by category.  
A dropdown selection parameter allows users to filter categories dynamically.

<vegachart schema-url="{{ site.baseurl }}/assets/hw5/chart2.json" style="width: 100%"></vegachart>

---

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/YunxiangWang-github/YOUR_REPO/main/data/your_data.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/YunxiangWang-github/YOUR_REPO/blob/main/python_notebooks/hw5.ipynb" text="The Analysis" %}
</div>

