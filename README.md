# GTM template for Sklik
Template supports conversion and remarketing code.

## Conversion
Conversion code documentation is on 
https://napoveda.sklik.cz/mereni-uspesnosti/konverze/konverzni-kod/
This template supports the new version of Sklik code from May 2020
https://blog.seznam.cz/2020/03/prechazime-na-novy-konverzni-kod/

## Retargeting
Conversion code documentation is on 
https://napoveda.sklik.cz/cileni/retargeting/retargetingovy-kod/

# Params
### Universal params
* ID - conversion or remarketing ID, expected numeric value like 111111
* Code Type - select conversion or retargeting
* URL (Optional) - custom URL can be submitted, real URL is used if not set

### Conversion specific
* Order ID - uniquie ID of conversion
* Revenue - revenue of conversion

### Retargeting specific
* Model type - Standard variables (1 param = 1 input) or Measurement Hub (readed from object)
* Page type - Category (product or service list) or Offer detail
* Category - category name, only for category pages
* Item ID - product ID, only for Offer detail pages
