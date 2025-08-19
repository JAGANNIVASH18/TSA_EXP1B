# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA


### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
### Developed by: JAGANNIVASH U M
### Register no: 212224240059
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Load the data
data = pd.read_csv("AirPassengers.csv")
# Create DataFrame
df = pd.DataFrame(data)

# Regular differencing
df['Regular Difference'] = df['#Passengers'].diff()

# Seasonal adjustment
result = seasonal_decompose(df['#Passengers'], model='additive', period=12)
df['Seasonal Adjustment'] = result.resid

# Log transformation
df['Log Transformation'] = np.log(df['#Passengers'])

# Plotting
plt.figure(figsize=(14, 10))

plt.subplot(4, 1, 1)
plt.plot(df['#Passengers'], label='Original')
plt.legend(loc='best')
plt.title('Original Data')

plt.subplot(4, 1, 2)
plt.plot(df['Regular Difference'], label='Regular Difference')
plt.legend(loc='best')
plt.title('Regular Differencing')

plt.subplot(4, 1, 3)
plt.plot(df['Seasonal Adjustment'], label='Seasonal Adjustment')
plt.legend(loc='best')
plt.title('Seasonal Adjustment')

plt.subplot(4, 1, 4)
plt.plot(df['Log Transformation'], label='Log Transformation')
plt.legend(loc='best')
plt.title('Log Transformation')

plt.tight_layout()
plt.show()
```
### OUTPUT:
#### ORIGINAL DATA:
<img width="1242" height="229" alt="Screenshot 2025-08-19 133021" src="https://github.com/user-attachments/assets/f2b55336-e125-48de-b6b3-fed5beeae2df" />


#### REGULAR DIFFERENCING:

<img width="1275" height="216" alt="Screenshot 2025-08-19 133054" src="https://github.com/user-attachments/assets/cd3f6a46-9334-4cf7-b0d9-955a64b5f5a0" />




#### SEASONAL ADJUSTMENT:

<img width="1262" height="221" alt="Screenshot 2025-08-19 133111" src="https://github.com/user-attachments/assets/d5565260-6ae6-4790-a254-9c493d27b337" />


#### LOG TRANSFORMATION:
<img width="1257" height="233" alt="Screenshot 2025-08-19 133124" src="https://github.com/user-attachments/assets/93e55341-367b-4510-9872-70f76a34a5cd" />





### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
