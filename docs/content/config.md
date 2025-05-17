# Konfigurationsfilen - mkdocs.yml

Inställningar görs via konfigurationsfilen mkdocs.yml som ligger i projektmappen. 

YAML är indenteringskänsligt. Använd bara mellanslag – aldrig tabbar. (Tror min VS Code gör mellanslag när jag tabbar, så det fungerar ju ändå höhö.)


## Grundläggande inställningar
Namn, tema och navigering. Bra för att snabbt komma igång. Notera att filadresserna utgår från mappen docs i projektmappen

```yaml
site_name: Mitt Projekt        # Namnet på sidan, visas i flik och header

theme:                         # Tema, färg och typsnitt
  name: material               # Valt tema

nav:                           # Navigation i sidomenyn 
  - Start: index.md
  - Modul 1:                   # Kan delas in i grupper med indentering
      - Intro: intro.md
      - Variabler: var.md
  - Modul 2:
      - Funktioner: func.md
```

## Temainställningar
Färger:
https://jimandreas.github.io/mkdocs-material/setup/changing-the-colors/
```yaml
theme:
  name: material                  # Använder Material-temat

  palette:
    primary: blue                 # Huvudfärg (t.ex. meny och rubriker)
    accent: indigo                # Färg på knappar, länkar etc.
    scheme: default               # Färgtema, default/slate

  font:
    text: Roboto                  # Brödtext
    code: Fira Code               # Kodblock

  features:
    - navigation.expand           # Menyn till vänster är alltid expanderad
    - navigation.sections         # Dela upp menyn i tydliga sektioner
    - navigation.tabs             # Gör huvudmenyn till flikar i toppen
    - toc.integrate               # Visar innehållsförteckning i sidomenyn
    - content.code.copy           # Kopieringsikon vid kodblock
    - content.code.annotate       # Gör att man kan använda ^1-kommentarer i kod

  logo: images/logo.png           # Logotyp i sidhuvudet (valfritt)
  favicon: images/favicon.ico     # Liten ikon i fliken (valfritt)

```



## Tillägg
Tillägg via [markdown_extensions](https://squidfunk.github.io/mkdocs-material/setup/extensions/){:target="_blank"} i mkdocs.yml. markdown_extensions är en lista med kommandon, så samla allt under EN "markdown_extensions:"

Se den rekommenderade [konfigurationen](https://squidfunk.github.io/mkdocs-material/setup/extensions/#recommended-configuration){:target="_blank"} för att få alla markdownrelaterade funktioner.

### Admonitions
De snygga tipsrutorna. [Läs mer](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#admonitions){:target="_blank"}
```yaml
markdown_extensions:
  - admonition                # Tipsrutor
  - pymdownx.details          # Utfällbara block
  - pymdownx.superfences      # Nästla annat inuti blocken
```
### Syntax highlight för kod
Använder Pygments. Färger kan ändras via extra CSS. Läs mer om [kodblock.](https://squidfunk.github.io/mkdocs-material/reference/code-blocks){:target="_blank"}

Nedanstående kopierat från officiella referensen.
```yaml
markdown_extensions:
  - pymdownx.highlight:
      anchor_linenums: true
      line_spans: __span
      pygments_lang_class: true
  - pymdownx.inlinehilite
  - pymdownx.snippets
  - pymdownx.superfences
```


### Övriga tillägg
```yaml
markdown_extensions:
  - toc:
      permalink: true         # Länkikoner vid rubriker

  - pymdownx.magiclink        # Gör länkar klickbara UTAN "[text](länk)"
  - attr_list                 # Ge HTML-attribut till länkar, bilder, osv
```


## Extra CSS och JavaSvcript
Kan lägga till en eller flera egna stilmallar via extra_css.

TODO: JavaScript.
```yaml
extra_css:                    
  - stil-1.css
  - stil-2.css
```

## Plugins
Notera hur sökfunktionen är igång från början, men om man ska köra andra plugins också så måste man skriva ut search här.
```yaml
plugins:                       # Tillägg (t.ex. sökfunktion)
  - search
```





## Övriga inställningar
Övrigt som kan vara av intresse. Typ för publicering och sånt. (Kommer inte riktigt ihåg vad de här sakerna är bra för)

```yaml


site_url: https://dittnamn.github.io/projektet/   # Webbadress
repo_url: https://github.com/dittkonto/dittrepo   # Länk till GitHub-repo
repo_name: GitHub                                 # Namn på knappen som visas
edit_uri: edit/main/docs/                         # Länk "Redigera på GitHub"

copyright: © 2025 Ditt Namn                       # Visas längst ner

extra:                                            # Egna variabler 
  kursnamn: Programmering 1                       # du kan använda i teman
  år: 2025


```

