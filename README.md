# Covid-19-project

Update(Aug 14 2020)
------------------
Note: The different best performance in the following algorithms might be result from different parameters which would be specially illustrate in the following description.

| Name | Best_Accuracy | Best_precision | Best_recall | Best_F1 score | 
| ----- | ----- | ------- | ------ | ------ | 
| DT | 94.8% | 92.7% | 97.9% | 94.7% | 
| KNN | 93.8% | 93.0% | 94.4% | 93.7% |
| RF | 96.7% | 98.2% | 97.9% | 96.7% |
| NB | 87.3% | 89.6% | 83.7% | 86.6% | 
| ET | 96.3% | 97.2% | 96.4% | 96.2% | 
| MLP | 89.6% | 89.3% | 96.4% | 89.7% |


Feature importance
--------------
![Screenshot](pics/a1.png)
**Feature ranking**
|Feature code| Feature name|
| ------- | ------ |
|feature 8 (0.292557)| Contain_Weried_number_combination|
|feature 9 (0.194848) |Alexa_rank|
|feature 0 (0.182058)| Created on 2020|
|feature 3 (0.083511) |Previous_malicious_top_level_domain_TLD|
|feature 5 (0.075750) |Wrong_spell_List|
|feature 12 (0.054549) |Redirect_URL|
|feature 6 (0.051481) |Longest_word_ratio|
|feature 10 (0.049043) |start_date|
|feature 7 (0.006558) |sub_domain|
|feature 2 (0.005403) |Freenom_top_level_domain|
|feature 1 (0.003594) |Way_back_archived|
|feature 4 (0.000650) |Name_length|
|feature 11 (0.000000) |wildcard_subdomain|


Decision Tree
-------------
**Performace graph on the correlation between max_depth and performance:**
![Screenshot](pics/d1.png)
best depth for accuracy: 4 accuracy: 0.9482758620689655  
best depth for precision: 4 precision: 0.9271844660194175  
best depth for f1_score: 4 f1_score: 0.9478908188585609  
best depth for recall: 3 recall: 0.9746192893401016  

**Performace graph on the correlation between min_leaf_number and performance:**
![Screenshot](pics/d2.png)
minimum sample for accuracy: 2 accuracy: 0.9482758620689655  
minimum sample for precision: 2 precision: 0.9271844660194175  
minimum sample for f1_score: 2 f1_score: 0.9478908188585609  
minimum sample for recall: 17 recall: 0.9796954314720813  

**Best DT visualize**
![Screenshot](pics/d3.png)

KNN
-----
Parameter(weights='distance',p=2)
**Performace graph on the correlation between Number_of_K and performance:**
![Screenshot](pics/k1.png)
best K for accuracy: 7 accuracy: 0.9384236453201971  
best K for precision: 7 precision: 0.93  
best K for f1_score: 7 f1_score: 0.9370277078085644  
best K for recall: 7 recall: 0.9441624365482234  

RF
---
**Performace graph on the correlation between max_depth and performance:**
![Screenshot](pics/r1.png)
best depth for accuracy: 17 accuracy: 0.9655172413793104  
best depth for precision: 17 precision: 0.9552238805970149  
best depth for f1_score: 17 f1_score: 0.9648241206030151  
best depth for recall: 8 recall: 0.9796954314720813  

**Performace graph on the correlation between n_estimators and performance:**
![Screenshot](pics/r3.png)
best estimator for accuracy: 12 accuracy: 0.9679802955665024  
best estimator for precision: 2 precision: 0.9820359281437125  
best estimator for f1_score: 164 f1_score: 0.9674185463659148  
best estimator for recall: 27 recall: 0.9796954314720813  

**Performace graph on the correlation between criterion and performance:**
![Screenshot](pics/r2.png)


ET
---
**Performace graph on the correlation between max_depth and performance:**
![Screenshot](pics/e1.png)
best depth for accuracy: 10 accuracy: 0.9507389162561576  
best depth for precision: 17 precision: 0.9489795918367347  
best depth for f1_score: 10 f1_score: 0.949748743718593  
best depth for recall: 6 recall: 0.9644670050761421  

**Performace graph on the correlation between n_estimators and performance:**
![Screenshot](pics/e3.png)
best estimator for accuracy: 16 accuracy: 0.9630541871921182  
best estimator for precision: 8 precision: 0.972972972972973  
best estimator for f1_score: 16 f1_score: 0.9620253164556962  
best estimator for recall: 15 recall: 0.9644670050761421  

**Performace graph on the correlation between criterion and performance:**
![Screenshot](pics/e2.png)

MLP
-----
![Screenshot](pics/MLP2.png)
**Performace graph on the correlation between batch_size and performance:**
![Screenshot](pics/MLP1.png)
best batch_size for accuracy: 19 accuracy: 0.896551724137931  
best batch_size for precision: 23 precision: 0.8936170212765957  
best batch_size for f1_score: 19 f1_score: 0.8975609756097561  
best batch_size for recall: 43 recall: 0.9644670050761421  


Update(Jul 25 2020)
--------
1. data_confirmed_CovidURL_final_version2.csv. data_Confirmed_whitelist_final_version2.csv. data_unlabled_data_final_version2.csv remove the columns ['end_date','blocked url','site age(days)','Shortening_service'], 
2. By relocating the IP address of the domain, querying the creation date of the IP address supplements the missing value in the previous start date。
3. Add new feature 'Created on 2020'.



| Name | Non_missing_value_rate(start_date)before | Non_missing_value_rate(start_date)after |
|------ | ----| ------|
| unlabeled data | 38% | 85%|
| Confirmed Covid19 related maclious data | 55% |79% |
| white list data | 100% | 100% |



Initial stage
--------------
1. Confirmed_whitelist_final_version.csv contains all white domain list with its feature.
2. confirmed_CovidURL_final_version.csv contains all maclious domain list with its feature.
3. unlabled_data_final_version.csv contains all unlabeled domain list with its feature.
4. phish_tank_final_version.csv contains all malicious urls from Phishtank with its feature
5. Data_cleaning contains part of the data preprocessing steps and data cleaning on the faature with null value.
6. Covid_unified_version.ipynb produces the inital featrue extraction from the raw data according to Professor Sopie's thesis and initial DBSCAN algorithm.
7. Phish_tank preprocess.ipynb contains new feature extraction opteration and phish tank data preprocessing steps.
8. Algorithm construction.ipynb contains current one-class SVM and DBSCAN algorithms

Data information
---------
| Name | Size | features |
|------ | ----| ------|
| unlabeled data | 229488 rows | 21|
| Phish tank data | 98251 rows | 21 |
| Confirmed Covid19 related maclious data | 394 rows |21 |
| white list data | 98 rows | 21|

Feature description
--------------------
| Feature | Data type  |  Description |
| ------- | --- | -----------|
| Unified_url | String | URLs
| Reachable_URL | categorical | Check whether the browser can reach to the url|
| Way_back_archived | categorical | Check whether the website is archived on Wayback Machine |
| Freenom_top_level_domain | categorical | Freenom top level domain (TLD) |
| Previous_malicious_top_level_domain_TLD | categorical | Previous malicious top level domain (TLD)|
| Name_length | ordinal | Domain Name length |
| Wrong_spell_List | categorical | Check whether the domain contain the wrong spell words|
| Longest_word_ratio | ordinal | Ratio of the longest English word |
| Special_mark | categorical | Containing “-” |
| sub_domain| ordinal | Number of subdomains |
| Shortening_service | ordinal | whether the url implement shortening service|
| Contain_Weried_number_combination | categorical | Presence of IP address in the URL |
| levenshtein_distance | ordinal | Mean levenshtein edit distance to confirmed phishing website |
| Alexa_rank | ordinal | Check the Alexa rank of the domain |
| Status_code | categorical | Check the domain status code by calling Amazon web service |
| start_date | ordinal | The documented record of the website creation date |
| end_date | ordinal | The documented record of the website expired date |
| site_age(days) | ordinal | Total time of website existence |
| wildcard_subdomain | categorical | This feature checks whether the domain is registered to accept all subdomains |
| Redirect_URL | categorical | This feature checks whether access to the domain redirectsto a different domain. |
| Blocked_url | categorical |This feature checks whether access to the domain returns error|

Inital feature transformation and data cleaning
------------------------------
1. Convert Alexa_rank from ordinal to binary data format. 1 means the domain has record on Alexa rank, 0 means the opposite.
2. Implement datawig Deep learning imputer model on start_date and end_date to impute missing values. 
3. Since the missing values in start_date and end_date in unlabeled_final is more than 50%, using features correlation table to extract the most relevant features corresponding to start_date and end_date can be much more accurate than the mean, median or most frequent imputation methods.
4. Normalize levenshtein_distance and site_age(days)
Feature correlation socre table
------------
![Screenshot](WechatIMG199.jpeg)
                                      
                                                  


