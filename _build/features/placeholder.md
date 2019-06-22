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

<html>
    <head>
      <script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
      <style>body{margin:0 100}</style>
    </head>
    <body>
        <object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/pokemon.html"></object>
    </body>
</html>
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">

<html>
    <head>
      <script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
      <style>body{margin:0 100}</style>
    </head>
    <body>
        <object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/pokemon.html"></object>
    </body>
</html>
</div>

</div>
</div>
</div>

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
%%html

<html>
    <head>
      <script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
    </head>
    <body>
        <object 
        data="https://djmcnay.github.io/pandachartstore/PlotlyHTML/pokemon.html" 
        width="1000" height="600">
        </object>
    </body>
</html>
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">

<html>
    <head>
      <script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
    </head>
    <body>
        <object 
        data="https://djmcnay.github.io/pandachartstore/PlotlyHTML/pokemon.html" 
        width="1000" height="600">
        </object>
    </body>
</html>
</div>

</div>
</div>
</div>

## TEST of In-Situ Download

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
# POKEMON
from hongxiongmao import pokemon
import plotly.offline as py

p = pokemon.pokemon_go()
p.download_and_run()
p.plotlyplot()
aPlot = py.plot(p.plot, filename='test_delete.html', auto_open=False, include_plotlyjs=False)

def plotly_html_hack(plot):
    html_template = """ 
        <html>
            <head>
              <script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
              <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap.min.css">
              <style>body{margin:0 100}</style>
            </head>
            <body>
            """ + plot + """
            </body>
        </html>"""
    display(HTML(html_template))
    
plotly_html_hack(aPlot)
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
 
        <html>
            <head>
              <script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
              <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap.min.css">
              <style>body{margin:0 100}</style>
            </head>
            <body>
            test_delete.html
            </body>
        </html>
</div>

</div>
</div>
</div>
