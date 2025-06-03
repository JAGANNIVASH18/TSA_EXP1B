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
### Developed by: AFSAR JUMAIL S
### Register no:212222240004
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

![image](https://github.com/user-attachments/assets/09883be6-56a5-43bc-b6e1-ab1a8066faf5)

#### REGULAR DIFFERENCING:

![image](https://github.com/user-attachments/assets/7922a094-902f-45b0-b43d-6a053f9930fc)



#### SEASONAL ADJUSTMENT:

![image](https://github.com/user-attachments/assets/3b8b45d9-1244-4ffc-ac57-d945b391e2b3)

#### LOG TRANSFORMATION:

![image](https://github.com/user-attachments/assets/097e20cc-3c1d-4c30-9518-a42fc70260bc)




### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
