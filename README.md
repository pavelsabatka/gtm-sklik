# GTM template for Sklik
Template supports conversion and remarketing code.

## Conversion
Conversion code documentation is on 
https://napoveda.sklik.cz/mereni-uspesnosti/konverze/konverzni-kod/
This template supports the new version of Sklik code from May 2020
https://blog.seznam.cz/2020/03/prechazime-na-novy-konverzni-kod/

![alt text](https://github.com/pavelsabatka/gtm-sklik/blob/master/conversion.png?raw=true)

## Retargeting
Conversion code documentation is on 
https://napoveda.sklik.cz/cileni/retargeting/retargetingovy-kod/

# Params
### Universal params
* `ID` - conversion or remarketing ID, expected numeric value like 111111
* `Code Type` - select conversion or retargeting

### Conversion specific
* `Order ID` - uniquie ID of conversion
* `Revenue` - revenue of conversion
* `Zbozi Shop ID` (Optional) - shop ID from aministration https://admin.zbozi.cz/
* `Zbozi Code Type` (Optional) - type of conversion code - Standard, Limited or Sandbox

### Retargeting specific
* `Model type` - Standard variables (1 param = 1 input) or Measurement Hub (readed from object)
* `Page type` - Category (product or service list) or Offer detail
* `Category` - category name, only for category pages
* `Item ID` - product ID, only for Offer detail pages
* `URL` (Optional) - custom URL can be submitted, real URL is used if not set. Parametr [documentation](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-rtg-kodu-volitelny-query-string/), example for [Sklik remarketing based on time on page](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-rtg-kodu-dle-doby-stravene-na-webu/)
