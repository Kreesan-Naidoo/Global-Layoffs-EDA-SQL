# SQL Exploratory Data Analysis — Global Layoffs (2020–2023)
-- Project Overview
This project performs end-to-end Exploratory Data Analysis (EDA) using MySQL on a cleaned dataset of global company layoffs between 2020 and 2023. The goal was to uncover meaningful patterns and trends across companies, industries, and time periods — answering real business questions purely through SQL.
This project is the second stage of a two-part series. The raw data was first cleaned in a separate data cleaning project before analysis began here.

-- Tools Used

MySQL — all analysis performed in SQL \
SQL techniques — Aggregations, GROUP BY, Window Functions, CTEs, DENSE_RANK(), Rolling Totals, SUBSTRING() for date parsing


--  Dataset

Source: Kaggle — Layoffs Dataset
Table used: layoffs_staging2 (cleaned dataset from the data cleaning project using the same dataset)
Period covered: March 2020 – March 2023
Key fields: Company, Industry, Country, Total Laid Off, Percentage Laid Off, Date, Stage, Funds Raised

-- Business Questions Explored

1. What are the maximum layoff figures in the dataset?
Identified the largest single layoff event and the highest percentage of a workforce cut in one round.

2. Which companies laid off their entire workforce?
Filtered for companies where percentage_laid_off = 1 (100% of staff), ordered by the total number of employees affected — highlighting which complete shutdowns were largest in scale.

3. Which companies had the highest total layoffs across the full period?
Ranked all companies by cumulative layoffs from 2020–2023 to identify the hardest-hit organisations overall.

4. What was the date range of the data?
Confirmed the full period covered by the dataset to contextualise all time-based analysis.


5. Which industries were most affected?
Aggregated total layoffs by industry to identify which sectors experienced the most significant workforce reductions.

6. How did layoffs trend year over year?
Broke down total layoffs by year to understand how the volume of cuts evolved from 2020 through 2023.

7. What was the rolling monthly total of layoffs?
Built a rolling (cumulative) total of layoffs by month using a CTE and SUM() OVER() window function — showing how the cumulative impact grew over time.



8. Which companies had the highest layoffs per year? (Top 5 per year)
Used double nested CTEs combined with DENSE_RANK() to rank companies by total layoffs within each calendar year — surfacing the top 5 hardest-hit companies for each year from 2020 to 2023.



-- Key Findings

The dataset spans March 2020 to March 2023, covering the COVID-19 period through the post-pandemic tech correction
Several companies laid off 100% of their workforce, indicating full shutdowns rather than cost-cutting measures
The Consumer and Retail industries were among the hardest hit by total headcount reductions
Layoffs accelerated significantly in 2022 and early 2023 following a relatively quieter 2021 — visible in the rolling monthly totals
A small number of large tech companies account for a disproportionately high share of total layoffs when ranked by year


-- Related Project :
This EDA was performed on data cleaned in Part 1 of this series.
 View the Data Cleaning Project on the same data set : SQL data cleaning project layoffs
