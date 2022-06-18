## Time-Series modeling

Time Series forecasting for Daily Bike Shares [data](https://www.kaggle.com/datasets/contactprad/bike-share-daily-data), using different approaches. It is a daily time series covering a 2-year period.

Raw time-series:
<p align="center">
  <img 
    width="600"
    height="300"
    src="https://github.com/uditgt/TimeSeries/blob/main/assets/DailyBikeSharing.png"
  >
</p>

Modeled time-series:


**Modeling Approaches Explored:**
1. **Holt-Winters exponential smoothing** - 
   * Comprises: triple exponential smoothing for ETS - Error, Trend, Seasonality
   * [Notebook](https://github.com/uditgt/TimeSeries/blob/main/1.%20Holt-Winters.ipynb) including forecasting for weekly Airmiles data. [article](https://timeseriesreasoning.com/contents/holt-winters-exponential-smoothing/)
2. **SARIMAX** -
   * Comprises: Seasonality + ARIMA + External regressors (holiday flags, strategic shifts etc.)
   * Notebook including forecasting for weekly Churrasco data
3. **TBATS** -
   * Comprises:
     * Trigonometric terms for seasonality
     * Box-Cox transformations for heterogeneity (transforming closer to normal)
     * ARMA errors for short-term dynamics
     * Trend (possibly damped)
     * Seasonal (including multiple and non-integer periods)
   * **Pros/Cons**:
     * handles non-integer seasonality, multiple seasonal periods (can also change over time)
     * Does NOT accomodate exogenous regressors
4. **Tensorflow Structural Time Series** -
   * Library built on TensorFlow; makes it easy to combine probabilistic models and deep learning. [webpage](https://www.tensorflow.org/probability)
   * Rob Hyndman's [slides](https://robjhyndman.com/nyc2018/3-2-TBATS.pdf)
   * **Pros/Cons**:
     * Flexible, good with short-term dynamics, accomodates exogenous regressors, intuitive
     * Complex model setup, model fitting takes time
   * Notebook including forecasting for weekly Store Footfall data, including comparison with SARIMAX
5. **Facebook's Prophet** - 
   * Comprises: Trend + Seasonality + Holiday Effects + External Regressors + error
      * Trend - linear or logistic
      * Seasonality - yearly/ weekly/ daily ... multiplicative/ additive
      * Holiday effect - define the specific day, and 'window' of days around it
    * **Pros/Cons**:
      * Flexible/ customizable, dynamic events, allows regressors, *automatic*
      * Built-in cross validation and hyperparameter tuning

**Learning Resources:**
* Udemy [lectures](https://www.udemy.com/course/forecasting-python/)
* **Forecasting Principles & Practice** [ebook](https://otexts.com/fpp3/)
* Rob Hyndman's [slides](https://robjhyndman.com/seminars/nyc2018/), [slides2](https://github.com/robjhyndman/ETC3550Slides), [blog](https://robjhyndman.com/), [seminars](https://robjhyndman.com/seminars/), [datacamp](https://app.datacamp.com/learn/courses/forecasting-in-r)
