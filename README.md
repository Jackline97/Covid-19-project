# Covid-19-project

Initial stage
1. whitelist_data.csv contains all white domain list with its feature(Length:600).
2. unlabeled_data.csv contains all unlabeled domain list with its feature(Length:265336).
3. Covid.ipynb produces the inital featrue extraction from the raw data according to Professor Sopie's thesis.

| Feature | Data type  | 
| ------- | --- | 
| Freenom_TLD | categorical | 
| Suspecious_TLD | categorical | 
| Word_ratio | ordinal | 
| Contain_number | categorical | 
| Length_of_domain | ordinal | 
| Contain_dash | categorical | 
| Number_of_sub_domain| ordinal | 
| Contain_IP | categorical | 
