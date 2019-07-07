---
redirect_from:
  - "/features/leading-indicators"
interact_link: content/features/leading_indicators.ipynb
kernel_name: python3
has_widgets: false
title: 'Leading Indicators'
prev_page:
  url: /features/placeholder
  title: 'Macro'
next_page:
  url: /features/fixed_income
  title: 'Fixed Income'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

# Leading Indicators

## OECD Normalised CLI
The OECD Composite Leading Indicators are published monthly, with a 2-month lag, as part of the [Monthly Economic Indicators](https://stats.oecd.org/index.aspx?queryid=6617). According to the OECD:

> The [composite leading indicator (CLI)](https://data.oecd.org/leadind/composite-leading-indicator-cli.htm) is designed to provide early signals of turning points in business cycles showing fluctuation of the economic activity around its long term potential level. CLIs show short-term economic movements in qualitative rather than quantitative terms.

Practically they are calibrated to lead the *"reference series"* by approximately 4-8 months

<div markdown="1" class="cell code_cell">
<div class="input_area hidecode" markdown="1">
```python
%%html
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/cli_dm.html" 
        width="645" height="450"></object>

<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/cli_em.html" 
        width="645" height="450"></object>
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/cli_dm.html" 
        width="645" height="450"></object>

<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/cli_em.html" 
        width="645" height="450"></object>
</div>

</div>
</div>
</div>

## CLI Swirlygram
Here we present the absolute level of the CLI series (adjusted around zero) and the 3-month change in the CLI level to get an indication of the direction the OECD CLI is trending and to make it easier to spot turning points. Credit to [CBS](https://www.cbs.nl/en-gb) from whom I originally got the idea, although I can no longer find the specific paper.

<div markdown="1" class="cell code_cell">
<div class="input_area hidecode" markdown="1">
```python
%%html
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/cli_dm_swirlygram.html" 
        width="645" height="500"></object>
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/cli_em_swirlygram.html"
        width="645" height="500"></object>
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/cli_dm_swirlygram.html" 
        width="645" height="500"></object>
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/cli_em_swirlygram.html"
        width="645" height="500"></object>
</div>

</div>
</div>
</div>

## Animated Swirlygram
From the OECD website: 
>The OECD CLI system is based on the "growth cycle" approach, where business cycles and turning points are measured and identified in the deviation-from-trend series. The Gross Domestic Product (GDP) is used as the reference for identification of turning points in the growth cycle for all countries, except for China for which the OECD relies on the value added of industry at 1995 prices.

We want to be able view the effectiveness of the OECD CLI at tracking it's ["reference"](https://www.oecd.org/sdd/leading-indicators/oecdcompositeleadingindicatorsreferenceturningpointsandcomponentseries.htm) series. Our animated swirlygram below shows the OECD CLI vs. the OECD Normalised GDP series (with a 6-month lead). **NB/** this is *"self contained"* example which seriously limits interactivity, however the same code can be used for a more dynamic version (including different reference series, lead times etc...)

<div markdown="1" class="cell code_cell">
<div class="input_area hidecode" markdown="1">
```python
%%html
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/cli_animated_swirlygram.html"
        width="645" height="500"></object>
```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

<div markdown="0" class="output output_html">
<object data="https://djmcnay.github.io/pandachartstore/PlotlyHTMLexJS/cli_animated_swirlygram.html"
        width="645" height="500"></object>
</div>

</div>
</div>
</div>
