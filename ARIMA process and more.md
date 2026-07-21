# ARIMA as AR + I + MA

For the future convenience I will focus on AR, moving into MA and end up with I part. That path is the most natural.

## AR 

In AR processes (notation AR(p)) we assume, future values depend on past values, 'p' determines the level of "lookback" into the past.

$$ X_t = c + \sum_{i=1}^{p}\phi_iX_{t-i} + \varepsilon_t $$

From the structure we already know a lot. IF it somehow turns out that this model is actually the best one, we already kave full knowledge and can do pretty much
anything we want - precitcing future values is simple, dependence fully explained ect. 

The real issue is to somehow dientify whether given model actually describes well given dataset. That is the key in modelling real word processes. 

Here, there are already few challanges:
1. In general, what are the assumptions here,
2. What is $\varepsilon_t$ - what properties, how to check it's assumptions
3. How to estimate parameters $\phi_i$. If we manage to estimate them, how can we check it's stability, maybe est of estimated value is close to some edge case.

In order to answer those questions, let's focus on $\varepsilon_t$ part. We assume, that process is time series process called [white noice](https://en.wikipedia.org/wiki/White_noise). I will place here the definition.
1. $E(\varepsilon_{t} = \mu)$
2. $Var(\varepsilon_t)=\sigma^2$
3. $Cov(\varepsilon_{t},\varepsilon_{t+h})=0, h\neq 0$
   
Here, $E$ is expected value of random variable, $Var$ is variance $Var(\varepsilon_t) = E^2(\varepsilon_t)-E(\varepsilon_t^2)$ and $Cov$ is covaraince $Cov(\varepsilon_{t},\varepsilon_{t+h}) = E(\varepsilon_{t}\varepsilon_{t+h}) - E(\varepsilon_{t})E(\varepsilon_{t+h})$
It is crucial to keep in mind those assumptions when thinking about picking final model for given dataset

---

## Proper ARIMA model

Notation ARIMA(p,d,q).

p tells us how many of past observations are we using, d - how many times we differenciate our series, and q-how many of past errors we use. After some time - exactly q, that part becomes irrelevant, no longer has impact. Case eg. cales in shop and single malfunction. It has impact on clients on that day - less clients and probably to some extent on few next days, no more! In AR, constatnly using past values!

Every time one come across some time series should ask yourself a question about few things:
1. Is there a trend
2. Seasionality?
3. Changes in Variation
4. Drastic jumps

AR and MA assume that mean is more or less stable, variation similar, correlations stay constant in time. If we notice some other behaviour, they may not be the best. For example if there is a linear trend, we can try to differenciate! 

In particular, in AR component $c$ is not a trend. After some time it will be around the mean which is equal to $\mu = \freac{c}{1-\theta}$ for AR(1).

Key here is to understand type of trend - dereministic or stochastic.

Deterministic - we already have planed future values, local error does not impact planned states e.g. every month we open some shop. Revenue may be then $X_t = 100 + 10t + /varepsilon_t$.
Some local impacts does not influecne future. On the other side in case of $X_t = X_{t-1} + \varepsion_t$ the erros DO impact future, that is stochastic error, but both of them may be written as vector!

WHEN ARIMA IS GOOD CANDIDATE:
- One time variable
- Clear dependence from the past
- There is trend or non-stationality, but after 1/2 differntiacions it dissapears.
- No clear sezionality (if visible - SARIMA)
- After differenciating structure seems to be possible to use AR/MA

WHEN ARIMA IS NOT GOOD:
- External variables impact e.g. ads, weather -> ARIMAX/SARIMAX
- Visible changes in volatility -> GARCH may be better
- Strong non-linearity or complex dependences

In order to  examine time series in the context of ARIMA model, one should refer to original list proposed in Box, Jenkins, Reinsel, Ljung — Time Series Analysis: Forecasting and Control.

1. Identification
2. Estimation
3. Diagnostic checking
4. Forecasting

1. Consider plot, check ACF, do stationaroty tests (ADF, KPSS), check variance



