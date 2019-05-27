# Pontificating Panda Chartbook

<img src="https://circleci.com/gh/jupyter/jupyter-book.svg?style=svg" class="left">

## About Me

https://www.linkedin.com/in/david-mcnay-9b582136/?originalSubdomain=uk



## Existential Crisis

In 2018 I took the decision to abandon Matlab as a coding language and learn to code in Python. What was required was a real world, practical project to work on and the Pontificating Panda Chartbook was born. The objective was to develop a cross-asset financial chartbook using Open Source tools and data.

Fair warning to anyone here - DON'T TRUST ANYTHING HERE


## Build Plan
What you can see here is very much a **work in progress**. The list below is a running list of additions I would like to make to the book in the coming few weeks and months - it isn't a comprehensive list of everything I'd like to add, more things I will (hopefully) have time to do.

#### Static Data
* More detailed "About Me" section
* Updated CV page with links
* World Selection fund information
* Bibliography - Journal articles from SSRN etc...

#### Data Dump
* Pull TS OHLC Data from Alpha Vantage for US listed ETFs and store as pickle
* Pull Pokemon data and store as pickle

#### Static Chartbook
Cross-Asset
* Prinipal Drivers Index
* Correlations Dendrogram

Fixed Income
* Pokemon model

Eco
* OECD CLIs & Swirlygrams

FX
* Spot price returns
* REER

Commodities
* Key charts for Oil, Precious Metals, Industrial Metals, Soft Commodities(?)
* Curve Term structure

#### Notebooks
* Pokemon Model
* Principal Drivers Index & Correlation Dendrogram

#### BadgerPM
* Repackage homemade dependencies and publish to github

#### Binder
* create binder folder to allow people to play with Jupyter Notebooks (with callbacks etc...)

#### Plotly Dash
Ultimately replace this entire book with a Dash App (or Flask website)
But more short term:
* Publish Python only Re-sampled Optimiser
* Publish work on Income Optimisation


## Acknowledgements

Jupyter Books was originally created by [Sam Lau][sam] and [Chris Holdgraf][chris]
with support of the **UC Berkeley Data Science Education Program and the Berkeley
Institute for Data Science**.

[sam]: http://www.samlau.me/
[chris]: https://predictablynoisy.com
