Pakistan Flight Data Analysis Project
📘 Overview:

This project analyzes domestic flight data in Pakistan to explore trends in flight frequency, ticket prices, delays, and airline performance.
It includes data cleaning, exploratory data analysis (EDA), and visualization using Python (Pandas, Matplotlib, Seaborn) and can also be explored in Excel or Power BI.

📂 Dataset:

File: pakistan_flight_data_final.csv
Rows: 1500 flights
Columns :

Flight_ID
Airline
Source_Airport
Destination_Airport
Departure_Time
Arrival_Time
Departure_Period (Morning / Afternoon / Evening / Night)
Arrival_Period
Duration_Minutes
Distance_KM
Ticket_Price_PKR
Delay_Minutes
Status (On-Time / Delayed / Cancelled)

1️⃣ Data Cleaning:

Tasks performed:

Removed missing values and duplicate rows

Fixed inconsistent entries

Saved cleaned dataset as pakistan_flight_data_cleaned.csv

Code example:

df.dropna(inplace=True)
df.drop_duplicates(inplace=True)
df.to_csv('pakistan_flight_data_cleaned.csv', index=False)

 2️⃣ Exploratory Data Analysis (EDA):

Key insights explored:

Total flights per airline

Busiest airports (departures + arrivals)

Average flight duration and distance per airline

Common aircraft types

Ticket price distribution (min, max, mean)

Example:

df['Airline'].value_counts()
df['Ticket_Price_PKR'].describe()

 3️⃣ Flight Timing & Delay Analysis:

Analyzed how flight delays vary with time of day and airline:

df.groupby('Departure_Period')['Delay_Minutes'].mean()
df.groupby('Airline')['Delay_Minutes'].mean()

📊4️⃣ Visualizations:

Created visual insights using Matplotlib and Seaborn.

Chart	Description
Bar Chart	Flights per airline
Pie Chart	Flight status distribution
Bar Chart	Average delay per airline
Histogram	Ticket price distribution
Heatmap	Departure period vs status

Example:

import seaborn as sns
sns.heatmap(pd.crosstab(df['Departure_Period'], df['Status']), annot=True, cmap='Blues')

Insights:

Morning flights are usually more punctual.

Night flights show higher average delays.

AirBlue and PIA handle the majority of flights.

Ticket prices vary widely depending on distance and airline.

Tools & Libraries:

Python: Pandas, Matplotlib, Seaborn
