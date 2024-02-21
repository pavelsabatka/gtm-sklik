# GTM šablona pro Sklik a Zboží.cz

[CZ](https://github.com/pavelsabatka/gtm-sklik/blob/master/README.md) | [EN](https://github.com/pavelsabatka/gtm-sklik/blob/master/README-EN.md) | [Changelog](https://github.com/pavelsabatka/gtm-sklik/blob/master/CHANGELOG.md)

Šablona má 3 možné nastavení:
* konverzní kód
* remarketingový kód
* odebrání identity uživatele - viz sekce Identita uživatele
  
![image](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/8bf1906a-b33c-4e6e-a99f-68026c4dd3f9)

#### Model Type

Data mohou být měřicím kódům předávána dvěma způsoby:

* **Standard Variables** - data v každém poli mohou být vložena s pomocí proměnných GTM *Variables*.
* **Measurement Hub** - způsob předpokládá objektový přístup k návrhu dataLayer. Šabloně jsou předány objekty (např. objekt `page`), data budou načítána z něj.

## Konverzní kód
Konverzní kód pro Sklik a Zboží.cz.

[Dokumentace](https://napoveda.sklik.cz/mereni-uspesnosti/konverze/konverzni-kod/)

### Parametry
* `Order ID` - unikátní ID konverze
* `Revenue` - hodnota konverze
* `Zbozi Shop ID` (volitelné) - shop ID z [administrace zbozi.cz](https://admin.zbozi.cz/)
* `Zbozi Code Type` (volitelné) - typ konverzního kódu - Standard, Limited or Sandbox

### Příklad
![Sklik conversion code configuration](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/98f414b6-c84a-408c-a3ef-e891d2c79986)


## Retargetingový kód
[Dokumentace](https://napoveda.sklik.cz/cileni/retargeting/retargetingovy-kod/)

### Parametry
* `Page type` - Typ stránky - Category (product or service list), Offer detail, nebo prázdné
* `Category` - [jméno kategorie](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-rtg-kodu-u-kategorie-category/)
* `Item ID` - [ID zobrazeného produktu](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-retargetingoveho-kodu/), only for Offer detail pages
* `Custom URL` (volitelné) - zde může být zadána URL s virtuálními parametry. Pozor, **doména a pathname musí být stejná s reálnou URL**, query parametry lze přidat. [Dokumentace](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-rtg-kodu-volitelny-query-string/), příklad pro [Sklik remarketing s měřením času na stránce](https://napoveda.sklik.cz/cileni/retargeting/pokrocile-nastaveni-rtg-kodu-dle-doby-stravene-na-webu/)

### Příklad
![Sklik remarketing code](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/3c686751-73d8-42f3-b9a5-2d06206c538c)


# User Identity
[Documentation](https://vyvojari.seznam.cz/identita/inzerent)

### Základní konfigurace

* `Email Hash (Silně doporučené) or Email` - Email hash (sha256) nebo Email.
Doporučujeme předávat již zashashovaný email, některé starší prohlížeče hashování nemusí podporovat. Pokud zadáte nezahashovaný email, bude automaticky šablonou zakódován a pak předán Sklik remarketingovému kódu.
Function `sha256` must be used.
* `Phone` - (volitelné) telefonní číslo ve formátu +420777111222
* `Address` - (volitelné), adresa, můžete vyplnit libovolný formát polí (e.g. Czech Republic, Česká republika, Česko, CZE, ČR,...) - Seznam používá algoritmus pro standardizaci

![image](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/090d6d0a-5890-4072-8f3c-c0a8829f5c38)

### Pokročilá konfigurace
* `Seznam Ad ID` - více informací v [dokumentaci Seznam Ad ID](https://vyvojari.seznam.cz/identita/said)
* `Czech Ad ID` - více informací [dokumentaci Czech Ad ID](https://vyvojari.seznam.cz/identita/secid)

# Odebrání identity uživatele
Smaže uživatelskou identitu předanou Sklik kódu.
Pozn.: Toto není třeba řešit pokud požíváte v GTM consent mode, při odebrání souhlasu toto šablona vyřeší za vás.

### Parametry
Žádné.

### Příklad
![image](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/e40ae318-b7fa-44bf-84f5-eb4d3171144f)


# Práce se souhlasem
Šablona podporuje dva různé druhy práce se souhlasem, které můžete vybrat z menu:
* `Consent Mode` - (výchozí) stav souhlasu je načítán z GTM consent mode - stav souhlasu je načítán z `ad_storage` a `analytics_storage` (lze změnit v nastavení).
Pokud zvolíte tuto možnost, můžete povolit nebo zakázat update listener. Pokud nemáme souhlas listener je povolen, data jsou šablonou automaticky posílána po udělelní souhlasu. Pokud listener zakážete, musíte po udělení souhlasu značku sami znovu spustit (přidat další trigger).
![image](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/0debdb17-ab28-4f37-859c-a690b996616f)

* `Load consent status from variables` - pokud chcete stav souhlasu načítat z proměnných. Předané proměnné musí vracet hodnoty granted/denied (string), 1/0 (int|string), true/false (bool).
![image](https://github.com/pavelsabatka/gtm-sklik/assets/1794400/896da879-84a9-40e6-9021-cf3bbfc4f217)

Pozn: možnost `No consent required` není od 21. 2. 2024 podporována
