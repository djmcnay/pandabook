---
redirect_from:
  - "/features/fixed-income"
interact_link: content/features/fixed_income.ipynb
kernel_name: python3
has_widgets: false
title: 'Fixed Income'
prev_page:
  url: /features/placeholder
  title: 'Leading Indicators'
next_page:
  url: /features/placeholder
  title: 'Pokemon'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

<div markdown="1" class="cell code_cell">
<div class="input_area hidecode" markdown="1">
```python
# Notebook Setup
from IPython.display import display, HTML

# Lambda function for HTML Object tag to embed another HTML file
gitchartstore = 'https://djmcnay.github.io/pandachartstore/'
htmlobj = lambda l, w=600, h=200: HTML('<object data=\"'+gitchartstore+l
                                           +'\" width=\"'+str(w)
                                           +'\" height=\"'+str(h)
                                           +'\"</object>')
```
</div>

</div>

# Fixed Income

### Pokemon Fair Value Bond Yields
Fair Value of the 10-year nominal bond estimated as a multi-variate regression.

$ FV_{x} = \beta_{x,0} 
+\beta_{x,1}\times \text{Short-Rates} 
+\beta_{x,2} \times \text{Inflation}
+\beta_{x,3} \times \text{Growth}
+\beta_{x,4}\times \text{Global Factor}
+\epsilon_{x}$

<div markdown="1" class="cell code_cell">
<div class="input_area hidecode" markdown="1">
```python
display(htmlobj('PlotlyHTMLexJS/pokemon.html'))
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/pokemon.html" width="600" height="200"</object>
</div>

</div>
</div>
</div>

<div markdown="1" class="cell code_cell">
<div class="input_area hidecode" markdown="1">
```python
l='PlotlyHTMLexJS/pokemon.html'
HTML('<object data=\"'+gitchartstore+l+'\" width=\"'+str(600)+'\" height=\"'+str(200)+'\"</object>')
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">



<div markdown="0" class="output output_html">
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/pokemon.html" width="600" height="200"</object>
</div>


</div>
</div>
</div>
