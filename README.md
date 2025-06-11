# AtliQ Grands: Hospitality Revenue Insights Dashboard

## Project Overview

AtliQ Grands, a prestigious chain of five-star hotels across India with a 20-year legacy in the hospitality industry, has been experiencing a decline in market share and revenue within the luxury/business hotel category. This downturn is attributed to strategic moves by competitors and ineffective management decision-making. To counteract this trend and regain their market position, the managing director of AtliQ Grands decided to integrate "Business and Data Intelligence" into their operations. Lacking an in-house data analytics team, they opted to engage a third-party service provider to extract insights from their historical data.

## Project Goal

As the data analyst for this project, the primary objectives were:
* To generate revenue insights for AtliQ Grands through a **Power BI dashboard**.
* To create specific metrics as outlined in a provided metric list.
* To design a dashboard that aligns with stakeholder mock-ups, showcasing **Key Performance Indicators (KPIs)**, trends, and filters.
* To develop relevant insights that extend beyond the initial metric list and mock-up.
* To understand the **end-to-end execution of a data analytics project**, from requirement gathering to solution design and stakeholder feedback.

## Data Sources

The project utilized a dataset mimicking real-life hospitality scenarios, provided as several CSV files:
* **Hotels Data**: Information on hotel locations (e.g., Delhi, Mumbai), property names, and types (business, luxury).
* **Room Types Data**: Codes (e.g., `rt1`, `rt2`) and their corresponding meanings for different room types.
* **Dates Data**: A comprehensive date table with date, month, year, and an initial flag for weekend/weekday, critical for hospitality analysis.
* **Bookings Data (Fact Bookings)**: Fine-grained transactional data including check-in/out dates, number of guests, room type, booking platform (direct or online), and generated/realized revenue.
* **Aggregated Bookings Data**: Derived from fact bookings, providing total successful bookings versus capacity for a given property ID and check-in date.

## Key Business Concepts & Metrics

The dashboard incorporates several vital hospitality industry metrics:
* **Revenue**: Total money generated.
* **Occupancy Percentage**: Total successful bookings divided by total capacity (considering "out-of-order" rooms).
* **RevPar (Revenue Per Available Room)**: Total revenue divided by total rooms available to sell, also calculated as ADR x Occupancy.
* **ADR (Average Daily Rate)**: The average rate at which rooms were sold.
* **DSRN (Daily Sellable Room Nights)**: The number of rooms available to sell on a daily basis, helping identify issues like room blocking or maintenance.
* **Realization Percentage**: Utilized Room Nights (URN) divided by Booked Room Nights (BRN), indicating how many bookings actually resulted in stays, excluding no-shows and cancellations from top-line revenue.
* **Weekday vs. Weekend Split**: Crucially, weekends are defined as Friday and Saturday in the hotel business, while Sunday to Thursday are weekdays. This split differentiates business hotels from leisure hotels.

## Data Analytics Project Execution (Step-by-Step)

The project followed a structured, industry-standard approach:

### 1. Problem Statement & Requirement Gathering:
* Initial problem statement defined AtliQ Grands' challenge.
* Discussions with a revenue manager (Abhishek Anand from OYO Rooms) were conducted to understand specific business needs and review an initial dashboard mockup.
* Key top-level metrics like RevPar, ADR, DSRN, and Realization were identified as crucial.
* The need for weekly/monthly trends and channel-level splits was emphasized for data movement analysis and decision-making.

### 2. Data Transformation (Power Query):
* Raw CSV data was imported into Power BI's Power Query Editor for cleaning and transformation.
* Steps included connecting to the data folder, expanding individual files, promoting headers, and renaming tables.
* The traditional "weekend" definition (Saturday/Sunday) in the `dim_date` table was removed, as the hospitality domain defines weekends as Friday and Saturday.

### 3. Data Modeling (DAX):
* Relationships between tables were established using a **star schema approach**, connecting fact tables (e.g., bookings) with dimension tables (e.g., hotels, dates).
* **Calculated Columns** were created using **DAX (Data Analysis Expressions)** for custom date types (Friday/Saturday as weekend) and week numbers based on subject matter expert input.
* **Measures** were developed in DAX for key aggregated metrics like Revenue, Total Bookings, Total Capacity, Total Successful Bookings, Occupancy, RevPar, ADR, DSRN, and Realization. These measures were grouped into a dedicated "Key Measures" table for organization.

### 4. Dashboarding & Visualization:
* A detailed table was created to display property-level metrics (Revenue, Occupancy, RevPar, ADR, Average Rating).
* Interactive filters (slicers) for City, Room Type, Month, and Week Number were implemented to enable drill-down analysis.
* **KPI cards** were incorporated for top-level metrics, featuring week-on-week change indicators (up/down arrows) and tooltips showing trends over time.
* **Conditional formatting** (e.g., data bars for Revenue and Rating) was used to enhance visual comparison.
* Additional visuals, such as a donut chart for occupancy percentage by room category, were created.

### 5. Stakeholder Review & Iteration:
* An 80% complete "Minimum Viable Product (MVP)" dashboard was presented to stakeholders for feedback.
* Refinements were made based on feedback, such as adjusting the order of key metrics in the weekday/weekend split view. This iterative process, combined with continuous communication and asking "why" questions ("peeling the onion" analogy), ensured the final product aligned with evolving business requirements.

### 6. Insights & Recommendations:
The dashboard enabled users to ask and answer "why" questions, moving beyond mere data presentation to actionable insights:
* **Flat Pricing Strategy**: The dashboard revealed a consistent ADR line, indicating a flat pricing strategy across hotels. This highlighted a significant opportunity for dynamic pricing or at least weekday/weekend differential pricing, especially during holiday seasons where price fluctuations are expected. Even basic weekday/weekend pricing differences were negligible, indicating untapped revenue potential.
* **Performance Correlation**: A strong correlation between low occupancy, low average rating, and high cancellation rates was observed, particularly for underperforming hotels (e.g., AtliQ Grands Bangalore). This emphasized the critical importance of service quality and online content accuracy.
* **Channel Optimization**: While outright differential pricing across various third-party channels is not advisable (due to bots scraping prices), hotels can use promotions or added benefits (e.g., discount coupons on their own website, complimentary services) to drive direct bookings without impacting channel rankings.
* **Pareto Principle Application**: The project highlighted the Pareto Principle (80/20 rule), emphasizing that focusing on the bottom 20% of underperforming hotels can lead to significant overall business improvement, as addressing low occupancy and ratings in these specific properties can yield substantial results.

## Power BI Features Utilized

* **Power Query Editor**: For data extraction, cleaning, and transformation.
* **DAX (Data Analysis Expressions)**: For creating calculated columns and measures to derive new insights and aggregate data.
* **Data Modeling (Star Schema)**: Establishing relationships between fact and dimension tables for effective data analysis.
* **Various Visuals**: Cards for KPIs, Tables for detailed data, Slicers for interactive filtering, Line Charts for trends, and Donut Charts for part-to-whole analysis.
* **Conditional Formatting**: Applying visual rules (e.g., data bars, icons) based on data values.
* **Tooltips**: Creating custom tooltips for enhanced hover-over insights.
