# NHS A&E Performance Analysis

An end-to-end healthcare data analytics project analysing NHS England Accident & Emergency performance for July 2026 using Python, Pandas and Tableau.

The project explores A&E demand, four-hour performance, emergency admissions and prolonged decision-to-admit delays across NHS providers.

## Dashboard

![NHS A&E Performance Dashboard](NHS%20A%26E%20Performance%20Dashboard%20.png)

## Project Approach

I wanted this project to go beyond simply creating a dashboard. My main aim was to understand what the NHS A&E data was actually showing and make the results easier to interpret at provider level.

The key questions I wanted to answer were:

- Which Type 1 A&E providers were performing worst against the four hour standard?
- Which providers were experiencing the highest levels of 12+ hour decision to admit delays?
- Does a higher number of A&E attendances appear to result in worse four hour performance?
- How can these findings be presented in a way that someone working with healthcare data could understand quickly?

The intended audience for the dashboard is someone such as a healthcare analyst, operational manager or NHS decision maker who wants a quick overview of provider performance without having to work through the raw NHS dataset.

## Understanding the Data

Before carrying out the analysis, I explored the structure of the NHS England dataset to understand the different types of A&E activity being reported.

One thing that became important during the project was distinguishing between Type 1 A&E departments and other types of emergency care services. Type 1 departments represent major consultant led A&E services, so I decided to use these when comparing provider performance.

This made the comparison more meaningful because I was comparing similar types of emergency departments rather than combining organisations that provide very different services.

I also used the official NHS England published figures throughout the project to check that my calculations were producing sensible results.

## Process and Decisions

I started by inspecting the dataset, checking the number of rows and columns, reviewing the data types and looking for any issues that could affect the analysis.

The dataset originally contained 192 rows. I identified that one of these rows represented the national total rather than an individual provider, so I removed it from provider level comparisons.

From there, I created additional measures including:

- Total A&E attendances
- Total attendances over four hours
- Four hour performance
- Type 1 four hour performance
- Emergency admissions through A&E
- 12+ hour decision to admit delays
- A derived 12+ hour delay rate

When looking at provider performance, I focused specifically on Type 1 A&E departments. This was a deliberate choice because comparing all A&E department types together could give a misleading picture of performance.

For the 12+ hour delay analysis, I also chose to calculate a rate rather than only comparing the raw number of delays. Larger hospitals naturally admit more patients, so using a rate gave more context when comparing providers of different sizes.

I also wanted to test whether busier A&E departments automatically performed worse. Instead of assuming this was the case, I calculated the correlation between Type 1 attendance volume and four hour performance and then visualised the relationship using a scatter plot.

## Iteration and Problem Solving

One of the most useful parts of this project came from finding a mistake in my first calculation.

My initial total for A&E attendances was lower than the official NHS England figure. Instead of continuing with the analysis, I went back through the dataset to work out why the numbers were different.

I realised that I had included standard A&E attendances but had not included booked A&E appointments.

The missing booked appointments accounted for 76,165 attendances.

After adding these into the calculation, my total A&E attendance figure became 2,487,580, which matched the official NHS England figure.

I then used the same validation approach for the other main metrics. My final calculations reproduced the published figures for:

- Overall four hour performance at 75.4%
- Type 1 four hour performance at 61.7%
- Emergency admissions at 547,828
- 12+ hour decision to admit waits at 47,438

This part of the project made me realise how important validation is. A calculation can run successfully in Python and still be wrong if the underlying logic is incomplete.

## Key Findings

The analysis showed a large difference in performance between NHS providers.

University Hospitals Plymouth NHS Trust recorded the lowest Type 1 four hour performance in the dataset at approximately 37.1%.

Croydon Health Services NHS Trust recorded the highest derived 12+ hour decision to admit delay rate at approximately 58.9%.

I also tested the relationship between Type 1 attendance volume and four hour performance.

The correlation was approximately 0.055, which suggests there was almost no linear relationship between how many Type 1 patients a provider treated and its four hour performance during July 2026.

This was interesting because it showed that higher demand alone did not explain why some providers performed significantly worse than others.

## Reflection

If I developed this project further, the biggest improvement would be to move from a one month snapshot to a longer time period.

Using several months or years of data would allow me to analyse trends and identify whether poor performance was temporary or consistent.

I would also like to include additional variables such as:

- Bed occupancy
- Staffing levels
- Regional differences
- Seasonal demand
- Patient complexity

This would make it possible to investigate why performance differs between providers rather than only identifying where those differences exist.

I would also consider adding regional filters and trend charts to the Tableau dashboard so users could explore changes in performance over time.

Overall, this project helped me become more confident working through the full analytics process, from understanding and cleaning raw data to validating calculations, investigating patterns and presenting findings through Tableau.
