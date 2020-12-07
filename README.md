# jekyll-theme-haal-centraal

Dit theme wordt gebruikt voor het deployen van de documentatie in de Haal Centraal repositories naar GitHub Pages.

## Generatie logica

Centraal staan daarbij de bestanden in de folders:
* _layouts
* _includes
* assets

Hieronder lichten we de folders en zo nodig de bestanden daarin toe.

### _layouts

Deze folder bevat de layouts (of templates) voor de 4 type pagina's die we met dit theme genereren. Layouts werken volgens het volgende principe.

Minmaal 1 layout (bijv. 'default.html') bevat een basis html content met daarbinnen de jekyll code ``{{ content }}`` (een variabele). Dus zoals het volgende:
```
<html>
...
{{ content }}
...
</html>
```

Waarbij in dit voorbeeld met ``...`` andere html elementen worden bedoelt. De ``content`` variabele wordt vervangen door de (naar html omgezette) inhoud van een md bestand, de inhoud van een andere layout of de inhoud van een van de bestanden in de '\_include' folder. Deze verwijzen in hun header dan op de volgende wijze naar de basis layout
```
---
layout: default
---
```
Andere layouts bestaan op hun beurt weer uit html tags (bijv. 'div') met evt. weer de jekyll code ``{{ content }}``. Daarvoor geldt weer hetzelfde principe als hierboven is toegelicht. Zo kan een html bestand worden opgebouwd door opeenvolgende lagen van layouts die steeds de bovenliggende laag in hun header definiëren en de content uit de md bestanden. Hieronder een voorbeeld:

![Include principe](Include-principe.jpg)

De layouts kunnen overigens ook andere variabelen bevatten die in de md bestanden weer in de header of in de '\_config.yml' gedefinieerd kunnen worden.

#### default.html

Deze layout bevat de basis indeling van de Haal Centraal pagina's. Naast de variabele ``content`` worden hierin ook de variabelen ``head_include`` en ``body_include`` gebruikt. Sommige md bestanden definiëren deze in hun header en ze bevatten daar de naam van een ander 'html' bestand met daarin javascript code of een verwijzing naar een css bestand.

Indien er voor een md  bestand in de basis GitHub Pages folder (afhankelijk van de gekozen instelling de 'docs' folder, de 'root' folder of een specifieke branch) geen layout is gedefinieerd wordt automatisch deze layout toegekend.
Duidelijker is echter het gebruik af te dwingen door in de header de vermeldde code op te nemen.

#### landing-page.html

Deze layout wordt alleen gebruikt door het 'index.md' bestand in de repository 'Haal-Centraal' (de landingspagina). Het bevat slechts een 'div' element dat dus aan de default layout wordt toegevoegd. Om deze layout te kunnen gebruiken wordt de code:
```
---
layout: landing-page
---
```
in het md bestand gebruikt.

#### page-with-side-nav.html

Deze layout wordt door de meeste pagina's in de Haal Centraal site gebruikt. Naast een content deel bevat het ook een side navigatie. Ook dit bevat slechts een 'div' element waarmee het content deel van de pagina's en de side navigatie wordt gedefinieerd. Gebruik
```
---
layout: page-with-side-nav
---
```
in de header van de md bestanden om deze layout te kunnen gebruiken.

#### page.html

Layout die op dit moment niet gebruikt wordt. 

### _includes

Hier zijn building blocks opgeslagen waarmee de content van de GitHub Pages pagina's worden opgebouwd. Te weten:

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

