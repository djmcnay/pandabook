---
redirect_from:
  - "/features/pokemon-primer"
interact_link: content/features/pokemon_primer.ipynb
kernel_name: python3
has_widgets: false
title: 'Pokemon Fair Value'
prev_page:
  url: /features/features
  title: 'Notebooks'
next_page:
  url: 
  title: ''
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

# Primer for the Pokemon Fair Value bond model

The intuition behind the model presented here is relatively simple - the *"Fair Value"* of a long dated bond should be a function of short-term interest rates, inflation and economic growth. Additionally as capital allocation becomes increasing global it is reasonable that our *"Fair Value"* should include a global factor.


$ FV_{x} = \beta_{x,0} 
+\beta_{x,1}\times \text{Rates} 
+\beta_{x,2} \times \text{Inf}
+\beta_{x,3} \times \text{Growth}
+\beta_{x,4}\times \text{Global}
+\epsilon_{x}$

Mathematically we are indifferent to the choice of input, as we are simply calculating a multi-variate linear regression over several rolling windows; practically variable selection is probably the most challenging part of the model. If we assume markets attempt to incorporate forward estimates into prices than similarly we would prefer to incorporate forward looking macro variables into our estimates. Exact inputs are covered below, but in general:
* Short-Rates - forward path of cash rates is modelled by the current 2-year rate
* Inflation - ideally taken from market implied inflation from breakeven rates or inflation swaps
* Growth - survey based (ISM) or from Composite Leading Indicators like the [OECD CLIs](http://www.oecd.org/sdd/leading-indicators/)
* Global Factor - **most difficult** but could be the [BIS REER](https://www.bis.org/statistics/eer.htm) or a blend of global bonds

## Fair Value Output

## Sample Python Code

Where the Pokemon FV model has been presented elsewhere in the chartbook it has been calculated using a homemade class function - eventually this will be wrapped and posted to PyPi - but the code below is a sample of what is happening.

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
def pokemon(df, window=36, valiadate_data=True):
    # REQUIREMENTS:
    #    from sklearn.linear_model import LinearRegression
    # INPUTS:
    #    df - DataFrame with datetimeindex, col[0] as long bond & col[1+] as regression variables
    #    window - rolling regression window; default is 36 months
    #    validate_data - forward fills missing data (useful where we may be missing current month)
    # OUTPUTS:
    #    guess - DataFrame with long-bond, full sample and rolling model outputs
    #    stats - coefficients for each thingy
    
    if valiadate_data is True:
        df.fillna(method='ffill', inplace=True)   # Forward fill missing data
        df = df[~df.isna().any(axis=1)]           # Each row complete
        
    # Dummy Dataframe(s)
    guess = pd.DataFrame(data=df.iloc[:,0])
    guess.columns = ['long_bond']
    coeff_vn = ['r2', 'intercept']
    coeff_vn.extend(list(df.columns.values)[1:])
    stats = pd.DataFrame(columns=coeff_vn)
        
    # Full Sample Period
    y, X = df.iloc[:,0], df.iloc[:,1:]
    lm = LinearRegression().fit(X,y)
    guess['full_sample'] = lm.predict(X)
    stats.loc['full_sample',['r2','intercept']]=lm.score(X, y),lm.intercept_
    stats.loc['full_sample'].iloc[2:] = lm.coef_
        
    # Rolling Window
    for i, v in enumerate(guess.index):   
        if i < window:
            continue
            
        y = df.iloc[i-window:i,0]     # Dependant Var [long bond]
        X = df.iloc[i-window:i,1:]    # Independant [short, inf, growth]
        roll_lm = LinearRegression().fit(X,y)
        guess.loc[v,'rolling'] = roll_lm.predict(X)[-1]
        stats.loc[v,['r2', 'intercept']] = roll_lm.score(X, y), lm.intercept_
        stats.loc[v].iloc[2:] = roll_lm.coef_ 

    return guess, stats
```
</div>

</div>

## Data Sources

All data is open sourced and comes from [Quandl](www.quandl.com). For the Pokemon model this means a compromise between what we would consider to be the optimal data and what is easily achievable. Below note the data used here (and consider some better data).

__US Treasuries__
* [US Treasury](https://www.quandl.com/data/USTREASURY/YIELD-Treasury-Yield-Curve-Rates) for nominal 10 & 2 year yields
* [UMich](https://www.quandl.com/data/UMICH/SOC33-University-of-Michigan-Consumer-Survey-Expected-Change-in-Prices-During-the-Next-5-Years) 5-year Median Inflation Expectations
* [ISM Mfg Composite](https://www.quandl.com/data/ISM/MAN_PMI-PMI-Composite-Index) for Growth estimates

__Gilts__
* [Bank-of-England](https://www.quandl.com/data/BOE/IUDMNZC-Yield-From-British-Government-Securities-10-Year-Nominal-Zero-Coupon) 10-year Nominal Zero-Coupon as a proxy for the standard nominal
* [ECB](https://www.quandl.com/data/ECB/FM_M_GB_GBP_RT_MM_GBP3MFSR__HSTA-United-Kingdom-Money-Market-GB-Pound-Sterling-3-month-British-Bankers-Association-Libor-Historical-close-average-of-observations-through-period-UK-pound-sterling-provided-by-Reuters) provide the 3m GBP LIBOR rate; need a better source but the BoE doesn't publish the 2 (or 1) year gilt yields or forward rate data. 
* [Rate Inflation](https://www.quandl.com/data/RATEINF/INFLATION_GBR-Inflation-YOY-UK)
* [OECD Amplitude-Adjusted Composite Leading Indicator](https://www.quandl.com/data/OECD/MEI_CLI_LOLITOAA_GBR_M-Amplitude-Adjusted-Cli-United-Kingdom)

__Bunds__
* Bundesbank for the [10-year](https://www.quandl.com/data/BUNDESBANK/BBK01_WT1010-Daily-Yield-Of-The-Current-10-Year-Federal-Bond) & [2-year](https://www.quandl.com/data/BUNDESBANK/BBK01_WT0202-Daily-Yield-Of-The-Current-two-year-Federal-Treasury-Notes) Bund yield. This needs further investigation as the Quandl dataset for the German 2-year only goes back to Jan-14, *which isn't enough for a sensible full-sample model*
* [Rate Inflation](https://www.quandl.com/data/RATEINF/INFLATION_DEU-Inflation-YOY-Germany)
* [OECD Amplitude-Adjusted Composite Leading Indicator](https://www.quandl.com/data/OECD/MEI_CLI_LOLITOAA_DEU_M-Amplitude-Adjusted-Cli-Germany)

__JGBs__
* [Ministry of Finance Japan]() for the [10-year](https://www.quandl.com/data/MOFJ/INTEREST_RATE_JAPAN_10Y-JGB-Interest-Rates-Term-Structure-10Y) & [2-year](https://www.quandl.com/data/MOFJ/INTEREST_RATE_JAPAN_2Y-JGB-Interest-Rates-Term-Structure-2Y) JGBs
* [Rate Inflation](https://www.quandl.com/data/RATEINF/INFLATION_JPN)
* [OECD Amplitude-Adjusted Composite Leading Indicator](https://www.quandl.com/data/OECD/MEI_CLI_LOLITOAA_JPN_M-Amplitude-Adjusted-Cli-Japan)

## Small Print

It should come as no surprise that the concept presented here is not new. Any CFA candidate who has has been even vaguely dilligent should recognise the basis. [NDR](https://www.ndr.com/group/ndr/content-viewer/-/v/B0410A) do some excellent modelling and often present a simplified version and [Goldman Sachs Research](https://research.gs.com/) have been incorporating a [forward looking Sudoku Fair Value](http://www.verstyuk.net/papers/GlobalViewpoint.07-24.pdf) model in their Fixed Income research since 2007; the GS model is probably superior as they take more time developing a trade-weighted variable for the *"Global"* factor.

Pokemon is indeed a nod to the childrens cartoon series. The point at which the model was developed happened to coincide with the Pokemon Go phenomenon in the UK during which time several PMs and Analysts were found wondering Green Park in London in search of Pokemon.
