# Import necessary libraries
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Mount Google Drive to access the dataset (assuming it's stored there)
from google.colab import drive
drive.mount('/content/drive')

# Load the dataset into a DataFrame
df = pd.read_csv('/content/drive/MyDrive/Womens Clothing E-Commerce Reviews.csv')

# Display the first few rows of the dataset for initial exploration
df.head()

# Display the columns in the dataset to understand its structure
df.columns

# Visualization of the distribution of ages using a histogram
plt.figure(figsize=(10, 6))
plt.hist(df['Age'], bins=20, color='skyblue', edgecolor='black')
plt.title('Distribution of Ages')
plt.xlabel('Age')
plt.ylabel('Frequency')
plt.show()

# Visualization of the distribution of a categorical variable (Department Name) using a bar chart
plt.figure(figsize=(12, 6))
df['Department Name'].value_counts().plot(kind='bar', color='salmon', edgecolor='black')
plt.title('Distribution of Department Names')
plt.xlabel('Department Name')
plt.ylabel('Frequency')
plt.xticks(rotation=45, ha='right')  # Rotate x-axis labels for better readability
plt.show()

# Visualization of the distribution of ratings using a bar chart
plt.figure(figsize=(8, 5))
df['Rating'].value_counts().sort_index().plot(kind='bar', color='lightgreen', edgecolor='black')
plt.title('Distribution of Ratings')
plt.xlabel('Rating')
plt.ylabel('Frequency')
plt.show()
