# jekyll-theme-haal-centraal

Dit theme wordt gebruikt voor het deployen van de documentatie in de Haal Centraal repositories naar GitHub Pages.

## Generatie logica

Centraal staan daarbij de bestanden in de folders:
* _layouts
* _includes
* assets

### _layouts

Deze folder bevat de layouts (of templates) voor de 4 type pagina's die we met dit theme genereren.

* default.html<br/>
Dit template bevat de basis indeling van de Haal Centraal pagina's en het wordt dan ook gebruikt door de andere templates.
Indien er voor een md bestand geen template is gedefinieerd wordt dit template automatisch toegekend.
Duidelijker is in dat geval het gebruik af te dwingen door in de header van het betreffende md bestand de volgende code te plaatsen:

```
---
layout: default
---
```

* landing-page.html<br/>
Dit template wordt alleen gebruikt door het 'index.md' bestand in de repository 'Haal-Centraal'. Het bevat slechts een 'div' element dat 
* page-with-side-nav.html
* page.html

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

