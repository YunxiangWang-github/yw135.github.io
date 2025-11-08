---
name: Two Visualizations of the Same Dataset
tools: [Python, Altair, Vega-Lite]
image: assets/hw5/thumb.png
description: Two interactive visualizations built using Altair.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
---

# Two Visualizations of the Same Dataset

## Visualization 1 — Building Counts by County and Agency
This stacked bar chart visualizes the number of state-owned buildings by **county**, with color representing **agency**.  
Two types of interactivity are implemented:

1. A **legend-bound selection** (`bind='legend'`) lets viewers **click on an agency name** to highlight its buildings across counties while dimming others.  
2. A **dropdown menu** labeled *“View”* allows switching between three scopes:  
   - **Top 10** counties (those with the most buildings),  
   - **All** counties, and  
   - **Other** counties (excluding the top 10).  

This design combines both *categorical filtering* and *highlight-based comparison*, enabling exploration at multiple levels of granularity.  
Counties are sorted by total building count for readability, and the stacked color encoding reveals how agencies are distributed across different regions.  
Together, these interactions go well beyond simple pan/zoom by supporting both selective focus and comparative analysis.

<vegachart schema-url="{{ site.baseurl }}/assets/hw5/chart1.json" style="width: 100%"></vegachart>

---

## Visualization 2 — Average Building Size by Agency (Filtered by County)
This bar chart compares the **average square footage** of buildings for each agency, filtered by **county**.  
A **dropdown selector** lists all counties in **alphabetical order**, allowing viewers to quickly choose a specific region and observe how building sizes differ across agencies.  
Bars are sorted by descending average square footage to emphasize ranking and facilitate comparison.  
This interaction enables a focused exploration of agency-level building data within each county, clearly going beyond static visualization or simple pan/zoom.

<vegachart schema-url="{{ site.baseurl }}/assets/hw5/chart2.json" style="width: 100%"></vegachart>

---

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html 
   link="https://github.com/YunxiangWang-github/YunxiangWang-github.github.io/blob/main/python_notebooks/hw5.ipynb" 
   text="The Analysis" %}
</div>
