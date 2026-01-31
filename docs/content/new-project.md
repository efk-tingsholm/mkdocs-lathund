# Starta upp MkDocs + GitHub Pages

## Förutsättningar
Kontrollera att du har Git, Python och pip:

```bash
git --version
python --version
python -m pip --version
```

Installera MkDocs + Material (om du inte redan har det):
```bash
python -m pip install mkdocs mkdocs-material
```

## Skapa MkDocs-projekt
Navigera till den mapp där du vill ha projektmappen, öppna en terminal och kör:
```bash
mkdocs new <projektnamn>
```

För att testa, navigera in i projektmappen, smidigast via terminalen direkt:
```bash
cd <projektnamn>
```
> Du ska se mkdocs.yml i mappen där du kör kommandona.

Väl inne i projektmappen kör kommandot serve:
```bash
mkdocs serve
```
> För att stänga ner den lokala servern tryck ctrl + C inne i terminalen.


## Skapa en repo på GitHub
Skapa en ny repository på GitHub. Namnet behöver inte vara samma, men det känns ju bra.

Notera, gör gärna en tom repo, ingen README/-gitignore/licens. Då slipper du krockar när du vill ladda upp ditt mkdocs-projekt istället.

Kopiera repots URL. Alltså länken.


## Starta Git och första commit
Dessa körs inne i projektmappen. Om liveservern är igång i terminalen, stäng den med Ctrl + C.
```bash
git init
git add .
git commit -m "Initial commit"
```

Sätt `main` som default-branch:
```bash
git branch -M main
```


## Koppla ihop GitHub och ditt lokala projekt
```bash
git remote add origin <REPO-URL>
git push -u origin main
```



## Publicera med GitHub Pages
MkDocs har en funktion för att publicera sidor direkt till GitHub Pages. Skrivs i terminal i projektmappen.
```bash
mkdocs gh-deploy
```
> Det skapar/uppdaterar en branch som heter `gh-pages`.


## Om sidan inte syns
Om Pages redan pekar på gh-pages behöver du inte ändra något här.

På GitHub: Settings → Pages

Välj:

- Source: Deploy from a branch
- Branch: `gh-pages` (root)


--- 


## Vanliga problem

### `mkdocs` hittas inte
Installera (igen) med:

```bash
python -m pip install mkdocs mkdocs-material
```

### `mkdocs serve` uppdaterar inte när du sparar
Kolla Click-version och pinna 8.2.1:

```bash
python -m pip show click
python -m pip install "click==8.2.1"
```
