# 4. Extract company Stock Data via URL

This code essentially fetches historical stock data from Yahoo Finance for a specified ticker symbol and date range, converts the dates to Unix timestamps, makes an HTTP request to the Yahoo Finance API, and saves the fetched data to a CSV file.

## code :

The user is prompted to input a ticker symbol (like AAPL, MSFT) and two dates (`from_date` and `to_date`) in the format 'YYYY-MM-DD'. These dates are then converted into `datetime` objects using `datetime.strptime`.

Using `time.mktime`, the `datetime` objects are converted into Unix timestamps (`from_epoch` and `to_epoch`). Unix timestamps are the number of seconds that have elapsed since January 1, 1970 (UTC).

A URL string is constructed using Yahoo Finance's API (`query1.finance.yahoo.com`) to fetch historical stock data (`https://query1.finance.yahoo.com/v7/finance/download/`). It includes the ticker symbol (`ticker`), start and end timestamps (`period1` and `period2`), interval (`1d` for daily), and events to retrieve (`history` and `includeAdjustedClose=true`).

`requests.get` sends an HTTP GET request to the constructed URL. The request includes headers to mimic a web browser (`User-Agent` header). The response is fetched as raw content (`content`).

The fetched content (historical stock data in CSV format) is written to a file named `data3.csv` in binary mode (`'wb'`). This file can then be used for further analysis or processing.

This script essentially fetches historical stock data from Yahoo Finance for a specified ticker symbol and date range, converts the dates to Unix timestamps, makes an HTTP request to the Yahoo Finance API, and saves the fetched data to a CSV file named `data3.csv`.
