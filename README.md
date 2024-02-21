# GTM template for Sklik

[CZ](https://github.com/pavelsabatka/gtm-sklik/edit/master/README.md) | [EN](https://github.com/pavelsabatka/gtm-sklik/edit/master/README-EN.md) | [Changelog](https://github.com/pavelsabatka/gtm-sklik/edit/master/CHANGELOG.md)

Template supports 3 main functions:
* conversion code
* remarketing code
* method for clearing provided user data
  
![image](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/8bf1906a-b33c-4e6e-a99f-68026c4dd3f9)

#### Model Type

Data to all codes can be submitted in two ways:

* **Standard Variables** - data will be loaded from *Variables*.
* **Measurement Hub** - expects object-oriented dataLayer structure. Data will be loaded from objects.

## Conversion code
Conversion tracking for Sklik and Zbozi.

[Conversion code documentation](https://napoveda.sklik.cz/mereni-uspesnosti/konverze/konverzni-kod/)

### Parameters
* `Order ID` - uniquie ID of conversion
* `Revenue` - revenue of conversion
* `Zbozi Shop ID` (Optional) - shop ID from [zbozi.cz aministration](https://admin.zbozi.cz/)
* `Zbozi Code Type` (Optional) - type of conversion code - Standard, Limited or Sandbox

### Example
![Sklik conversion code configuration](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/98f414b6-c84a-408c-a3ef-e891d2c79986)


## Retargeting code
[Retargeting code documentation](https://napoveda.sklik.cz/cileni/retargeting/retargetingovy-kod/)

### Parameters
* `Model type` - Standard variables (1 param = 1 input) or Measurement Hub (readed from object)
* `Page type` - Category (product or service list) or Offer detail
* `Category` - [category name](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-rtg-kodu-u-kategorie-category/), only for category pages
* `Item ID` - [product ID](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-retargetingoveho-kodu/), only for Offer detail pages
* `Custom URL` (Optional) - an URL with virtual query parameters can be submitted here. Hostname and pathname must be same as real url. Parameter [documentation](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-rtg-kodu-volitelny-query-string/), example for [Sklik remarketing based on time on page](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-rtg-kodu-dle-doby-stravene-na-webu/)

### Example
![Sklik remarketing code](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/3c686751-73d8-42f3-b9a5-2d06206c538c)


# User Identity
[Documentation](https://vyvojari.seznam.cz/identita/inzerent)

### Basic configuration

* `Email Hash (Recommended) or Email` - Email hash or Email.
If you enter a non-hashed email, it will be encoded automatically and only the encoded value will be passed to the remarketing code. We recommend passing the email hash directly using the sha256 function, some browsers may not support the hashing function.
Function `sha256` must be used.
* `Phone` - (Optional) user's phone in format +420777111222
* `Address` - (Optional), user's address, you can use any format for data (e.g. Czech Republic, Česká republika, Česko, CZE, ČR,...) - Seznam has an advanced address matching and probably resolves it

![image](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/090d6d0a-5890-4072-8f3c-c0a8829f5c38)

### Advanced configuration
* `Seznam Ad ID` - more info in [documentation](https://vyvojari.seznam.cz/identita/said)
* `Czech Ad ID` - more info in [documentation](https://vyvojari.seznam.cz/identita/secid)

# Clear provided user data
Clears an user identity passed to Sklik code. It is not necessary to use this code if you use a consent mode.

### Parameters
No parameters are required.

### Example
![image](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/e40ae318-b7fa-44bf-84f5-eb4d3171144f)


# Consent Handling
The Sklik template supports different handling with consent. In collapsable menu "Sklik" can choose from 3 different ways:
* `Consent Mode` - (default option) GTM consent mode is used - consent status is loaded from `ad_storage` and `analytics_storage`. If you choose this option, you can enable/disable the consent listener. If the update listener is enabled, requests are sent automatically if consent is given. You can choose which consent will be checked. If the update listener is disabled you must handle that with GTM triggers.
![image](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/0debdb17-ab28-4f37-859c-a690b996616f)

* `Load consent status from variables` - you can read the consent status from the GTM variable. Supported values are granted/denied (string), 1/0 (int|string), true/false (bool).
![image](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/896da879-84a9-40e6-9021-cf3bbfc4f217)

Note: option `No consent required` is no longer supported

