# british-national-health-service-data
A program for data munging procedures and techniques applied on a raw data set obtained from the Britain's National Health Service for extracting different useful information

This data set comes from Britain's National Health Service. 

A [glossary of terms](http://webarchive.nationalarchives.gov.uk/20180328130852tf_/http://content.digital.nhs.uk/media/10686/Download-glossary-of-terms-for-GP-prescribing---presentation-level/pdf/PLP_Presentation_Level_Glossary_April_2015.pdf/) and [FAQ](http://webarchive.nationalarchives.gov.uk/20180328130852tf_/http://content.digital.nhs.uk/media/10048/FAQs-Practice-Level-Prescribingpdf/pdf/PLP_FAQs_April_2015.pdf/) is available from the NHS regarding the data. Below we supply a data dictionary briefly describing what these fields mean.

| Data field |Description|
|:----------:|-----------|
|`'practice'`|Code designating the medical practice issuing the prescription|
|`'bnf_code'`|British National Formulary drug code|
|`'bnf_name'`|British National Formulary drug name|
|`'quantity'`|Number of capsules/quantity of liquid/grams of powder prescribed|
| `'items'`  |Number of refills (e.g. if `'quantity'` is 30 capsules, 3 `'items'` means 3 bottles of 30 capsules)|
|  `'nic'`   |Net ingredient cost|
|`'act_cost'`|Total cost including containers, fees, and discounts|

The scripts variable is a list of prescriptions issued by NHS doctors. Each prescription is represented by a dictionary with various data fields: 'practice', 'bnf_code', 'bnf_name', 'quantity', 'items', 'nic', and 'act_cost'.

```python 
scripts[:1]

[{'bnf_code': '0101010G0AAABAB',
  'items': 2,
  'practice': 'N81013',
  'bnf_name': 'Co-Magaldrox_Susp 195mg/220mg/5ml S/F',
  'nic': 5.98,
  'act_cost': 5.56,
  'quantity': 1000}]
```



The practices variable is a list of member medical practices of the NHS. Each practice is represented by a dictionary containing identifying information for the medical practice. Most of the data fields are self-explanatory. Notice the values in the 'code' field of practices match the values in the 'practice' field of scripts.

``` python
practices[:1]
[{'code': 'A81001',
  'name': 'THE DENSHAM SURGERY',
  'addr_1': 'THE HEALTH CENTRE',
  'addr_2': 'LAWSON STREET',
  'borough': 'STOCKTON ON TEES',
  'village': 'CLEVELAND',
  'post_code': 'TS18 1HU'}]
```

The Goal of this project is to find different useful insights from the given data such as summary statistics(mean, median, standard deviation etc), most common item, total posts and items by region by combining different aspects of the given data.
