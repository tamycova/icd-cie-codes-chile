# ICD CODES FOR DRG IN CHILE 

When working with ICD codes it is very hard to find the relevant mappings online, and even harder if it's in Spanish or for a specific country. In the case of Chile, the DRG system uses CIE-10/ICD-10 for diagnoses and CIE-9-MC/ICD-9-CM for procedures. This repo contains the Spanish and English versions of these codes, which were collected and scraped from different sources. Intuitively this should be a simple task, but it proved to be a considerable obstacle in my research project, which is why I am making them public. 

In this repo you can find:

- [ICD-10 2008](./diagnoses/en)
- [CIE-10 2009](./diagnoses/es)
- [ICD-9-CM 2011](./procedures/en)
- [CIE-9-MC 2014](./procedures/es)
- [Mapping from diagnosis code to English/Spanish description](./diagnoses)
- [Mapping from procedure code to English/Spanish description](./procedures)

Additionally if you are interested in the representation of ICD codes (as graphs and with embeddings), please check [this repo](https://github.com/tamycova/ICD-embeddings)


## ICD-10 2008

Scraped from the [WHO's (World Health Organization) website](https://icd.who.int/browse10/2008/en) using their JSON API. It was scraped using BFS so the JSON file also contains the graph representation of the codes (it includes a parent attribute and a boolean for leaf nodes). The file is the full representation, with not only leaf nodes but intermediate nodes.

## CIE-10 2009 8va edición/8th edition

Available online at the [Spanish Ministry of Health](https://eciemaps.mscbs.gob.es/ecieMaps/documentation/documentation.html). The processed.txt file is the .tsv 
version of the file with Spanish special characters removed to facilitate encoding. 


## ICD-9-CM 2011

The CMS (Centers for Medicare & Medicaid Services) has different versions of the ICD-9-CM Diagnosis and Procedure Codes (in abbreviated and full form) [available for downloading online](https://www.cms.gov/Medicare/Coding/ICD9ProviderDiagnosticCodes/codes). Unfortunately, the available codes are only the leaf nodes in the ICD graph (only 4 digit codes) so we are still missing information about the description in intermediate nodes, this can be found in the .tsv file procedures_official. 

The CDC (Centers for Disease Control and Prevention) has a rich text format (RTF) version of the 2011 edition (which corresponds to the CIE-9-MC of 2014 according to the Spanish Ministry of Health) [available online](https://www.cdc.gov/nchs/icd/icd9cm.htm). In order to work with this data the file was converted to pdf format, then to html format and parsed using the Beautiful Soup Python library to finally have a .tsv file with all the codes, both leaves and intermediate nodes, it can be found in the parsed_from_document directory. 

## CIE-9-MC 2014 9na edición/9th edition

In parsed_fom_document the codes are obtained from the [official publication of the standard's translation](https://www.mscbs.gob.es/estadEstudios/estadisticas/docs/CIE9MC_2014_def_accesible.pdf). The pdf file was parsed to html using an [online tool](https://www.pdftohtml.net/), and then scraped to find all the code-description lines. The final result can be found in codes_desc.csv. 

These codes are also available online at the [Spanish Ministry of Health](https://eciemaps.mscbs.gob.es/ecieMaps/documentation/documentation.html), this version is in codes_desc_official.
