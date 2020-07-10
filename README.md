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
![Screenshot](WechatIMG199.jpeg)
Feature correlation socre table

Inital DBSCAN parameter
------------------------
| Parameter | Value  |  
| ------- | --- | 
| Eps | 1.5| 
| Min_samples | 30 |
| Metric | Euclidean | 
| Algorithm | Auto | 
| Leaf_size | 30 | 

Results:
-------
Estimated number of clusters: 18  
Estimated number of noise points: 1788  
Silhouette Coefficient: 0.063


Next release on:
-------
1. Enhance the wrong spell check.
2. Implementing cluster on new features.
3. Duplicate feature analysis.
4. Implementing one-class classification on phishtank-urls.
