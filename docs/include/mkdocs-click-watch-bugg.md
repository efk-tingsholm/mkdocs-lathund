# Bug: MkDocs `serve` uppdaterar inte vid filändringar (Click > 8.2.1)

## Symptom
- Du kör `mkdocs serve`
- Sidan laddar på `http://127.0.0.1:8000/`
- Men när du sparar en `.md`-fil händer inget:
  - Ingen “Building documentation…” i terminalen
  - Ingen live reload i webbläsaren
- Om du stoppar servern och startar om den, syns dina ändringar (dvs “builden” funkar, men fil-watch/livereload är död)

## Orsak (kort)
MkDocs använder Python-biblioteket **Click** för sitt CLI (kommandot `mkdocs ...`).
Det finns en regression där `mkdocs serve` slutar bevaka filändringar när Click-versionen är **nyare än 8.2.1** (t.ex. 8.3.0 / 8.3.1).

## Kolla vilken Click-version du har
Kör i samma miljö där du kör MkDocs (samma Python):

```bat
python -m pip show click
```

Du kan även kolla MkDocs samtidigt:

```bat
python -m pip show mkdocs click
```

## Åtgärd: pinna Click till 8.2.1
1) Stoppa servern (`Ctrl+C`)
2) Installera Click 8.2.1:

```bat
python -m pip install "click==8.2.1"
```

3) Verifiera att det blev rätt:

```bat
python -m pip show click
```

4) Starta om servern:

```bat
python -m mkdocs serve -v
```

Efter detta ska du få “Building documentation…” när du sparar, och live reload ska fungera igen.

## (Valfritt) Undvik att problemet kommer tillbaka: lås versionskrav
Skapa en `requirements.txt` i projektet och lås Click-versionen:

```txt
mkdocs==1.6.1
mkdocs-material
click==8.2.1
```

Installera på ny dator med:

```bat
python -m pip install -r requirements.txt
```

> Tips: Om du kör med venv (rekommenderat) så blir din setup mer stabil per projekt.

## Källor / buggrapporter
- MkDocs issue: “mkdocs does not watch for file changes when using click>8.2.1” (#4032)  
  https://github.com/mkdocs/mkdocs/issues/4032
- Material for MkDocs issue: “mkdocs serve doesn't reload upon change anymore” (#8478)  
  https://github.com/squidfunk/mkdocs-material/issues/8478
