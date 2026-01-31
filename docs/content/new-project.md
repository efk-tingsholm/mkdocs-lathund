# Nytt projekt (MkDocs + GitHub Pages)

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

---

## 1) Skapa projekt lokalt
Skapa en ny mapp och initiera MkDocs:

```bash
mkdir <PROJEKT-NAMN>
cd <PROJEKT-NAMN>
mkdocs new .
```

Starta lokalt för att testa:

```bash
mkdocs serve
```

---

## 2) Initiera Git och gör första commit
```bash
git init
git add .
git commit -m "Initial commit"
```

> Tips: Om du vill använda `main` som default-branch:
```bash
git branch -M main
```

---

## 3) Skapa repo på GitHub
Skapa ett nytt repo på GitHub (gärna tomt).

Kopiera repots URL (HTTPS eller SSH).

---

## 4) Koppla remote + första push
```bash
git remote add origin <REPO-URL>
git push -u origin main
```

Om du kör `master` istället för `main`:

```bash
git push -u origin master
```

---

## 5) Publicera med GitHub Pages (MkDocs)
```bash
mkdocs gh-deploy
```

Det skapar/uppdaterar en branch som heter `gh-pages`.

---

## 6) Om sidan inte syns (Pages-inställning)
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
