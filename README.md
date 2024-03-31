from matplotlib import pyplot as plt
import pandas as pd
import seaborn as sns

DATA is loan from non-profit

df = pd.read_csv('kiva_data.csv')
df.head()

df.head(25)

## Step 4: Bar Charts

# Creates the figure, note: you're only using this syntax so that you can modify the y-axis ticks later
f, ax = plt.subplots(figsize=(15, 10))
sns.barplot(data = df , x = 'country', y = 'loan_amount')


import matplotlib.ticker as mtick

# Creates the figure
f, ax = plt.subplots(figsize=(15, 10))

# Plot the data
sns.barplot(data=df, x="country", y = "loan_amount")

fmt = '${x:,.0f}'
tick = mtick.StrMethodFormatter(fmt)
ax.yaxis.set_major_formatter(tick)

# Use part of the code above to format the y-axis ticks below this line




By gender

# Creates the figure, you're only using this syntax so you can modify the y-axis ticks below
f, ax = plt.subplots(figsize=(15, 10))

sns.barplot(data=df, x="country", y="loan_amount", hue = 'gender')

fmt = '${x:,.0f}'
tick = mtick.StrMethodFormatter(fmt)
ax.yaxis.set_major_formatter(tick)

# Better style

# Set color palette
sns.set_palette('Accent')
sns.set_style('darkgrid')
# Set style


# Create figure and axes (no need to use the previous syntax, as the y-label ticks aren't going to be formatted)
plt.figure(figsize=(25, 15))



fmt = '${x:,.0f}'
tick = mtick.StrMethodFormatter(fmt)
ax.yaxis.set_major_formatter(tick)

# Add a title
ax.set_title('Loan given in dollar per country based on gender')

# Use Seaborn to create the bar plot
sns.barplot(data=df, x="country", y="loan_amount", hue = 'gender')


Box Plots

plt.figure(figsize=(16, 10))
sns.boxplot(data = df, x = 'country', y = 'loan_amount')
sns.set_style('dark')
sns.set_palette('Pastel1')


## By activity 
plt.figure(figsize=(16, 10))
sns.boxplot(data = df, y = 'loan_amount', x = 'activity')
sns.set_style('white')
sns.set_palette('Dark2')




## Violin plot by activity 
plt.figure(figsize=(16, 10))

sns.violinplot(data=df, x="activity", y="loan_amount")

# Violin plot by country 

plt.figure(figsize=(16, 10))
sns.violinplot(data=df, x="country", y="loan_amount")

# by country and gender
sns.set_palette("Spectral")
plt.figure(figsize=(18, 12))
sns.violinplot(data=df, x="activity", y="loan_amount", hue = 'gender', split = True)