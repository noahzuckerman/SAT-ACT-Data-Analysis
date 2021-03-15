# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Testing, Statistical Summaries and Inference

## Executive Summary

### Overview

The ACT has been outpacing the SAT in participation in recent years, steadily gaining ground across the country. The College Board implemented some major design changes to the SAT in 2016, in an attempt to revitalize their test. We've been asked by the College Board to review the last three years of SAT and ACT data to identify strategies to improve the SAT participation in future years.

### Problem Statement

This technical report reviews aggregate SAT and ACT scores and participation rates from each state in the United States in 2017,2018 and 2019 to see if we can generate any strategies the College Board might employ to increase SAT participation moving forward.

Throughout the report we'll seek to identify trends in the data and combine the data analysis with outside research to identify likely factors influencing participation rates and scores in various states. The result of this data analysis culminates in targeted strategic recommendations which have been presented to the executives of the College Board with the intent of improving statewide participation in Ohio.  


### Contents of this README

- Executive Summary
- Data-set Description
- Methodology and Analysis
- Outside Research
- Conclusions and Recommendations
- Next Steps

---

### Data-set Overview

#### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|SAT 17/18/19|The U.S. state where the test results were aggregated from|
|part_sat_*year*|float|SAT 17/18/19|The participation rate of students who took the test out of the whole student population|
|ebrw_sat_*year*|integer|SAT 17/18/19|The total score in the evidence-based reading and writing sub test section|
|math_sat_*year*|integer|SAT 17/18/19|The total score in the math sub test section|
|total_sat_*year*|integer|SAT 17/18/19|The total aggregate score of the test (sum total of the math and ebrw section)|
|state|object|ACT 17/18/19|The U.S. state where the test results were aggregated from|
|part_act_*year*|float|ACT 17/18/19|The participation rate of students who took the test out of the whole student population|
|english_act_2017|float|ACT 17|The total score in the english sub test section|
|math_act_*year*|float|ACT 17|The total score in the math sub test section|
|reading_act_*year*|float|ACT 17|The total score in the reading sub test section|
|science_act_*year*|float|ACT 17|The total score in the science sub test section|
|composite_act_*year*|float|ACT 17/18/19|The total aggregate score of the test (average of the english, math, reading and science sections)|

#### Provided Data

For this project, I've used the following six datasets as source data:

- [2017 SAT Scores](./data/sat_2017.csv)
- [2017 ACT Scores](./data/act_2017.csv)
- [2018 SAT Scores](./data/sat_2018.csv)
- [2018 ACT Scores](./data/act_2018.csv)
- [2019 SAT Scores](./data/sat_2019.csv)
- [2019 ACT Scores](./data/act_2019.csv)

You can see the sources for the SAT data [here](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/) and [here](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent), and the source for the ACT data [here](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows). The data source referenced in order to correct the data entry errors discovered in the data cleaning phase can be found [here](https://www.act.org/content/dam/act/unsecured/documents/cccr2017/ACT_2017-Average_Scores_by_State.pdf).

Additionally, I've created the following four datasets for the purpose of analysis.

- [2017 Combined Data](./data/combined_2017.csv)
- [2018 Combined Data](./data/combined_2018.csv)
- [2019 Combined Data](./data/combined_2019.csv)
- [Final Combined Data](./data/final.csv)

The Final dataset is the most relevant dataset to reference for this analysis. It includes cleansed data from both tests in all three years.

This data is compiled into CSV files which are included in the data directory of this repo.

#### Primary Findings & Insights

The ACT and SAT participation distributions roughly mirror each other, with states geographically tending to prefer one test or the other.

There are strong regional and historical affiliations associated with test preference in each state. Coastal states tend to favour the SAT, while Midwestern and Mountain states tend to favour the ACT.

ACT and SAT scores are inversely correlated with their respective participation rates. This is most likely due to selection bias.

#### Recommendations

We can apply the successful learnings from Colorado's successful SAT transition and leverage the overhauled student-accessible SAT design to gain traction amongst Ohio school districts for their future decision making. Ohio has a large amount of potential to improve SAT participation rates (<80%) and has already displayed the propensity to improve participation rates significantly in a short time frame (25% in 1 year).

#### Next Steps

Moving onto the next phase of this analysis would require additional resources and data. In order to properly strategize our campaign in Ohio, it will be critical to get access to more granular statewide data by school district in order to better understand local trends and ensure our approach aligns to their requirements & needs.

---

## Methodology of analysis


#### 1. Reading the data

1. Read the SAT and ACT data
2. View and describe the data
3. Check data completeness
4. Check for issues with the observations
5. Compare and contrast observations with source data for accuracy
6. Check datatypes of each column

#### 2. Cleaning the data

1. Fix data correctness issues; ensuring to align to source data
2. Fix incorrect datatype's
3. Rename column headers across all files
4. Drop unnecessary rows/Remove Duplicates
5. Merge cleaned Dataframes
6. Save transformed data files
7. Merge all combined yearly dataframes into a Final transformed data file
7. Define a data dictionary

#### 3. Exploratory data analysis

1. Conduct descriptive statistics on transformed data
2. Investigate trends in the data
    - Highest/Lowest participation rates
    - Highest/Lowest total/composite scores
    - States with significant YoY participation rate changes
    - States showing high participation on both tests
3. Identify states of interest for further research & analysis

#### 4. Plotting

1. Plot heat map of correlation of all variables in dataset
2. Plot histograms of the following:
        - Participation rates for SAT & ACT
        - Math scores for SAT & ACT
        - Reading/verbal scores for SAT & ACT
3. Plot scatterplots of the following:
    - SAT vs. ACT math scores for 2017
    - SAT vs. ACT verbal/reading scores for 2017
    - SAT vs. ACT total/composite scores for 2017
    - Total scores for SAT 2017 vs. 2018
    - Composite scores for ACT 2017 vs. 2018
4. Plot and interpret box plots of the following:
    - SAT vs. ACT Participation rates by year
    - SAT Math & EBRW scored by year
    - SAT Total score by year
    - ACT Sub test scores by year
    - ACT Composite scores by year
5. Additional plots and interpretations:
    - SAT vs. ACT Participation rate correlation heat map
    - SAT vs. ACT Participation rate XY scatter plots
    - SAT 2017 vs 2018 Participation XY scatter plot
    - ACT 2017 vs 2018 Participation XY scatter plot
    - SAT 2017 vs 2019 Participation XY scatter plot
    - ACT 2017 vs 2010 Participation XY scatter plot
    - SAT 2017 Total Score vs. SAT Participation
    - SAT 2018 Total Score vs. SAT Participation
    - ACT 2017 Composite Score vs. SAT Participation
    - ACT 2018 Composite Score vs. SAT Participation

---

## 5. Outside Research

Conducted supplemental external qualitative research to confirm hypotheses.

Two states that were of interest from exploring this dataset were Colorado and Ohio. I researched Colorado in order to confirm my hypothesis that they underwent a statewide transition from the ACT to the SAT and to gain a better understanding of the drivers of a state that has successfully transitioned students from the ACT to SAT. Given Ohio has had a significant improvement in the ACT participation rate over the last three years (+25%) but has not managed to obtain an SAT participation rate greater than 20%, it is an interesting state to analyze as it has a lot of potential to gain from the successes of states like Colorado.

Colorado came up in the dataset as a state that very quickly increase their SAT participation rates while simultaneously dropping their ACT rates to near 0. Given this is the first state that I wanted to understand better through external research.

Here are the highlights illustrating why Colorado's participation rates on the SAT went from near 0% to nearly 100% in a matter of three years:

- In 2015, state lawmakers voted that the Colorado Dpt. of Education must make competitive bids for college-entrance exams. Following this vote, the state decided to switch tests and replace the ACT with the SAT as the standard college entrance test for high school juniors to take
- In spring 2017, 5000 (11%) Colorado high school juniors took the SAT for the very first time  
- As our data suggests, the trial period in 2017 was a success and in 2018, Colorado scored 100% participation on the SAT with the ACT falling to 30% participation.
- This transition meant the SAT was being administered statewide at no cost
- The college board provided free SAT study materials to everyone in state

The primary driver for the high participation rate in Colorado is driven directly from changing state policies but a lot can be learnt from their success in transitioning from 100% ACT participation to 100% SAT participation in only 1 academic year. It is worth noting that Illinois exhibited the exact same pattern as Colorado (very quickly transitioning from high ACT participation rates to very high SAT rates). Upon further research, it is clear that Illinois underwent the same state-wide policy change from the ACT to the SAT as of 2017.

Both of these states transition from the ACT to the SAT comes in parallel to the College Board releasing their redesigned SAT in 2016. One of the primary goals of the overhaul was to align the SAT with the Common Core Standards (https://blog.prepscholar.com/what-is-the-common-core) making the test much more appealing as an assessment test than the older version.

The reasons both states have cited for their successes are the following:
- "They found that the College Board’s Practice SAT, given to 10th-graders, aligned better with the high school Colorado Academic Standards, a requirement of 2015 legislation" - Will Morton, director of assessment administration for the CDE -
- "The College Board’s reporting system was also considered more useful to students, because it connects them to resources and activities to best help them succeed"- Will Morton, director of assessment administration for the CDE
- "The College Board has done a good job redesigning both the PSAT and SAT to better measure what students are learning in high school and what they need to know to succeed in college"- Will Morton, director of assessment administration for the CDE
- The decision to transition was made based on the mutual agreement that the SAT exam is:
    - More relevant to the material they learned in high school
    - Removes guesswork associated with timed questions
    - Allowed 43% more time than the old ACT
    - No science section
    - Math section is simpler
    - Simplified and more relevant words in the vocabulary section
- "This SAT is frankly so much easier, so much closer to what students are seeing in their classes" - Sal Khan, Founder and President of Khan Academy
- Khan Academy teamed with the College Board to provide free and personalized SAT study courses for Colorado students
- Other test-prep companies are doing the same in advance of the administration of the SAT on April 11
- Students can prep for test online, via Skype or in class at school

In Ohio, passing the ACT or SAT is a requirement to graduate from high school. As of 2018, the state of Ohio decided to cover the cost for the ACT or SAT for all eligible high school juniors. This led to a greatly improved ACT participation rates (25% improvement) between 2017 and 2018. Over the same period the SAT has struggled to move above the 20% participation rate despite the updates/re-design to the SAT made in 2016.

This discrepancy in participation between the exams can be explained due to the fact that districts select one exam (either the SAT or ACT) to offer for the state-sponsored administration test. The students are responsible to pay for the cost of any additional administrations of the exam. Given that about 95 percent of Ohio districts have chosen the ACT over the SAT, according to the state Dpt. of Education, the cost and burden of taking the SAT often falls to students electing to take the additional examination.

Unfortunately, the improvement in participation of the ACT was also accompanied by a significant decline in mean ACT test scores. The composite scores fell from 22.0 in 2017 to 20.3 in 2018 and 20.0 in 2019. This has raised questions about how well the ACT is aligned to the Ohio education standards.  

Given the context, Ohio is an excellent candidate for the College board to focus on targeting participation rate improvements. We can apply the successful learnings from Colorado's SAT transition and leverage the overhauled student-accessible SAT design to gain traction amongst school districts for their future decision making. In 2018, 127K students took the ACT in Ohio whereas only 22.8K (18%) took the SAT. There is a lot of potential for increases in SAT participation (~5.5x of possible growth)in Ohio as well as the state infrastructure & funding to support this growth.

Sources includes in detailed report.

---

## Conclusion's & Recommendation's

The ACT and SAT participation distributions roughly mirror each other, with states geographically tending to prefer one test or the other. The ACT shows a large group of highly committed states (many states with participation rates of 100%) and a higher baseline participation nationwide. The SAT shows a larger group of states with 50-80% participation, as well as a smaller set of highly committed states. The ACT has historically been the test of choice across the U.S. That said, the SAT revamped their test as of 2016 and since then has displayed an uptrend in their nationwide participation rates.

There are strong regional and historical affiliations associated with test preference in each state. Coastal states tend to favour the SAT, while Midwestern and Mountain states tend to favour the ACT.

ACT and SAT scores are inversely correlated with their respective participation rates. This is most likely due to selection bias. Those who are electing to participate in states with no mandated requirement for that test are also taking on both the financial and time burden in order to take the test. This means that state participation will be low in these states but those that are participating will be higher achieving. In states with very high participation, it likely means that the test is mandated by the state, includes the whole student population and therefore there is diluted quality of test scores.

We can apply the successful learnings from Colorado's successful SAT transition and leverage the overhauled student-accessible SAT design to gain traction amongst Ohio school districts for their future decision making. In 2018, 127K students took the ACT in Ohio whereas only 22.8K (18%) took the SAT. There is a lot of potential for increases in SAT participation (~5.5x of possible growth) in Ohio as well as the state infrastructure & funding to support this growth.

---

## Next Steps

Moving onto the next phase of this analysis would require additional resources and data. In order to properly strategize our campaign in Ohio, it will be critical to get access to granular statewide data by school district in order to better understand local trends and ensure our approach aligns to their requirements & needs.
