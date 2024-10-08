# Trend-and-seasonality
## Import
matplotlib.pyplot: A plotting library used to visualize the data and its components (original data, trend, seasonality).

pandas: A data manipulation library used to load and process the CSV file.
## Loading Data
The CSV file is loaded using pandas.read_csv().

It extracts the 'VWAP' (Volume Weighted Average Price) column from the dataset and stores it in variable y. This column represents the time series that will be analyzed.
## Functions to Estimate Trend and Seasonality
This function estimates the trend component of the time series. It uses a moving window of size d (either odd or even) to smooth the series.

The function loops over each time step t and averages the values within the window centered around t.

For odd values of d, the window is symmetric, but for even d, it shifts slightly to account for the window size.

The result is a smoothed trend component of the series.

This function estimates the seasonality component by dividing the original series y by its trend component. This isolates the periodic fluctuations (seasonal variations) in the data.
## Choosing the Window Size d
This simple logic checks if the length of the time series y is even or odd and sets d accordingly. If the series length is even, the window size d is set to 3, otherwise, it’s set to 4.
## Computing Trend and Seasonality
The trend and seasonality are computed by calling the previously defined functions with y and the chosen window size d.
## Plotting the Results
Three subplots are created:
     
     The original time series.
     
     The estimated trend component.
     
     The estimated seasonality component.

The layout is made tight using plt.tight_layout() to ensure there’s no overlap between the plots.
