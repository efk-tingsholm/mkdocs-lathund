# Kom igång

Här är två vanliga scenarion:

- **Ny dator**: du har redan ett repo på GitHub och vill få igång allt lokalt.
- **Första gången**: du har ett lokalt projekt och vill lägga upp det som ett repo på GitHub.

> Tips: Om du “bara vill jobba som vanligt” efter att allt är igång, gå till **Dagligt pass**.

---

## Förutsättningar (gäller båda)

- Du har (eller skapar) ett konto på GitHub.
- Du har **Git** installerat.
- Du har **Python** installerat (och kan köra `python`/`pip` i terminalen).

---

## Ny dator (klona repo + installera beroenden)

### Snabbchecklista
1. Klona repot
2. Installera MkDocs + Material
3. Testa lokalt med `mkdocs serve`
4. Kör vidare via **Dagligt pass**

### Steg för steg

#### 1) Klona repot
I en terminal, gå till en mapp där du vill ha projektet och kör:

```bash
git clone <REPO-URL>
```

Gå in i mappen:

```bash
cd <REPO-NAMN>
```

#### 2) Installera MkDocs + Material
```bash
pip install mkdocs mkdocs-material
```

> [!tip]
> Om du vill undvika att installera globalt kan du senare köra virtuell miljö (venv). Men för lathundens “kom igång snabbt” räcker detta.

#### 3) Starta sidan lokalt
```bash
mkdocs serve
```

Öppna adressen som visas (ofta `http://127.0.0.1:8000/`) och kontrollera att sidan laddar.

#### 4) När du är igång
Gå vidare till **Dagligt pass** och följ checklistan där (pull → jobba → commit/push → deploy).

---

## Första gången (skapa repo på GitHub + koppla lokalt projekt)

### Snabbchecklista
1. Skapa ett nytt repo på GitHub (tomt)
2. Initiera Git lokalt (om det inte redan är gjort)
3. Koppla remote
4. Första push

### Steg för steg

#### 1) Skapa repo på GitHub
Skapa ett nytt repo (utan att lägga till README om du redan har ett lokalt projekt du vill pusha).

Notera repots URL (HTTPS eller SSH).

#### 2) Initiera Git lokalt (om behövs)
I projektmappen:

```bash
git init
```

Kolla status:

```bash
git status
```

#### 3) Lägg till remote
```bash
git remote add origin <REPO-URL>
```

Kontrollera:

```bash
git remote -v
```

#### 4) Första commit + push
```bash
git add .
git commit -m "Initial commit"
git push -u origin master
```

> [!info]
> Vissa repo använder `main` istället för `master`. Om din push klagar på branch-namn, byt `master` → `main`.

---

## Vanliga problem

### `pip` eller `python` hittas inte
- Kontrollera att Python är installerat och att “Add Python to PATH” är ikryssat (Windows).
- Testa `python --version` och `pip --version`.

### Autentisering mot GitHub strular
- Om `git push` säger “authentication failed” kan du behöva logga in på nytt eller använda token/SSH beroende på din setup.

---

## Relaterat
- Dagligt pass: `content/arbetsflode/dagligt-pass.md`
- Publicera: `content/publicera/github-pages.md`
