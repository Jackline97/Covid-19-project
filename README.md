# Covid-19-project

Initial stage
1. whitelist_data.csv contains all white domain list with its feature(Length:600).
2. unlabeled_data.csv contains all unlabeled domain list with its feature(Length:265336).
3. Covid.ipynb produces the inital featrue extraction from the raw data according to Professor Sopie's thesis.

| Feature | Data type  |  Description |
| ------- | --- | -----------|
| Freenom_TLD | categorical | Freenom top level domain (TLD) |
| Suspecious_TLD | categorical | Previous malicious top level domain (TLD)|
| Word_ratio | ordinal | Ratio of the longest English word |
| Contain_number | categorical | Containing digits |
| Length_of_domain | ordinal | Name length |
| Contain_dash | categorical | Containing “-” |
| Number_of_sub_domain| ordinal | Number of subdomains |
| Contain_IP | categorical | Presence of IP address in the URL |
