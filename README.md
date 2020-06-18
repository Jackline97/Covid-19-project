# Covid-19-project

Initial stage
1. whitelist_data.csv contains all white domain list with its feature(Length:600).
2. unlabeled_data.csv contains all unlabeled domain list with its feature(Length:265336).
3. Covid.ipynb produces the inital featrue extraction from the raw data according to Professor Sopie's thesis.

| Feature | Data type  |  Description |
| ------- | --- | -----------|
| Reachable_URL | categorical | Check whether the browser can reach to the url|
| Time_stamp_if_exist | int | Check the earliest timestamp history of the website|
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
