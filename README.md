# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 4.03.2025

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```c
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import holoviews as hv
hv.extension('bokeh')
```
```c
file_path = 'IOT-temp.csv'  # Replace with your file path
data = pd.read_csv(file_path)
```
```c
data = data[(data['temp'] > 0) & (data['temp'] < 50)]
data['noted_date'] = pd.to_datetime(data['noted_date'], dayfirst=True)
data['hour'] = data['noted_date'].dt.hour
data['day'] = data['noted_date'].dt.day
data['month'] = data['noted_date'].dt.month
```
```c
plt.figure(figsize=(12, 6))
sns.boxplot(x='hour', y='temp', data=data)
plt.title("Trend Month vs Temp")
plt.xlabel("Temp")
plt.ylabel("Month")
plt.show()
```









# OUTPUT:

![image](https://github.com/user-attachments/assets/7ae128aa-4d91-4ae6-90fa-f1566208d879)








# RESULT:
Thus we have created the python code for plotting the time series of given data.
