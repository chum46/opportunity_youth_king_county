# Table of Contents

[Files and Folders of Note](link)

[Context of Project](link)

[Preview of Results](link)

[Data](link)

[Process](link)

[Results](link)

[Strengths and Limitations](link)

[Real World Application](link)


# Files and Folders of Note
├── README.md
├── environment.yml
├── notebooks
│   ├── exploratory
│   │   ├── 01_erh_download_and_explore_data.ipynb
│   │   ├── 02_cm_download_and_explore_data.ipynb
│   │   ├── 03_mc_download_and_explore_data.ipynb
│   │   ├── 04_ar_download_and_explore_data.ipynb
│   │   ├── 05_ar_map_visualization.ipynb
│   │   ├── 06_mc_oy_estimate_viz.ipynb
│   │   ├── 07_cm_trend_table_viz.ipynb
│   └── report
│       ├── 08_all_final_summary.ipynb
├── references
├── reports
│   ├── figures
│   │   ├── oy_by_age.png
│   │   ├── oy_by_puma.png
│   │   └── percent_oy_by_puma.png
│   └── presentation.pdf
├── src
│   ├── data
│   ├── mc_functions.py
│   └── requirements
│       └── install.sh
└── windows.yml


# Context of Project

Our project task was to update The Seattle Region Partnership (SRP) on the current estimate of Opportunity Youth in South King County. Furthermore, we were to investigate deeper into the status of Opportunity Youth within South King County such as the total amount in each PUMA code, a breakdown of Opportunity Youth status by age, and also provide a comparison to the previous report.

For the purposes of our analysis, we defined Opportunity Youth as any individual between the ages of 16 and 24 who is not in school and not in the labor force or unemployed. We also defined King County to be the area with PUMA codes 11601-11616 and South King County to be a subset of that area, with PUMA codes 11610-11614.


#### Source 2017 5-year American Community Survey (ACS) Public Use Microdata Survey (PUMS).

 - Definition of opportunity youth (16-to 24-year-olds not in school and not working)
 - South King County includes pumas 11610 to 11615
 - Throughout the notebook "Opportunity Youth" may be abbreviated as "OY"


# Preview of Results

The primary purpose of our analysis was to estimate the number of individuals considered to be Opportunity Youth within South King County, which we found to be 9,404. Furthermore, we were to provide a breakdown of the number of Opportunity Youth within each PUMA code of South King County.

![](figures/oy_by_puma.png)

This graph shows the number of Opportunity Youth within each PUMA code of King County. The areas in South King County are highlighted. As you can see from the visualization, the areas designated as South King County have more Opportunity Youth than any other part of King County.

Looking at the segmented age groups within the opportunity youth population, we can see some trends over time in the education level. 

![](figures/oy_by_age.png)

We can see that within the 22-24 age group there was a significant dropoff in the number of degreed Opportunity Youth. This could mean that more grads are being hired into the workforce, or less youth are going into higher education. When you look at the 19-21 age group, you see an increase in the amount of OY that have a HS diploma or GED, and a shrinking population of those with some college credits. We can possible deduce that less Youth are taking the next step in getting higher education but we would need more data to support that. It could be that more youth are finishing degrees and getting hired into the work force. Further investigation can be done to confirm this by seeing if the general population in these regions have seen any changes that support this assumption.

# Data
The dataset provided to us was the ACS 2013-2017 5-Year PUMS file containing a sampling of five percent of the population of Washington. This dataset provided extensive information on the individuals surveyed. For the purposes of our analysis, we only utilized a small portion of this data. 

Using our definition of Opportunity Youth from above, we required information on the individuals’ age, PUMA code, school status, work status, and corresponding weight of that observation in order to get an accurate estimate of total number of Opportunity Youth. We also utilized the column for educational attainment that gave the highest level of schooling the given individual obtained. The names of those columns are as follows:

- Age of individual: ‘agep’
- PUMA (Public Use Microdata Area) Code: ‘puma’
- School status: ‘sch’
- Educational attainment: ‘schl’
- Work status: ‘esr’
- Weight of observation: ‘pwgtp’

# Process
Utilizing the python programming language along with the pandas library and SQLite we had isolated the columns we wished to use to help identify the opportunity youth of southern king county. This included people between the age of 16 - 24 who are not in any form of schooling and are not in the labor force or are unemployed who reside in the PUMA’s (Public Use Microdata Areas) of 11610 - 11614. Once This group was isolated from the rest of the ACS 2013-2017 dataset the columns were further divided in order to look into specific topics such as the educational attainment or employment statuses of opportunity youths. To find trends in the data the python libraries matplotlib and seaborn were used to make graphical visualizations to help illustrate the data to better understand its trends. 

# Results

The first step of our analysis was to provide an estimate of the number of Opportunity Youth within South King County, as well as the number of Opportunity Youth within each PUMA code of South King County. To give some context, we wanted to show the number of Opportunity Youth within each PUMA of King County so we could compare South King County to the rest.

By utilizing the columns listed above, we estimate that there are a total of 9,404 Opportunity Youth within South King County.

![](figures/oy_by_puma.png)

As you can see from the plot above, the PUMA codes in South King County have a higher number of Opportunity Youth than any other area in King County. Our first thought was that the population of those ages 16-24 may be higher in these areas. Since the population was not consistent across PUMA codes, we decided to plot a relative measurement instead, the percentage of the population ages 16-24 who are considered Opportunity Youth.

![](figures/percent_oy_by_puma.png)

This representation breeds the same result. The PUMA codes in South King County have the highest percentage of Opportunity Youth among the 16-24 year old population.

# Application

According to an article from the Aspen Institute, “one estimate places the personal and public costs of not changing the trajectories of opportunity youth at $6.3 trillion dollars over the lifetimes of all current opportunity youth” (Aspen Institute). The barriers preventing these individuals from reconnecting with society represent a massive economic burden on society as a whole. Removing the barriers for these individuals and helping them get reconnected with our societal structure will greatly benefit both local economies and the national economy.

Our analysis provides a basis for where relief efforts should be targeted. We found the areas within King County to have the highest number of Opportunity Youth and therefore are the areas we should most invest in. 

The next steps of our project would be to identify the specific barriers that Opportunity Youth are facing. For example, the availability of transportation so they can travel to work or the presence of an authority figure to help guide them. This information could provide great insight into what strategies and policies would best get Opportunity Youth reconnected with society.
