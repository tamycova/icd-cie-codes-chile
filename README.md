# CIE-9-MC / ICD-9-CM

When working with ICD codes is very hard to find the relevant mappings online, and even harder if its in Spanish. This repo contains a csv with all the procedure codes (which are used in the DRG system in Chile at the moment) for the latest version of ICD-9-CM in Spanish (9th edition, 2014). 

The mapping is [available online](https://eciemaps.mscbs.gob.es/ecieMaps/browser/index_9_mc.html) but it is not available in its raw version. The data was obtained from the [official publication of the standard's translation](https://www.mscbs.gob.es/estadEstudios/estadisticas/docs/CIE9MC_2014_def_accesible.pdf) (**procedures.pdf**). The pdf file was parsed to html using an [online tool](https://www.pdftohtml.net/) (**parsed.html**), and then scraped to find all the code-description lines (**parsing.ipynb**). The final result can be found in **codes_desc.csv**. 
