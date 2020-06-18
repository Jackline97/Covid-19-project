# Covid-19-project

Initial stage
--------------
1. data_white_final.csv contains all white domain list with its feature.
2. data_maclious_final.csv contains all maclious domain list with its feature.
3. data_final_version1.csv contains all unlabeled domain list with its feature.
4. Covid_unified_version.ipynb produces the inital featrue extraction from the raw data according to Professor Sopie's thesis and initial DBSCAN algorithm.


Feature description
--------------------
| Feature | Data type  |  Description |
| ------- | --- | -----------|
| Reachable_URL | categorical | Check whether the browser can reach to the url|
| Time_stamp_if_exist | ordinal | Check the earliest timestamp history of the website|
| Way_back_archived | categorical | Check whether the website is archived on Wayback Machine |
| Freenom_top_level_domain | categorical | Freenom top level domain (TLD) |
| Previous_malicious_top_level_domain_TLD | categorical | Previous malicious top level domain (TLD)|
| Name_length | ordinal | Domain Name length |
| Wrong_spell_List | categorical | Check whether the domain contain the wrong spell words|
| word_dic | ordinal | Ratio of the longest English word |
| Special_mark | categorical | Containing “-” |
| sub_domain| ordinal | Number of subdomains |
| Contain_IP_Adress | categorical | Presence of IP address in the URL |
| levenshtein_distance | ordinal | Mean levenshtein edit distance to confirmed phishing website |
| Alexa_rank | ordinal | Check the Alexa rank of the domain |
| Status_code | categorical | Check the domain status code by calling Amazon web service |


Inital feature transformation
------------------------------
1. Convert Alexa_rank from ordinal to binary data format. 1 means the domain has record on Alexa rank, 0 means the opposite.
2. Convert Time_stamp_if_exist from ordinal to catefory. 2 means the earliest visitor record of the domain is before 2020, 1 means in 2020, 0 means no record.

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
