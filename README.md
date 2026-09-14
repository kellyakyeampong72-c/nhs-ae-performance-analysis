# NHS A&E Performance Analysis

An end-to-end healthcare data analytics project analysing NHS England Accident & Emergency performance for July 2026 using Python, Pandas and Tableau.

The project explores A&E demand, four-hour performance, emergency admissions and prolonged decision-to-admit delays across NHS providers.

## Dashboard

![NHS A&E Performance Dashboard](NHS%20A%26E%20Performance%20Dashboard%20.png)

## Project Objectives

The analysis aimed to investigate:

- How NHS providers performed against the four-hour A&E standard
- Which major Type 1 A&E providers had the lowest four-hour performance
- Which providers experienced the highest rates of 12+ hour decision-to-admit delays
- Whether higher Type 1 A&E demand was associated with poorer four-hour performance
- How provider-level performance could be communicated through an interactive Tableau dashboard

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Google Colab
- Tableau
- GitHub

## Data Preparation

The original NHS England provider-level dataset contained 192 rows and 22 columns.

The cleaning and preparation process included:

- Inspecting column names, data types and missing values
- Identifying and removing the national `Total` summary row from provider-level comparisons
- Checking for duplicate organisation codes
- Calculating total A&E attendances across department types and booked appointments
- Calculating attendances completed within and over four hours
- Creating overall and Type 1 four-hour performance measures
- Calculating total emergency admissions
- Combining decision-to-admit delay categories
- Creating a derived 12+ hour DTA delay rate
- Filtering providers with no relevant A&E activity from specific comparisons

## Validation

Calculated metrics were checked against published NHS England figures to confirm the transformations were correct.

Key validated totals included:

- **Total A&E attendances:** 2,487,580
- **Overall four-hour performance:** 75.4%
- **Type 1 four-hour performance:** 61.7%
- **Emergency admissions:** 547,828
- **12+ hour decision-to-admit waits:** 47,438

During validation, an initial attendance total was found to exclude booked A&E appointments. Investigating the discrepancy identified 76,165 booked appointments, which were then incorporated into the final calculation.

## Key Findings

### Four-Hour Performance

No reporting Type 1 provider achieved the 95% four-hour operational standard during July 2026.

University Hospitals Plymouth NHS Trust recorded the lowest Type 1 performance in the analysis at approximately **37.1%**.

### Decision-to-Admit Delays

Croydon Health Services NHS Trust recorded the highest derived 12+ hour DTA delay rate at approximately **58.9%**.

This rate was calculated as the number of 12+ hour decision-to-admit waits relative to emergency admissions via A&E and is used here as a comparative analytical measure rather than an official NHS performance metric.

### Demand vs Performance

The correlation between Type 1 attendance volume and four-hour performance was approximately **0.055**.

This indicates very little linear relationship between provider attendance volume and four-hour performance in the July 2026 snapshot. Higher patient volumes alone therefore did not explain differences in provider performance.

## Tableau Dashboard

The Tableau dashboard presents:

- Total A&E attendance
- Overall four-hour performance
- Type 1 four-hour performance
- 12+ hour decision-to-admit waits
- Emergency admissions
- Lowest-performing Type 1 providers
- Highest derived 12+ hour DTA delay rates
- Type 1 demand versus four-hour performance

The packaged Tableau workbook is available here:

[Download the Tableau workbook](NHS%20A%26E%20performance%20dashboard.twbx)

## Python Analysis

The complete Python analysis and data preparation workflow can be viewed here:

[View the Jupyter notebook](NHS_AE_July_2026.ipynb)

## Data Source

NHS England  
A&E Attendances and Emergency Admissions  
July 2026

## Skills Demonstrated

This project demonstrates practical experience in:

- Healthcare data analysis
- Data cleaning and validation
- Pandas data manipulation
- Feature engineering and calculated KPIs
- Exploratory data analysis
- Correlation analysis
- Data visualisation
- Tableau dashboard development
- Communicating analytical findings
