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
from bs4 import BeautifulSoup
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
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/pokemon.html" width="800" height="500"></object>
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

### Within IPython which should in theory make the cell hideable

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
HTML('''
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/pokemon.html" width="800" height="500"></object>
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
HTML('''<script>
code_show=true; 
function code_toggle() {
 if (code_show){
 $('div.input').hide();
 } else {
 $('div.input').show();
 }
 code_show = !code_show
} 
$( document ).ready(code_toggle);
</script>
<form action="javascript:code_toggle()"><input type="submit" value="Click here to toggle on/off the raw code."></form>''')
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">



<div markdown="0" class="output output_html">
<script>
code_show=true; 
function code_toggle() {
 if (code_show){
 $('div.input').hide();
 } else {
 $('div.input').show();
 }
 code_show = !code_show
} 
$( document ).ready(code_toggle);
</script>
<form action="javascript:code_toggle()"><input type="submit" value="Click here to toggle on/off the raw code."></form>
</div>


</div>
</div>
</div>
