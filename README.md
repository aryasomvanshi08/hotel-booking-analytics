# Hotel Booking Demand & Cancellation Analytics — Project Notes

## 1. Project Overview

This project analyzes hotel booking data to understand booking patterns, customer behavior, and cancellation trends.

The main goal is to clean the hotel booking dataset and perform Exploratory Data Analysis (EDA) to identify useful patterns and business insights.

The project focuses on:

- Hotel booking cancellations
- Booking lead time
- Hotel type
- Market segments
- Deposit types
- Cancellation trends over time
- Business recommendations based on the analysis

The project stops at **data cleaning and EDA**.

---

# 2. Project Goal

The main business question is:

> What patterns can be found in hotel bookings and cancellations, and how can these patterns help hotels better understand cancellation risk?

The analysis is descriptive. It identifies relationships and patterns in the data but does not prove that one factor causes another.

---

# 3. Dataset

The project uses hotel reservation data containing information about:

- Hotel type
- Cancellation status
- Lead time
- Arrival date
- Length of stay
- Number of guests
- Market segment
- Distribution channel
- Customer type
- Deposit type
- Average Daily Rate (ADR)
- Previous cancellations
- Special requests

After data cleaning:

- Total bookings: **87,222**
- Total columns: **34**

---

# 4. Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- Git
- GitHub

---

# 5. Project Structure

```text
hotel-booking-analytics/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── images/
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   └── 02_eda.ipynb
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

# 6. Project Workflow

## Step 1: Data Cleaning

The raw hotel booking dataset was inspected and prepared for analysis.

The cleaning process included:

- Checking the dataset structure
- Checking data types
- Identifying missing values
- Handling invalid values
- Creating useful variables
- Preparing the final dataset for analysis

The cleaned data was then used for Exploratory Data Analysis.

Notebook:

```text
notebooks/01_data_cleaning.ipynb
```

---

# 7. Exploratory Data Analysis

The second notebook focuses on understanding cancellation behavior and booking patterns.

The analysis includes:

- Overall cancellation rate
- Cancellation rate by hotel type
- Cancellation rate by lead time
- Cancellation rate by market segment
- Cancellation rate by deposit type
- Cancellation rate over time

Notebook:

```text
notebooks/02_eda.ipynb
```

---

# 8. Overall Cancellation Rate

![Overall Cancellation Rate](image/booking_cancellation_status.png)

The overall cancellation rate is:

**27.53%**

Out of 87,222 bookings:

- 63,213 bookings were not canceled
- 24,009 bookings were canceled

This means approximately **1 out of every 4 bookings was canceled**.

### Business Meaning

Cancellations represent a significant part of the booking activity.

Hotels should consider expected cancellations when planning room availability and future occupancy.

---

# 9. Cancellation Rate by Hotel Type

![Cancellation Rate by Hotel Type](image/cancellation_by_hotel.png)

Cancellation rates differ between City Hotels and Resort Hotels.

| Hotel Type   | Cancellation Rate |
| ------------ | ----------------: |
| City Hotel   |            30.10% |
| Resort Hotel |            23.49% |

City Hotels had a higher cancellation rate than Resort Hotels.

The difference is approximately **6.6 percentage points**.

### Business Meaning

City Hotel bookings show a higher cancellation rate in this dataset.

This does not mean that hotel type causes cancellations. It only shows that cancellation behavior differs between the two hotel types.

### Recommendation

Hotels could monitor City Hotel cancellations separately and investigate which customer groups or booking channels contribute most to these cancellations.

---

# 10. Cancellation Rate by Lead Time

![Cancellation Rate by Lead Time](image/cancellation_by_lead_time.png)

Lead time means the number of days between the booking date and the arrival date.

The analysis shows that cancellation rates increase as lead time increases.

| Lead Time   | Cancellation Rate |
| ----------- | ----------------: |
| 0–7 days    |             8.42% |
| 8–30 days   |            25.39% |
| 31–90 days  |            32.04% |
| 91–180 days |            35.01% |
| 181+ days   |            39.74% |

Bookings made more than 181 days in advance had the highest cancellation rate:

**39.74%**

Bookings made within 7 days had the lowest cancellation rate:

**8.42%**

### Business Meaning

Longer lead-time bookings are associated with higher cancellation rates.

### Recommendation

Hotels could:

- Monitor bookings made far in advance
- Send confirmation reminders
- Consider expected cancellations when forecasting occupancy
- Monitor future room availability carefully

---

# 11. Cancellation Rate by Market Segment

![Cancellation Rate by Market Segment](image/cancellation_by_market_segment.png)

Online Travel Agency (Online TA) was the largest market segment.

Online TA had:

- **51,550 bookings**
- **35.39% cancellation rate**

The major market segments were:

| Market Segment | Cancellation Rate |
| -------------- | ----------------: |
| Online TA      |            35.39% |
| Groups         |            27.07% |
| Aviation       |            19.91% |
| Offline TA/TO  |            14.85% |
| Direct         |            14.75% |
| Complementary  |            12.28% |
| Corporate      |            12.13% |

The Undefined segment had a 100% cancellation rate, but it contained only 2 bookings.

Because the number of bookings is extremely small, this is not considered a meaningful pattern.

### Business Meaning

Online TA is important because it has:

- A large number of bookings
- A relatively high cancellation rate

### Recommendation

Hotels could:

- Monitor OTA cancellation rates regularly
- Compare OTA bookings with direct bookings
- Track changes in OTA cancellation behavior
- Include expected OTA cancellations in occupancy planning

---

# 12. Cancellation Rate by Deposit Type

![Cancellation Rate by Deposit Type](image/cancellation_by_deposit_type.png)

Cancellation rates also differed significantly by deposit type.

| Deposit Type | Cancellation Rate |
| ------------ | ----------------: |
| Non Refund   |            94.70% |
| No Deposit   |            26.72% |
| Refundable   |            24.30% |

The Non Refund category had a cancellation rate of:

**94.70%**

### Important Observation

This is an unusually high result.

It should not immediately be treated as a final business conclusion.

The result should be investigated further to understand:

- Whether the data was recorded correctly
- Which market segments are involved
- Which booking channels are involved
- Whether the pattern is concentrated in a particular period
- Whether the deposit category has any data-related issues

### Recommendation

Investigate this pattern before making changes to hotel cancellation or deposit policies.

---

# 13. Cancellation Rate Over Time

![Cancellation Rate Over Time](image/cancellation_rate_overtime.png)

Cancellation rates vary across different months.

Some examples from the analysis are:

| Month         | Cancellation Rate |
| ------------- | ----------------: |
| November 2015 |            14.64% |
| January 2016  |            16.28% |
| June 2017     |            34.00% |
| July 2017     |            35.24% |
| August 2017   |            36.74% |

Higher cancellation rates were observed during several months in 2017 compared with some earlier periods.

### Business Meaning

Cancellation behavior changes over time.

This suggests that time-related or seasonal booking patterns may be relevant when studying cancellations.

### Recommendation

Hotels could monitor cancellation rates by month and consider historical cancellation patterns when planning future occupancy.

---

# 14. Key Findings

The main findings from the EDA are:

1. The overall cancellation rate is **27.53%**.
2. City Hotels have a higher cancellation rate than Resort Hotels.
3. Longer lead times are associated with higher cancellation rates.
4. Online TA has a relatively high cancellation rate and the largest booking volume.
5. Deposit type shows a large difference in cancellation rates.
6. Cancellation rates vary across time.

---

# 15. Business Recommendations

## Recommendation 1: Monitor Long Lead-Time Bookings

Longer lead-time bookings have higher cancellation rates.

Hotels could monitor these reservations more closely and use confirmation reminders.

---

## Recommendation 2: Monitor City Hotel Bookings

City Hotels have a higher cancellation rate than Resort Hotels.

Hotels could analyze City Hotel bookings separately to understand where the higher cancellation rate comes from.

---

## Recommendation 3: Monitor Online TA Bookings

Online TA has a large booking volume and a relatively high cancellation rate.

Hotels could regularly monitor OTA cancellation patterns and compare them with other booking channels.

---

## Recommendation 4: Investigate the Non Refund Result

The 94.70% cancellation rate for Non Refund bookings is unusual.

This result should be investigated before using it to make a business decision.

---

## Recommendation 5: Consider Cancellation Risk in Occupancy Planning

With an overall cancellation rate of 27.53%, hotels should not assume that every reservation will result in an actual stay.

Expected cancellations can be considered when planning:

- Room availability
- Occupancy
- Future demand
- Reservation monitoring

---

# 16. Important Analytical Note

The analysis identifies **relationships and patterns**, not direct causes.

For example:

> Longer lead times are associated with higher cancellation rates.

This does not mean:

> Longer lead times cause cancellations.

Further analysis would be required to establish causation.

---

# 17. Final Conclusion

The EDA shows that hotel cancellations are not evenly distributed across all bookings.

Different booking characteristics have different cancellation patterns.

The strongest findings are:

- Overall cancellation rate: **27.53%**
- City Hotel cancellation rate: **30.10%**
- Resort Hotel cancellation rate: **23.49%**
- 0–7 day lead-time cancellation rate: **8.42%**
- 181+ day lead-time cancellation rate: **39.74%**
- Online TA cancellation rate: **35.39%**
- Non Refund cancellation rate: **94.70%**

The analysis provides a better understanding of hotel booking and cancellation behavior and highlights areas where hotels could focus their cancellation monitoring and planning.

---

# 18. Notebooks

## Data Cleaning

```text
notebooks/01_data_cleaning.ipynb
```

This notebook contains the data inspection, cleaning, and preparation process.

## Exploratory Data Analysis

```text
notebooks/02_eda.ipynb
```

This notebook contains the analysis, visualizations, findings, and business recommendations.

---

# 19. Skills Demonstrated

This project demonstrates practical skills in:

- Python
- Pandas
- NumPy
- Data Cleaning
- Exploratory Data Analysis
- Data Visualization
- Statistical Comparison
- Business Insight Generation
- Business Recommendations
- Jupyter Notebook
- Git
- GitHub

---

# 20. Author

**Arya Singh**

Aspiring Data Analyst

Skills:

**Python | Pandas | NumPy | Matplotlib | Seaborn | Jupyter Notebook | Git | GitHub**
