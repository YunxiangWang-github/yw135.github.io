---
name: Two Visualizations of the Same Dataset
tools: [Python, Altair, Vega-Lite]
image: assets/hw5/thumb.png
description: Two interactive visualizations built using Altair.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Two Visualizations of the Same Dataset

## Visualization 1 — Building Counts by County and Agency
This stacked bar chart visualizes the number of state-owned buildings by `county`, with color representing `agency`.  
Two types of interactivity are implemented:

1. A *legend-bound selection* (`bind='legend'`) lets viewers click on an agency name to highlight its buildings across counties while dimming others.  
2. A *dropdown menu* labeled “View” allows switching between three scopes:  
   - *Top 10* counties (those with the most buildings),  
   - *All* counties, and  
   - *Other* counties (excluding the top 10).  

**Encodings —** `county` → *x (nominal)*, `count()` → *y (quantitative)*, and `agency` → *color (nominal)*. Opacity is conditioned on the legend selection to emphasize the chosen agency.  

**Color Map —** A *categorical palette* is used so distinct agencies remain visually separable. A sequential palette is intentionally avoided since `agency` is a nominal variable rather than continuous.  

**Transformations —** Altair performs a `count()` aggregation grouped by `county` and `agency`. Counties are sorted by total count, and a derived *category field* (“Top10”, “Other”) defines the dropdown filter scope.  

**Interactivity —** The combination of *categorical filtering* (dropdown) and *highlight-based comparison* (legend selection) enables multi-level exploration of how state agencies are distributed across Illinois counties—well beyond simple pan/zoom.

<vegachart schema-url="{{ site.baseurl }}/assets/hw5/chart1.json" style="width: 100%"></vegachart>

---

## Visualization 2 — Average Building Size by Agency (Filtered by County)
This bar chart compares the average of `Square Footage` for each `agency`, filtered by `county`.  
A *dropdown selector* lists all counties in alphabetical order, allowing viewers to quickly focus on a specific region and see how building sizes differ across agencies.  
Bars are sorted in descending order of average building size to emphasize ranking and facilitate comparison.

**Encodings —** `agency` → *x (nominal, sorted by descending mean)*, `mean(Square Footage)` → *y (quantitative)*, and `agency` → *color* (consistent palette across both charts).  

**Color Map —** The same *categorical color scheme* is applied for consistency between both visualizations, reinforcing agency identity.  

**Transformations —** The selected county acts as a *filter*, and Altair computes the mean of `Square Footage` per agency before re-sorting the bars.  

**Interactivity —** The dropdown provides county-level filtering for focused analysis, supporting region-specific exploration and comparison across agencies.

<vegachart schema-url="{{ site.baseurl }}/assets/hw5/chart2.json" style="width: 100%"></vegachart>

---

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/YunxiangWang-github/YunxiangWang-github.github.io/blob/main/python_notebooks/hw5.ipynb" text="The Analysis" %}
</div>
