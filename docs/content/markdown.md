# Skriva i Markdown

## Bilder

Sätt in en bild med alt-text och sökväg:

```markdown
![Beskrivning](bilder/filnamn.jpg)
```
> Sökvägen utgår från `docs/`-mappen.

Mer kontroll (storlek, centrering etc.) via HTML:
```html
<img src="bilder/filnamn.jpg" width="300" />
```

---

## Länkar

### Interna länkar
Till andra `.md`-sidor i projektet.
```markdown
[Länktext](content/fil.md)
```

### Externa länkar
```markdown
[Länktext](https://exempel.se)
```

### Öppna i ny flik
Kräver tillägget `attr_list`.
```markdown
[Länktext](https://exempel.se){:target="_blank"}
```

---

## Kodblock

### Inline-kod
Via VS Code extension `Markdown All in One` kan man sätta en keyboard shortcut för att lägga till runt markerad text.
```markdown
Använd `print()` för att skriva ut i Python.
```

### Block med kod
````markdown
```python
print("Hej världen")
```
````

> Ändra `python` till `csharp`, `html` osv. beroende på språk.
> För att lägga block inuti block, använd 4 backticks istället.

---

## Admonitions
Tipsrutor som används för att lyfta fram info. Kräver `admonition` i `markdown_extensions`. [Läs mer.](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#admonitions){:target="_blank"}

### Enkel ruta
```markdown
!!! note "Observera"
    Det här är en ruta med information.
```
!!! note "Observera"
    Det här är en ruta med information.

### Utfällbar
```markdown
??? tip "Visa exempel"
    Här kan man lägga mer info som kan fällas ut.
```
??? tip "Visa exempel"
    Här kan man lägga mer info som kan fällas ut.

## Citatblock
Används för att visa information i indraget format.
```
> Detta är ett citat eller informationsblock.
```
> Det visas som ett visuellt indrag och är bra för att lyfta fram tips, förklaringar eller citat.


## Listor

### Punktlista
```
- Första punkt
- Andra punkt
  - Undernivå
```

### Numrerad lista

```
1. Första steg
2. Andra steg
   1. Underrad
```

Punkt- eller numrering avgör listtypen. Indrag med 2 eller 4 mellanslag skapar nivåer.

## Tabeller

Skapa en enkel tabell med | och -.

```
| Namn     | Ålder | Klass     |
|----------|-------|-----------|
| Olle     | 17    | TE22B     |
| Johanna  | 18    | TE22A     |
```

| Namn     | Ålder | Klass     |
|----------|-------|-----------|
| Olle     | 17    | TE22B     |
| Johanna  | 18    | TE22A     |

Tabellen måste ha en rad med --- för att separera rubriker från innehåll.

För vänster-, höger- eller centrerad justering:

```
| Vänster | Mitten | Höger |
|:--------|:------:|------:|
| A       | B      | C     |
```

Kolon `:` anger justeringen – före, efter eller både ger vänster, höger eller centrerat.

