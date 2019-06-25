---
interact_link: content/features/placeholder.ipynb
kernel_name: python3
has_widgets: false
title: 'Cross-Asset'
prev_page:
  url: https://github.com/djmcnay/pandabook
  title: 'GitHub repository'
next_page:
  url: /features/placeholder
  title: 'Correlations'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
from IPython.display import display, HTML
from urllib.request import urlopen
```
</div>

</div>

# Placeholder Page

But seeing as you are here...

![Cute Red Pandas](https://adorableanimals4lois.files.wordpress.com/2012/07/tumblr_lpfrzsyeie1qgxenqo1_500.jpg?w=620)

... have a happy panda

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
%%html
<div align="left">
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/pokemon.html" width="800" height="500"></object>
</div>
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<div align="left">
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/pokemon.html" width="800" height="500"></object>
</div>
</div>

</div>
</div>
</div>

### Within IPython Trying to Hide Code Cell

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
# HIDE CODE
HTML('''<object data='''"https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/pokemon.html" width="800" height="500"></object>
''')
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">



<div markdown="0" class="output output_html">

<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/pokemon.html" width="800" height="500"></object>

</div>


</div>
</div>
</div>

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
# Lambda function for HTML Object tag to embed another HTML file
htmlobj = lambda l, w=800, h=200: HTML(str('<object data=\"https://djmcnay.github.io/pandachartstore/'+l
                                  +'\" width=\"'+str(w)+'\" height=\"'+str(h)+'\"</object>'))
htmlobj('PlotlyHTMLexJS/pokemon.html')
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">



<div markdown="0" class="output output_html">
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/pokemon.html" width="800" height="200"</object>
</div>


</div>
</div>
</div>

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('Code Should be Hidden')
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
Code Should be Hidden
```
</div>
</div>
</div>

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('Please hide this code')
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
Please hide this code
```
</div>
</div>
</div>

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print('This is really annoying...')
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">
{:.output_stream}
```
This is really annoying...
```
</div>
</div>
</div>
