# Git
Git är ett versionshanteringsystem som synkroniserar mappar och filer mellan din dator och GitHub.

## Day-to-Day
1. **Öppna terminal i projektmappen**  
   T.ex. högerklicka i Utforskaren → *"Öppna i terminal"*

2. **Hämta senaste versionen från GitHub**  
I samma terminal som ovan
```powershell
git pull
```

3. **Öppna textredigeringsprogram**   
I rätt mapp, t.ex. VSCode via samma terminal som ovan.
```powershell
code .
```

4. **Starta lokal server**    
För att se ändringar i realtid
```powershell
mkdocs serve
```

5. **Utför arbete**   
Ja, du vet. Sånt.


6. **Spara backup**    
Ladda upp innehållet till GitHub. Öppna terminal i projektmappen, eller återanvänd ovanstående genom att stänga ner liveservern med 'ctrl+c'.
```powershell
git add .
git commit -m "Obligatorisk kommentar"
git push 
```
> Första pushen: git push -u origin master


7. **Uppdatera hemsidan**   
Uppdatera GitHub Pages via mkdocs.
```powershell
mkdocs gh-deploy     # MkDocs fixar pages automatiskt via detta kommando
```
