# hate-crime-data
Analysis of FBI data on hate crime in America. See [Medium article](https://nlp-andrew.medium.com/analyzing-data-on-hate-crimes-in-america-from-1991-to-2019-4c82a4aa0b48) for full writeup.

* datasets/hate_crime.csv

The source data on hate crimes numbers. Originally from [here](https://crime-data-explorer.fr.cloud.gov/downloads-and-docs) by scrolling down and clicking on Hate Crime to download hate_crime.zip. The most recent dataset only goes up to 2019. The 2020 data will probably be released around November 2021.

* datasets/demographics.csv

It was much harder to get annual population data for all these groups. For race and ethnicity, my primary source was the US Census. The White category in the census includes Hispanic and Arab populations, which are treated as separate groups in the hate crime dataset, so I subtracted those population numbers from the White census population. Because the census only occurs every 10 years, I interpolated population figures for the intervening years assuming a perfectly smooth increase within the decade.

Other fine-grained population figures such as relgion, gender, and sexuality were much harder to find. In the end, I looked for a source that listed 2019 levels, and simply assumed that that proportion is constant. This is certainly not true in reality, but allowed me to calculate the numbers based simply on populations levels each year for the US as a whole.

Also, I could not find any good numbers on the number of people with physical disabilities vs. people with mental disabilities, so I just took the total number of disabled people and assigned half of the population to each group.

I would welcome anyone who could point me to a higher quality population dataset.

* datasets/victimization_raw_numbers.csv
* datasets/victimization_rates.csv

Generated by process_and_graph.ipynb, based on the two csv files mentioned above. Contains the absolute numbers and the per capita rates (per million).
