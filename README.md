## EXP 3: Log Transformation of International Airline Passenger Data
## NAME : LIVYA DHARSHINI G
## REGISTER NUMBER : 2305001013
## Aim
To perform log transformation on the International Airline Passenger dataset using Python.
## Ojectives
1. To load the airline passenger dataset.
   
3. To visualize the original time series data.
   
5. To apply log transformation using NumPy.
   
7. To compare the original and transformed time series.
   
9. To analyze variance before and after transformation.

## Program
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# 1. Load AirPassengers dataset
df = pd.read_excel("/content/AirPassengers.xlsx")

# Convert Month to datetime
df['Month'] = pd.to_datetime(df['Month'])

# Set Month as index
df.set_index('Month', inplace=True)

print("Original Data:")
print(df.head())

# 2. Plot original time series
plt.figure(figsize=(12, 5))
plt.plot(
    df.index,
    df['Passengers'],
    marker='o'
)

plt.title('International Airline Passengers')
plt.xlabel('Year')
plt.ylabel('Passengers (Thousands)')
plt.grid(True)
plt.show()

# 3. Apply log transformation
df['Log_Passengers'] = np.log(df['Passengers'])

print("\nLog Transformed Data:")
print(df.head())

# 4. Plot log-transformed series
plt.figure(figsize=(12, 5))
plt.plot(
    df.index,
    df['Log_Passengers'],
    marker='o'
)

plt.title('Log-Transformed Airline Passenger Data')
plt.xlabel('Year')
plt.ylabel('Log(Passengers)')
plt.grid(True)
plt.show()

# 5. Compare the series
fig, axes = plt.subplots(2, 1, figsize=(12, 8))

axes[0].plot(df.index, df['Passengers'])
axes[0].set_title('Original Airline Passenger Series')
axes[0].set_ylabel('Passengers')
axes[0].grid(True)

axes[1].plot(df.index, df['Log_Passengers'])
axes[1].set_title('Log-Transformed Airline Passenger Series')
axes[1].set_ylabel('Log(Passengers)')
axes[1].set_xlabel('Year')
axes[1].grid(True)

plt.tight_layout()
plt.show()
```
## Output

<img width="717" height="545" alt="Screenshot 2026-10-29 091056" src="https://github.com/user-attachments/assets/9fa4a3c5-8612-4fd3-9430-0070b103ec1e" />




<img width="842" height="597" alt="image" src="https://github.com/user-attachments/assets/34a712eb-92c6-4f61-92d5-ff3ce942c3ee" />



<img width="847" height="557" alt="image" src="https://github.com/user-attachments/assets/48cd3559-77af-4439-a026-30ccaaa21ab8" />

## Result

Log transformation was successfully applied to the International Airline Passenger dataset. The
original and transformed series were plotted and compared. The transformation compresses larger
values and may help stabilize increasing variability.


