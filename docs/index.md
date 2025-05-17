# Lathund för MkDocs 

MkDocs är en site-creator som tar text i markdown och gör hemsida av det. Populär för teknisk dokumentation. Kräver python och valfritt textredigeringsverktyg. :rocket:

## Snabbstart
ATT GÖRA: Flytta undan det gamla, lägg till snabb guide för att snabbt göra en dok, serve:a den och lägga in väldigt basic nav och markdown i ett dokument.

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.


## Flera projekt samtidigt

För att köra flera MkDocs-sidor parallellt.

```powershell
mkdocs serve -a 127.0.0.1:8001
```

> Startar servern på port 8001 istället för standard 8000.
> Öppna i ny terminalflik/fönster så kan du ha t.ex. både projektet och lathunden igång samtidigt.

---
For full documentation visit [mkdocs.org](https://www.mkdocs.org).