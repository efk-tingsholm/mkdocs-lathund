# Lathund för MkDocs 

MkDocs är en site-creator som tar text i markdown och gör hemsida av det. Populär för teknisk dokumentation. Kräver python och valfritt textredigeringsverktyg. 


## Day-to-Day
1. **Öppna terminal i projektmappen**  
   T.ex. högerklicka i Utforskaren → *"Öppna i terminal"*

2. **Hämta senaste versionen från GitHub**  
I samma terminal som ovan
```bash
git pull
```

3. **Öppna textredigeringsprogram**   
I rätt mapp, t.ex. VSCode via samma terminal som ovan.
```bash
code .
```

4. **Starta lokal server**    
För att se ändringar i realtid
```bash
mkdocs serve
```

5. **Utför arbete**   
Ja, du vet. Sånt.

6. **Spara backup**    
Ladda upp innehållet till GitHub. Öppna terminal i projektmappen, eller återanvänd ovanstående genom att stänga ner liveservern med 'ctrl+c'.
```bash
git status
git add .
git commit -m "Obligatorisk kommentar"
git push 
```
> Kör git status när du vill se vad som kommer med i nästa commit.

7. **Uppdatera hemsidan**   
Uppdatera GitHub Pages via mkdocs.
```bash
mkdocs gh-deploy     # Skapar/Uppdaterar gh-pages
```

## Skapa MkDocs-projekt
Öppna terminal i mappen där du vill göra projektmappen. Skapa, navigera in i mappen och starta live-servern. 
```bash
mkdocs new <projektnamn>
cd <projektnamn>
mkdocs serve
```
