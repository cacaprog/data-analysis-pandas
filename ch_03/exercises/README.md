### Exercises

Complete the following exercises using what we have learned so far in this book and the
data in the exercises/ directory:

1. We want to look at data for the Facebook, Apple, Amazon, Netflix, and Google (FAANG) stocks, but we were given each as a separate CSV file (obtained using the stock_analysis package we will build in Chapter 7, Financial Analysis – Bitcoin and the Stock Market). Combine them into a single file and store the dataframe of the FAANG data as faang for the rest of the exercises:

    a) Read in the aapl.csv, amzn.csv, fb.csv, goog.csv, and nflx.csv files.

    b) Add a column to each dataframe, called ticker, indicating the ticker symbol it is for (Apple's is AAPL, for example); this is how you look up a stock. In this case, the filenames happen to be the ticker symbols.

    c) Append them together into a single dataframe.

    d) Save the result in a CSV file called faang.csv.


2. With faang, use type conversion to cast the values of the date column into datetimes and the volume column into integers. Then, sort by date and ticker.


3. Find the seven rows in faang with the lowest value for volume.


4. Right now, the data is somewhere between long and wide format. Use melt() to make it completely long format. Hint: date and ticker are our ID variables (they uniquely identify each row). We need to melt the rest so that we don't have separate columns for open, high, low, close, and volume.


5. Suppose we found out that on July 26, 2018 there was a glitch in how the data was recorded. How should we handle this? Note that there is no coding required for this exercise.


6. The European Centre for Disease Prevention and Control (ECDC) provides an open dataset on COVID-19 cases called daily number of new reported cases of COVID-19 by country worldwide (https://www.ecdc.europa.eu/en/publications-data/download-todays-data-geographic-distribution-covid-19-cases-worldwide). This dataset is updated daily, but we will use a snapshot that contains data from January 1, 2020 through September 18, 2020. Clean and pivot the data so that it is in wide format:
    
    a) Read in the covid19_cases.csv file.

    b) Create a date column using the data in the dateRep column and the pd.to_datetime() function.

    c) Set the date column as the index and sort the index.

    d) Replace all occurrences of  United_States_of_America and United_Kingdom with USA and UK, respectively. Hint: the replace() method can be run on the dataframe as a whole.

    e) Using the countriesAndTerritories column, filter the cleaned COVID-19 cases data down to Argentina, Brazil, China, Colombia, India, Italy, Mexico, Peru, Russia, Spain, Turkey, the UK, and the USA.

    f) Pivot the data so that the index contains the dates, the columns contain the country names, and the values are the case counts (the cases column). Be sure to fill in NaN values with 0.



7. In order to determine the case totals per country efficiently, we need the aggregation skills we will learn about in Chapter 4, Aggregating Pandas DataFrames, so the ECDC data in the covid19_cases.csv file has been aggregated for us and saved in the covid19_total_cases.csv file. It contains the total number of cases per country. Use this data to find the 20 countries with the largest COVID-19 case totals. Hints: when reading in the CSV file, pass in index_col='cases', and note that it will be helpful to transpose the data before isolating the countries.


---

# About the data

| File | Description | Source |
| --- | --- | --- |
| `aapl.csv` | Daily opening, high, low, and closing price of Apple stock, along with volume traded for 2018. | The `stock_analysis` package (see *Chapter 7, Financial Analysis &ndash; Bitcoin and the Stock Market*). |
| `amzn.csv` | Daily opening, high, low, and closing price of Amazon stock, along with volume traded for 2018. | The `stock_analysis` package (see *Chapter 7, Financial Analysis &ndash; Bitcoin and the Stock Market*). |
| `covid19_cases.csv` | ECDC's *daily number of new reported cases of COVID-19 by country worldwide dataset* from January 1, 2020 through September 18, 2020. | ECDC's *daily number of new reported cases of COVID-19 by country worldwide dataset*. |
| `covid19_total_cases.csv` | Pivot table of total COVID-19 cases per country from January 1, 2020 through September 18, 2020. | ECDC's *daily number of new reported cases of COVID-19 by country worldwide dataset* pivoted to calculated total cases per country. |
| `fb.csv` | Daily opening, high, low, and closing price of Facebook stock, along with volume traded for 2018. | The `stock_analysis` package (see *Chapter 7, Financial Analysis &ndash; Bitcoin and the Stock Market*). |
| `goog.csv` | Daily opening, high, low, and closing price of Google stock, along with volume traded for 2018. | The `stock_analysis` package (see *Chapter 7, Financial Analysis &ndash; Bitcoin and the Stock Market*). |
| `nflx.csv` | Daily opening, high, low, and closing price of Netflix stock, along with volume traded for 2018. | The `stock_analysis` package (see *Chapter 7, Financial Analysis &ndash; Bitcoin and the Stock Market*). |

### Sources
- The European Centre for Disease Prevention and Control's (ECDC) *daily number of new reported cases of COVID-19 by country worldwide dataset* can be found [here](https://www.ecdc.europa.eu/en/publications-data/download-todays-data-geographic-distribution-covid-19-cases-worldwide). The data here was collected on September 19, 2020 via [this](https://opendata.ecdc.europa.eu/covid19/casedistribution/csv) link.
- The [`stock_analysis`](https://github.com/stefmolin/stock-analysis) package contains easy to use interfaces for basic technical analysis of stocks. We will walk through the construction of this package in *Chapter 7, Financial Analysis &ndash; Bitcoin and the Stock Market*.

