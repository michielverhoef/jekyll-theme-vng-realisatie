# jekyll-theme-haal-centraal

Dit theme wordt gebruikt voor het deployen van de documentatie in de Haal Centraal repositories naar GitHub Pages.

## Generatie logica

Centraal staan daarbij de bestanden in de folders:
* _layouts
* _includes
* assets

Hieronder lichten we de folders en zo nodig de bestanden daarin toe.

### _layouts

Deze folder bevat de layouts (of templates) voor de 4 type pagina's die we met dit theme genereren.

#### default.html

Dit template bevat de basis indeling van de Haal Centraal pagina's. De content van md bestanden of andere templates wordt aan dit template toegevoegd middels de code:
```
{{ content }}
```
Daarvoor dienen deze aan het begin van hun inhoud wel de volgende code te plaatsen:
```
---
layout: default
---
```
De andere templates refereren hier dus ook naar waarmee hun content een aanvulling vormt op dit template.
Indien er voor een md  bestand in de basis GitHub Pages folder (afhankelijk van de gekozen instelling de 'docs' folder, de 'root' folder of een specifieke branch) geen template is gedefinieerd wordt dit template automatisch toegekend.
Duidelijker is echter het gebruik af te dwingen door in de header de vermeldde code op te nemen.

#### landing-page.html

Dit template wordt alleen gebruikt door het 'index.md' bestand in de repository 'Haal-Centraal' (de landingspagina). Het bevat slechts een 'div' element dat dus aan het default template wordt toegevoegd. Om dit template te kunnen gebruiken wordt de code:
```
---
layout: landing-page
---
```
gebruikt.

#### page-with-side-nav.html

Dit template wordt door de meeste pagina's in de Haal Centraal site gebruikt. Naast een content deel bevat het ook een side navigatie. Ook dit bevat slechts een 'div' element waarmee het content deel van de pagina's en de side navigatie wordt gedefinieerd. Gebruik
```
---
layout: page-with-side-nav
---
```
in de header van de md bestanden om dit template te kunnen gebruiken.

#### page.html

### _includes

Hier zijn de building blocks opgeslagen waarmee de content van de GitHub Pages pagina's worden opgebouwd. Te weten:

* nav.html
* redoc-body.html
* side-nav.html
* swagger-ui-body.html
* swagger-ui-head.html
* topnavigatie.html

### assets

Tenslotte bevat de folder 'assets' het noodzakelijke css bestand en alle benodigde images. Hiernaar wordt in de bestanden in de voorgaande folders verwezen.
Hierop gaan we in dit document niet verder in.

## Geautomatiseerde rebuild

