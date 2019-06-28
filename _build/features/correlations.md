---
interact_link: content/features/correlations.ipynb
kernel_name: python3
has_widgets: false
title: 'Correlations'
prev_page:
  url: /features/placeholder
  title: 'Cross-Asset'
next_page:
  url: /features/placeholder
  title: 'Macro'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

# Correlations

NB/ Observations are coming from the AlphaVantage close price, where the adjusted close maybe more appropropriate for a total return. Shouldn't make a meaningful difference here as correlations won't be materially impacted over 1week.

## Principal Drivers Index
The Principal Drivers Index takes 10 US listed ETFs and shows a timeseries of the percentage variance explained by the principal eigenvector - intuitively the percentage of returns that can be explained by the most important factor. PCA correlation matrix uses 26-weeks of price data, sourced from AlphaVantage.

<div markdown="1" class="cell code_cell">
<div class="input_area hidecode" markdown="1">
```python
%%html
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/principaldrivers.html" 
        width="645"
        height="525">
</object>
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/principaldrivers.html" 
        width="645"
        height="525">
</object>
</div>

</div>
</div>
</div>

For a more detailed explanation of PCA and Principal Drivers Index I’ve written a blog article for Medium.

Several selection choices will have material impacts the PDI, such as:
* Asset Mix - we use a sample of US ETFs and futures available on AlphaVanatage
* Lookback window for returns - default is 13 weeks
* Minimum Asset Count requirement - in order to extend the PDI timeseries we don't require the full asset mix going back historically; we set the threshold at having data for a min. of 50% of current universe 

Sebastian Raschka has written two very useful blog pieces [here](https://plot.ly/ipython-notebooks/principal-component-analysis/) and [here](http://sebastianraschka.com/Articles/2014_pca_step_by_step.html) which cover PCA with Python

## Duo-Dendrogram
We present a double dendrogram, where each dendrogram uses the same US listed ETF universe but different time-horizons to construct the input correlation matrix; by default we use 260 & 13 weeks.

<div markdown="1" class="cell code_cell">
<div class="input_area hidecode" markdown="1">
```python
%%html
<object data="https://djmcnay.github.io/pandachartstore/matplotlib/duodenrogram_etfs.png" 
        width="650"
        height="300">
</object>
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<object data="https://djmcnay.github.io/pandachartstore/matplotlib/duodenrogram_etfs.png" 
        width="650"
        height="300">
</object>
</div>

</div>
</div>
</div>

A dendrogram is a tree diagram to help with hierarchical organisation. We cluster correlations using the agglomerate hierarchical clustering technique, which avoids having to estimate in advance the number of clusters. Agglomerate Clustering first assigns each data point into its own cluster, and gradually merges clusters until only one remains. 

The chart is constructed using matplotlib using the [linkage method from SciPy cluster hierarchy](https://docs.scipy.org/doc/scipy/reference/generated/scipy.cluster.hierarchy.dendrogram.html) and the default setting of Euclidean distance; however the underlying code can be updated to use other methods like Ward or single.

We can get a sense of how well clustering performs using the Cophenetic Correlation Coefficient,  c . This correlates actual pairwise distances of all samples to those implied by the hierarchical clustering. The closer  c  is to 1, the better the clustering preserves the original distances. Generally  c  > 0.7 is consistered a good cluster fit.

A useful [blog](https://silburt.github.io/blog/stock_correlation.html)
