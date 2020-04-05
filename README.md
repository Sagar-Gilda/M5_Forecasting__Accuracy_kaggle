# M5_Forecasting__Accuracy_kaggle
Kaggle competition to improve the forecast accuracy using ML.
The goal: We have been challenged to predict sales data provided by the retail giant Walmart 28 days into the future. This competition will run in 2 tracks: In addition to forecasting the values themselves in the Forecasting competition, we are simultaneously tasked to estimate the uncertainty of our predictions in the Uncertainty Distribution competition. Both competitions will have the same 28 day forecast horizon.

We are working with 42,840 hierarchical time series. The data were obtained in the 3 US states of California (CA), Texas (TX), and Wisconsin (WI). “Hierarchical” here means that data can be aggregated on different levels: item level, department level, product category level, and state level. The sales information reaches back from Jan 2011 to June 2016. In addition to the sales numbers, we are also given corresponding data on prices, promotions, and holidays. Note, that we have been warned that most of the time series contain zero values.

The data comprises 3049 individual products from 3 categories and 7 departments, sold in 10 stores in 3 states. The hierachical aggregation captures the combinations of these factors. For instance, we can create 1 time series for all sales, 3 time series for all sales per state, and so on. The largest category is sales of all individual 3049 products per 10 stores for 30490 time series.

The training data comes in the shape of 3 separate files:
sales_train.csv: this is our main training data. It has 1 column for each of the 1941 days from 2011-01-29 and 2016-05-22; not including the validation period of 28 days until 2016-06-19. It also includes the IDs for item, department, category, store, and state. The number of rows is 30490 for all combinations of 30490 items and 10 stores.

sell_prices.csv: the store and item IDs together with the sales price of the item as a weekly average.

calendar.csv: dates together with related features like day-of-the week, month, year, and an 3 binary flags for whether the stores in each state allowed purchases with SNAP food stamps at this date (1) or not (0).

Key Findings:
The sales are generally going up from 2012-2016. We can make out some yearly seasonality, and a dip at Christmas, which is the only day of the year when the stores are closed.
California (CA) sells more items in general, while Wisconsin (WI) was slowly catching up to Texas (TX) and eventually surpassed it in the last months of our training data.
“Foods” are the most common category, followed by “Household” which is still quite a bit above “Hobbies”. The number of “Household” rows is closer to the number of “Foods” rows than the corresponding sales figures, indicating that more “Foods” units are sold than “Household” ones.
“FOODS_3” is clearly driving the majority of “FOODS” category sales in all states. “FOODS_2” is picking up a bit towards the end of the time range, especially in “WI”.

Planning to do items:
Feature Engineering: 
Need to CPI (Consumer Price Index) data for 2014-2016 might come handy
Weather Data - people dont do shopping generally on Rainy or snowy days
US Elections
Macro Economic factors
Holidays - people tend to shop more or move out of house on holidays
