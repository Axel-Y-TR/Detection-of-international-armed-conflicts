# Detection-of-international-armed-conflicts

As I wanted to develop a project combining geopolitics, machine learning and data analysis, I set myself the goal of creating a solution capable of detecting international armed conflicts, such as wars, civil wars or coups d'état, with a 5-year lead time.

In the project that follows, our aim will be to attempt to predict conflicts from 2020 to 2024 (in other words, now), using data from before 2019 in order to test the effectiveness of our project. If the results seem fairly conclusive for the 2020-2024 period, it would be interesting to test the solution for other periods such as 2024-2028.

The aim of this challenge was to be completed in 6 days, so it wasn't exactly perfect. If you have any suggestions on how to improve this project, don't hesitate to let me know! I'll continue to develop it over time. 



# The files given

Data_collection: 

This file contains the code used to collect data from the different data sources used for this project. 
The data sources used for this project were the World Bank, for all economic, social and government data. Kaggle (dataset from the University of Michigan) for cultural and religious data. 
And the UCDP for all data relating to armed conflicts and their history. 

Data_cleaning: 

This file contains the code used to clean up the dataset created in the data_collection file. In particular, it fills in the NaN Values and saves the new dataset in a DB(Mysql Workbench). 
The output of this code is a dataframe of 1074 rows and 95 columns, which will then be used for the maching learning stage. 

ML:

This file contains the code needed to carry out the maching learning part of the process, which includes pre-processing, feature selection, testing several ML models, tuning the model, testing the model and finally making predictions for 2020-2024. 

# Test results 

ML Model : Random Forest

Hyperparameters used : 
Bootstrap: True,
Max_depth: 6,
min_sample _leaf: 3,
min_sample_split: 9,
n_estimator: 200,

ROC AUC Test score: 0.97

With a threshold of 0.4

Precision: 85.4%

Recall: 80.4%


 
 




10 Columns used following the RFECV:
------------------------------------------------------------------------------
| Column                           | Type de Données                          |
|----------------------------------|------------------------------------------|                                
| population_total                 | float64                                  |
| pcap (current USD)               | float64                                  |
| primary_completion(rate)         | float64                                  |
| control_corruption_estimate      | float64                                  |
| army_weight                      | float64                                  |
| Battle_related(number of death)  | float64                                  |
| homicide_(per 100k people)       | float64                                  |
| Christianity_all        | float64                                  |
| Islam_all     | float64                                  |
| Number_of_conflicts                      | int64                                  |


Description of the columns comprising the data frame use and their type:
------------------------------------------------------------------------------
| Column                           | Type de Données                          |
|----------------------------------|------------------------------------------|
| code (code)                      | Object                                   |
| country_name                     | Object                                   |
| year                             | int64                                    |
| population_total                 | float64                                  |
| gdp (current$)                   | float64                                  |
| gdp_growth                       | float64                                  |
| gdp_per_capita_ppp               | float64                                  |
| gni (current$)                   | float64                                  |
| pcap (current$)                  | float64                                  |
| poverty gap                      | float64                                  |
| primary_completion(rate)         | float64                                  |
| mortality_rate(per 1000 births)  | float64                                  |
| mortality_rate(per 1000 people)  | float64                                  |
| control_corruption_estimate      | float64                                  |
| control_corruption_rank          | float64                                  |
| army_weight                      | float64                                  |
| army_expenditure(% gdp)          | float64                                  |
| battle_related(number of deaths) | float64                                  |
| homicide_(per 100k people)       | float64                                  |
| christianity_protestant          | float64                                  |
| christianity_romancatholic       | float64                                  |
| christianity_easternorthodox     | float64                                  |
| christianity_anglican            | float64                                  |
| christianity_other               | float64                                  |
| christianity_all                 | float64                                  |
| judaism_orthodox                 | float64                                  |
| judaism_conservative             | float64                                  |
| judaism_reform                   | float64                                  |
| judaism_other                    | float64                                  |
| judaism_all                      | float64                                  |
| islam_sunni                      | float64                                  |
| islam_shi’a                      | float64                                  |
| islam_ibadhi                     | float64                                  |
| islam_nationofislam              | float64                                  |
| islam_alawite                    | float64                                  |
| islam_ahmadiyya                  | float64                                  |
| islam_other                      | float64                                  |
| islam_all                        | float64                                  |
| buddhism_mahayana                | float64                                  |
| buddhism_theravada               | float64                                  |
| buddhism_other                   | float64                                  |
| buddhism_all                     | float64                                  |
| zoroastrianism_all               | float64                                  |
| hinduism_all                     | float64                                  |
| sikhism_all                      | float64                                  |
| shinto_all                       | float64                                  |
| baha’i_all                       | float64                                  |
| taoism_all                       | float64                                  |
| jainism_all                      | float64                                  |
| confucianism_all                 | float64                                  |
| syncretism_all                   | float64                                  |
| animism_all                      | float64                                  |
| noreligion_all                   | float64                                  |
| otherreligion_all                | float64                                  |
| religion_all                     | float64                                  |
| protestant_percent               | float64                                  |
| romancatholic_percent            | float64                                  |
| easternorthodox_percent          | float64                                  |
| anglican_percent                 | float64                                  |
| otherchristianity_percent        | float64                                  |
| christianity_percent             | float64                                  |
| orthodox_percent                 | float64                                  |
| conservative_percent             | float64                                  |
| reform_percent                   | float64                                  |
| otherjudaism_percent             | float64                                   |
| judaism_percent                  | float64                                  |
| sunni_percent                    | float64                                  |
| shi’a_percent                    | float64                                  |
| ibadhi_percent                   | float64                                  |
| nationofislam_percent            | float64                                  |
| alawite_percent                  | float64                                  |
| ahmadiyya_percent                | float64                                  |
| otherislam_percent               | float64                                  |
| islam_percent                    | float64                                  |
| mahayana_percent                 | float64                                  |
| theravada_percent                | float64                                  |
| otherbuddhism_percent            | float64                                  |
| buddhism_percent                 | float64                                  |
| zoroastrianism_percent           | float64                                  |
| hinduism_percent                 | float64                                  |
| sikhism_percent                  | float64                                  |
| shinto_percent                   | float64                                  |
| baha’i_percent                   | float64                                  |
| taoism_percent                   | float64                                  |
| jainism_percent                  | float64                                  |
| confucianism_percent             | float64                                  |
| syncretism_percent               | float64                                  |
| animism_percent                  | float64                                  |
| noreligion_percent               | float64                                  |
| otherreligion_percent            | float64                                  |
| religion_sumpercent              | float64                                  |
| total_percent                    | float64                                  |
| dual_religion                    | float64                                  |
| number of conflicts              | int64                                    |
