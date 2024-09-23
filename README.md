# Project1
This Python code is designed to analyze a time series data set by extracting the trend and seasonality components using moving averages.

Libraries Imported
- NumPy: For numerical operations and array handling.
- Pandas: Although imported, it's not used in this code. It can be helpful for data manipulation.
- Matplotlib: For plotting the time series data, trends, and seasonality.
- 
 Functions Defined
1.moving_average_odd(data, q):
   - Calculates the moving average for datasets with an odd number of elements.
   - For each point in the data, it computes the average of the points in a window defined by q (the number of points on either side).

2. moving_average_even(data, q):
   - Similar to the odd moving average, but designed for datasets with an even number of elements.
   - Adjusts the calculation slightly to account for the even length by weighting the first and last points in the window.

3. calculate_w_k(data, trend, d):
   - Computes w_k, which represents the irregularity and seasonality of the data relative to the calculated trend.
   - For each point, it sums the deviations from the trend at intervals defined by d (a parameter for periodicity).

4. calculate_g_k(w_k, d):
   - Calculates g_k, which indicates the seasonal component.
   - It finds the average of w_k and then centers w_k around this average.

Example Usage
- Data Input: An example time series data array is provided.
- User Input: The user is prompted to enter the value of q, which controls the moving average window size.
- Trend Calculation: The code determines whether the length of the data is odd or even and calls the appropriate moving average function.
- Seasonality Calculation: After determining the trend, it computes w_k and then g_k.

Output
- The program prints the trend and seasonality arrays.
- Finally, it visualizes the original data, the trend, and the seasonality using three subplots.

Observations on Output
- When the user enters q = 10, the output shows a trend array primarily filled with zeros, indicating a lack of sufficient data points to compute a meaningful trend due to q being too large relative to the length of the dataset.
- The seasonality (g_k) shows fluctuations, suggesting variations around the average deviations from the trend.
