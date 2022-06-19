## Time-Series modeling

Time Series forecasting for Daily Bike Shares [data](https://www.kaggle.com/datasets/contactprad/bike-share-daily-data), using different approaches. It is a daily time series covering a 2-year period. The challenge is to forecast for the month of Dec-12, which exhibits considerable volatility.

Raw time-series:
<p align="center">
  <img 
    width="600"
    height="300"
    src="https://github.com/uditgt/TimeSeries/blob/main/assets/DailyBikeSharing.png"
  >
</p>

Modeled time-series - select models:
<p align="center">
  <img 
    width="600"
    height="300"
    src="https://github.com/uditgt/TimeSeries/blob/main/assets/DailyBikeSharing%20-%20fitted.png"
  >
</p>

Modeled time-series - (naive) ensemble approach:
<p align="center">
  <img 
    width="600"
    height="300"
    src="https://github.com/uditgt/TimeSeries/blob/main/assets/DailyBikeSharing%20-%20fitted_ensemble.png"
  >
</p>


**Modeling Approaches Explored:**
1. **[Holt-Winters exponential smoothing](https://github.com/uditgt/TimeSeries/blob/main/1.%20Holt-Winters.ipynb)** - 
   * Comprises: triple exponential smoothing for ETS - Error, Trend, Seasonality
   * Explanation [blog post](https://timeseriesreasoning.com/contents/holt-winters-exponential-smoothing/)
2. **[SARIMAX](https://github.com/uditgt/TimeSeries/blob/main/2.%20SARIMAX.ipynb)** -
   * Comprises: Seasonality + ARIMA + External regressors (holiday flags, strategic shifts etc.)
3. **[TBATS](https://github.com/uditgt/TimeSeries/blob/main/3.%20TBATS.ipynb)** -
   * Comprises:
     * Trigonometric terms for seasonality
     * Box-Cox transformations for heterogeneity (transforming closer to normal)
     * ARMA errors for short-term dynamics
     * Trend (possibly damped)
     * Seasonal (including multiple and non-integer periods)
   * Pros/Cons:
     * handles non-integer seasonality, multiple seasonal periods (can also change over time)
     * Does NOT accomodate exogenous regressors
4. **[Tensorflow Structural Time Series](https://github.com/uditgt/TimeSeries/blob/main/4.%20Tensorflow.ipynb)** -
   * Library built on TensorFlow; makes it easy to combine probabilistic models and deep learning. [webpage](https://www.tensorflow.org/probability)
   * Rob Hyndman's [slides](https://robjhyndman.com/nyc2018/3-2-TBATS.pdf)
   * Pros/Cons:
     * Flexible, good with short-term dynamics, accomodates exogenous regressors, intuitive
     * Complex model setup, model fitting takes time
   * Notebook including forecasting for weekly Store Footfall data, including comparison with SARIMAX
5. **[Facebook's Prophet](https://github.com/uditgt/TimeSeries/blob/main/5.%20Facebook%20Prophet.ipynb)** - 
   * Comprises: Trend + Seasonality + Holiday Effects + External Regressors + error
      * Trend - linear or logistic
      * Seasonality - yearly/ weekly/ daily ... multiplicative/ additive
      * Holiday effect - define the specific day, and 'window' of days around it
    * Pros: Flexible/ customizable, dynamic events, allows regressors, *automatic*, Built-in cross validation and hyperparameter tuning
6. **XGBoost + Prophet** - 
   * Stage 1: Fit Prophet model, and take select forecast variables to augment original feature matrix
   * Stage 2: Fit XGBoost Regression model on the updated feature matrix



**Learning Resources:**
* Udemy [lectures](https://www.udemy.com/course/forecasting-python/)
* **Forecasting Principles & Practice** [ebook](https://otexts.com/fpp3/)
* Rob Hyndman's [slides](https://robjhyndman.com/seminars/nyc2018/), [slides2](https://github.com/robjhyndman/ETC3550Slides), [blog](https://robjhyndman.com/), [seminars](https://robjhyndman.com/seminars/), [datacamp](https://app.datacamp.com/learn/courses/forecasting-in-r)
