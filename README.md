# Covid-19-project

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
                                      
                                                  
                                                    
Inital One-class SVM classification and parameter tuning process
------------------------
| Parameter | Value |
| --------- | -----|
| Kernel | poly |
| gamma | scale |

Discussion
----------
In the stage, Phish_tank data is regarded as negative cluster where one-class SVM model is trained on, degree of SVM model is tuned during the initial process. The rate of positive label(legitimate url) is used as performance on the observation process to find out how the level of degree would affect model performance.
![Screenshot](p1.png)

Inital DBSCAN clustering and parameter tuning process
------------------------
| Parameter | Value |
| --------- | -----|
| eps | 1.5 |
| min_samples | 30 |
| metric | cosine |
| metric_params | None|
| algorithm | auto |
| leaf_size | 30|



