# assignment_5_1

This repo is my submission for Assignment 5.1 for UC Berkeley's [Professional Certificate in Machine Learning and Artificial Intelligence](https://em-executive.berkeley.edu/professional-certificate-machine-learning-artificial-intelligence) program.

#### Jupyter Notebook
Here is the link to the [Jupyter Notebook](./prompt.ipynb) with the analysis for this dataset.

## The Assignment

We were given a dataset from the UCI Machine Learning repository that was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios including the destination, current time, weather, passenger, etc., as well as different driver characteristics, and asks if the person would accept the coupon presented to them.

There were 5 different types of coupons:
- Bar
- Carry out & Take away
- Coffee House
- Restaurants(<20) - cheaper restaurants less than $20
- Restaurants(20-50) - restaurants from $20-50

The assignment was to produce a brief report highlighting the scenarios and characteristics of the drivers who accept the coupon for _one of the coupon types_. I chose the _Carry out & Take away_ coupon type because it had the highest acceptance rate compared to the other coupon types at 73%.

_**Note:** In the Jupyter Notebook, I'm using Plotly instead of Seaborn for visualization, but Plotly doesn't render in Github. To mitigate this, I have called both `fig.show()` for the interactive plot and `fig.show('png')` for the static plot (which will show in Github). Furthermore, all Plotly plots are saved in the images directory._

![coupon types](./images/coupon_types.png)

## The Problem for Carry out & Take away Coupons

The problem is to find the scenarios and driver characteristics that have the highest 
## The Findings

Here is a summary of the findings. More extensive analysis and visualizations are in the Jupyter Notebook.

### Highest Acceptance Rates
The highest acceptance rates come from 15 values across 5 categories:
- occupation (9 out of 15 values are specific occupations)
  - Building & Grounds Cleaning & Maintenance
  - Protective Service
  - Construction & Extraction
  - Healthcare Practitioners & Technical
  - Healthcare Support
  - Food Preparation & Serving Related
  - Business & Financial
  - Transportation & Material Moving
  - Farming Fishing & Forestry
- education = 'Some High School' and 'Associates degree'
- widows
- time of day = 2PM and 6PM (this makes sense that people would say no to a coupon while on the way to work in the morning)
- people who _never_ go to cheap restaurants (these seem to prefer to take away food to eat at home instead)

![highest acceptance rates_plot](./images/highest_acceptance_rates_plot.png)

**Highest Acceptance Rates**
![highest acceptance rates](./images/highest_acceptance_rates.png)

### Lowest Acceptance Rates

On the other hand, the lowest acceptance rates are much more spread out across categories. For the lowest acceptance rates, there are 16 values across 11 categories.
The following scenarios and characteristics result in the lowest acceptance rates:
- occupation
  - Life Physical Social Science
  - Legal
  - Installation Maintenance & Repair
  - Architecture & Engineering
  - Arts Design Entertainment Sports & Media
  - Student
- visit frequencies
  - Bar - people who go to bars more than 8 times a month
  - Coffee House - people who go to Coffee House more than 8 times a month
  - Carry Away - people who carry away less than once a month (this tells us that they are not interested in Carry Away)
  - Restaurants - people who go to restaurants more than 8 times a month
- weather - rainy weather
- education = people with graduate degrees
- time of day = 7AM and destination = Work correspond with people who are going to work
- income level of $75000 - $87499 - which is the 3rd highest income level is 5% less likely than the next income level
- 2-hour expiration - shorter expiration (instead of 1-day) is not conducive to acceptance.
![lowest acceptance rates_plot](./images/lowest_acceptance_rates_plot.png)

**Lowest Acceptance Rates**
![lowest acceptance rates](./images/lowest_acceptance_rates.png)

### Next Steps and Recommendations
For the next steps, I recommend to do similar analyses for the other coupon types and then compare acceptance rates across coupon types, categories, and their values.
Doing so would enable the different types of establishments associated with the various coupon types to understand the best way to target coupons campaigns. The acceptance rate for a certain audience can also help with pricing of the service, informing both supply and demand of a potential digital coupon delivery service.
However, to properly choose the correct audience to show coupons to, I recommend looking at both the size of the audience in addition to the acceptance rate that we have explored above.
Furthermore, I hypothesize that rainy and cold weather, early time of day (7AM), people heading to work, and short-term expirations (2-hour) would all result in low acceptance rates across all coupon types, and can therefore be avoided with the coupon service.
In terms of weather, locality should be considered because what is cold in one location may not be cold for another location.



