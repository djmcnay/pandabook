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

## Principal Drivers Index
The PDI takes 10 US listed ETFs and generates a timeseries of the variance explained by the principal eigenvector; correlations from 26wk rolling returns.

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

## Duo-Dendrogram
We present two dendrograms which both use the same universe of US listed ETFs, but over different time horizons. Construction uses the [SciPy](https://docs.scipy.org/doc/scipy/reference/generated/scipy.cluster.hierarchy.dendrogram.html) and defaults to Euclidean distance, although we can run other clustering methods. We get a sense of how well clustering performs using the Cophenetic Correlation Coefficient,  c . This correlates actual pairwise distances of all samples to those implied by the hierarchical clustering. The closer  c  is to 1, the better the clustering preserves the original distances. Generally  c  > 0.7 is consistered a good cluster fit.

A useful [blog](https://silburt.github.io/blog/stock_correlation.html)

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
