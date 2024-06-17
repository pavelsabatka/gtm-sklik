# Changelog

17.6.2024
* Je odesílán retargetingový hit i s consent=0. Po udělení souhlasu se odešle i consent=1

8.3.2024
* Výchozí hodnota pro souhlas s konverzním kódem je ad_storage
* Drobné fixy v layout

21.2.2024
* Přidány způsoby identifikace uživatele - hash emailu, telefon, adresa atd.
* Identifikace uživatele je možná i pro remarketingový kód, nejen pro konverzní
* Přidání nového typu kódu - smazání identifikace uživatele
* Změny v UX šablony
* Remarketingový kód - je možné načítat typ stránky z proměnné, poskytovat item ID a category z proměnných -> stačí jedna GTM značka pro remarketing
* Odebrána možnost spouštět kód bez souhlasu (No Consent)
