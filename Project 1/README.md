# Project 1: SAT & ACT Analysis 

## Introduction 
The SAT and ACT generally cover the same topics. Both ACT and SAT scores are used for college admissions decisions and awarding merit-based scholarships. Most colleges do not prefer one test over the other. Neither the SAT or ACT is harder than the other. Different students tend to do better on one test over the other.

In the past, ACT and SAT are a US high-schoolers rites of passage to college. However, in recent years, a large number of colleges have announced that they no longer require ACT/SAT scores for admissions. As the CEO of RoJAk Data Consultancy, I do see this as an opportunity for a moderated act. Therefore, before I propose the ways in which RoJAk Data Consultancy can help, I would first examine how various macro-social factors can affect ACT performances among high-schoolers (i.e., problem statement).

In this project, I have included several datasets to set the ground for discussion:

1. The set of ACT datasets (2017-2019) contains the participation rate by state, the average scores for each subject (e.g., English, Math, Reading, and Science), and the composite scores. This dataset also includes data at the national level in terms of participation rate, average scores, and composite scores.

2. The set of SAT datasets (2017-2019) contains various data for each state in the U.S. Information provided includes participation rate by state, average scores on the Evidence-Based Reading & Writing and Math sections, and the total scores. The Evidence-Based Reading & Writing section consists of the reading sub-test and writing and language sub-test, while the Math section consists of the no-calculator sub-test and calculator sub-test.

- Note: Even though the problem statement focuses on ACT performance, I did some exploratory analyses on SAT performance as well.

3. The other factors dataset contain the number of crime rates, GDP per cap, religiosity, political affiliation, and poverty rate, all sorted by states. The sources will be linked below in the data dictionary.


## Data Dictionary 

The features in the final data table is summarised below:

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|ACT/SAT|State names for 50 states in the US |
|act_2017_rate|float|ACT/SAT|State-wide participation rate in 2017 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|act_2017_english|float|ACT/SAT|State mean score for English in 2017 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|act_2017_math|float|ACT/SAT|State mean score for Math in 2017 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|act_2017_reading|float|ACT/SAT|State mean score for Reading in 2017 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|act_2017_science|float|ACT/SAT|State mean score for Science in 2017 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|act_2017_composite|float|ACT/SAT|State mean compsite score (average score for English, Math, Reading, and Science in 2017 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|sat_2017_rate|float|ACT/SAT|State-wide participation rate in 2017 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|sat_2017_ebrw|integer|ACT/SAT|State mean score for Evidence-Based Reading and Writing in 2017 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|sat_2017_math|integer|ACT/SAT|State mean score for Math in 2017 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|sat_2017_total|integer|ACT/SAT|State mean total (combined score for Evidence-Based Reading and Writing and Math) in 2017 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|act_2018_rate|float|ACT/SAT|State-wide participation rate in 2018 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)|
|act_2018_composite|float|ACT/SAT|State mean compsite score (average score for English, Math, Reading, and Science in 2018 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)|
|sat_2018_rate|float|ACT/SAT|State-wide participation rate in 2018 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|sat_2018_ebrw|integer|ACT/SAT|State mean score for Evidence-Based Reading and Writing in 2018 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|sat_2018_math|integer|ACT/SAT|State mean score for Math in 2018 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|sat_2018_total|integer|ACT/SAT|State mean total (combined score for Evidence-Based Reading and Writing and Math) in 2018 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|act_2019_rate|float|ACT/SAT|State-wide participation rate in 2019 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)|
|act_2019_composite|float|ACT/SAT|State mean compsite score (average score for English, Math, Reading, and Science in 2019 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)|
|sat_2019_rate|float|ACT/SAT|State-wide participation rate in 2019 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|sat_2019_ebrw|integer|ACT/SAT|State mean score for Evidence-Based Reading and Writing in 2019 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|sat_2019_math|integer|ACT/SAT|State mean score for Math in 2019 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|sat_2019_total|integer|ACT/SAT|State mean total (combined score for Evidence-Based Reading and Writing and Math) in 2019 - [Source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)| 
|cr_17|float|Others|State violent crime rates in 2017 - [Source](https://www.wikiwand.com/en/List_of_U.S._states_and_territories_by_violent_crime_rate)| 
|cr_18|float|Others|State violent crime rates in 2018 - [Source](https://www.wikiwand.com/en/List_of_U.S._states_and_territories_by_violent_crime_rate)| 
|cr_19|float|Others|State violent crime rates in 2019 - [Source](https://www.wikiwand.com/en/List_of_U.S._states_and_territories_by_violent_crime_rate)| 
|cr_20|float|Others|State violent crime rates in 2020 - [Source](https://www.wikiwand.com/en/List_of_U.S._states_and_territories_by_violent_crime_rate)| 
|rep_lean|float|Others|Proportion of surveyed state residents expressing inclination towards Republican Party - [Source](https://www.pewresearch.org/religion/religious-landscape-study/compare/party-affiliation/by/state/)| 
|dem_lean|float|Others|Proportion of surveyed state residents expressing inclination towards Democrat Party - [Source](https://www.pewresearch.org/religion/religious-landscape-study/compare/party-affiliation/by/state/)| 
|nominalgdp_percapita_20|float|Others|State GDP per capita for 2020 in Nominal USD - [Source](https://www.bea.gov/data/gdp/gdp-state)| 
|v_religious|float|Others|Proportion of surveyed residents idenitfying as "very religious" - [Source](https://www.statista.com/statistics/221454/share-of-religious-americans-by-state/)| 
|moderately_religious|float|Others|Proportion of surveyed residents idenitfying as "moderately religious" - [Source](https://www.statista.com/statistics/221454/share-of-religious-americans-by-state/)| 
|religious|float|Others|Proportion of surveyed residents idenitfying as "very religious" or "moderately religious" - [Source](https://www.statista.com/statistics/221454/share-of-religious-americans-by-state/)| 
|poverty_rate|float|Others|Proportion of residents living below the national poverty level - [Source](https://www.statista.com/statistics/233093/us-poverty-rate-by-state/)| 
|burglary_per_100K|float|Others|Proportion of state burglary rates in 2018 - [Source](https://www.worldatlas.com/articles/the-most-burglaries-in-the-us.html)| 

## Key takeaways
From the analyses, we can see that macro factors do affect ACT performance. 

Specifically, these are the ways in which individual macro factors affect one's ACT performance.
- The higher the crime rates, the lower one scores on the ACT
- The higher the burglary rates, the lower one scores on the ACT
- The higher the poverty rate in a state, the lower one scores on the ACT
- The higher the nominal GDP, the higher one scores on the ACT
- The more religious a state is, the lower one scores on the ACT
- The more one identifies as a Republican, the lower one scores on the ACT
- The more one identifies as a Democrat, the higher one scores on the ACT


## Conclusions and recommendations 

Based on the above analyses, we can see that macro factors do affect ACT performance in one way or another.

Here is a quick recap to see how each individual macro factors affect one's ACT performance.

The higher the crime rates, the lower one scores on the ACT
The higher the burglary rates, the lower one scores on the ACT
The higher the poverty rate in a state, the lower one scores on the ACT
The higher the nominal GDP, the higher one scores on the ACT
The more religious a state is, the lower one scores on the ACT
The more one identifies as a Republican, the lower one scores on the ACT
The more one identifies as a Democrat, the higher one scores on the ACT

The team at RoJAk Data Consultancy feels that these macro factors should be taken into consideration when evaluating if one should be given college admission. However, it is definitely not a one man effort. We propose that if you would like to engage in our services, we will work with the following stakeholders and institutions to help the future generations.

1. ACT level
- Rebrand to shed image as a classist standardised test
- Revamp ACT scoring system

2. State/National level
- Provide insights to influence national/state politics and resource allocation to improve quality of education

3. College level
- Review admission criteria to be more inclusive
- Partner with other colleges to adopt new ACT scoring system

Moreover, here are some of our future work we plan to do in order to encompass a more holistic approach. We plan to collect more data at the county or district level, look at other macro factors (e.g., student access to education), consider how it affects private vs public schools, and to consider state education budgets.


