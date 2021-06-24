# The Duration of Life Insurer's Liabilities

![public companies durations](</misc/Stock Market Equity Dura.png>)

This repository hosts the estimated duration of the liabilities of U.S. life insurance companies. The data is available from **2001** to **2021**, for a cross-section of about **900 individual companies** and **aggregated**.

The [individual company data](/data/liability_duration.csv) is indexed by the `year` of the annual statement and the NAIC company number `NAIC_no`. The estimated actuarial value of the liabilities is `Value_L` and the estimated duration is `D_L`. The statutory value of liabilities is `Reserve_L` which agrees with the sum of gross totals of reserves. The [aggregated data](/data/liability_duration_agg.csv) does not have the `NAIC_no` column.

# Procedure

![Exhibit 5](</misc/ex5.png>)

The `reserve values` are taken from the "EXHIBIT 5 - AGGREGATE RESERVE FOR LIFE CONTRACTS" of the annual statements of U.S. life insurance companies. Each row reflects the present value of a class of liabilities that was issued in the past. Discounting uses a `reserve rate` and the future `reserve benefits` that will be paid out are calculated using a conservative mortality table, e.g. `1983 Table A` or `1993 GAR`:

<center>
![Reserve](</misc/value.gif>)
</center>

Observing the evolution of the `reserve values` from one annual statement to the next implies the `reserve benefits`. For the purposes of calculating the actuarial value and duration of a liability, the `reserve benefits` are a good approximation of the true benefits, at least for the most popular annuity and life insurance policies. 

An empirical model of `reserve benefits` is estimated and the resulting predictions are used to calculate the actuarial value and duration of each reserve position. These are aggregated yearly to the individual company level. There is substantial cross-sectional heterogeneity in the duration of liabilities and the industry-wide average shows an increasing time trend:

![Exhibit 5](</misc/Duration Liabilities.png>)
