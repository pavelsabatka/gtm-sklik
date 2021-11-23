# GTM template for Sklik
Template supports conversion and remarketing code.

## Conversion
[Conversion code documentation](https://napoveda.sklik.cz/mereni-uspesnosti/konverze/konverzni-kod/)

![sklik gtm template preview](https://github.com/pavelsabatka/gtm-sklik/blob/master/img/sklik-tag.png?raw=true)

## Retargeting
[Retargeting code documentation](https://napoveda.sklik.cz/cileni/retargeting/retargetingovy-kod/)

# Params
### Universal params
* `ID` - conversion or remarketing ID, expected numeric value like 111111
* `Code Type` - select conversion or retargeting

### Conversion specific
* `Order ID` - uniquie ID of conversion
* `Revenue` - revenue of conversion
* `Zbozi Shop ID` (Optional) - shop ID from [zbozi.cz aministration](https://admin.zbozi.cz/)
* `Zbozi Code Type` (Optional) - type of conversion code - Standard, Limited or Sandbox

### Retargeting specific
* `Model type` - Standard variables (1 param = 1 input) or Measurement Hub (readed from object)
* `Page type` - Category (product or service list) or Offer detail
* `Category` - [category name](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-rtg-kodu-u-kategorie-category/), only for category pages
* `Item ID` - [product ID](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-retargetingoveho-kodu/), only for Offer detail pages
* `URL` (Optional) - URL with virtual query params can be submitted here. Hostname and pathname must be same as real url. Parametr [documentation](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-rtg-kodu-volitelny-query-string/), example for [Sklik remarketing based on time on page](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-rtg-kodu-dle-doby-stravene-na-webu/)


# Consent Handling
Sklik template supports different handling with consent. In collapsable menu "Sklik" can choose from 3 different ways:
* `Consent Mode` - (default option) GTM consent mode is used - consent status is loaded from `ad_storage` and `analytics_storage`. If you choose this option, you can enable/disable consent listener. If update listener is enabled, request is sent automatically if consent is given. If update listener is disabled you must handle that with GTM triggers.
![alt text](https://github.com/pavelsabatka/gtm-sklik/blob/master/img/consent-mode.png?raw=true)
* `Load consent status from variables` - you can read consent status from your variable
![alt text](https://github.com/pavelsabatka/gtm-sklik/blob/master/img/consent-variable.png?raw=true)
* `No consent required` - tag will be fired like consent is granted
![alt text](https://github.com/pavelsabatka/gtm-sklik/blob/master/img/consent-none.png?raw=true)
