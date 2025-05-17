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

## Andra användbara kommandon
ATT GÖRA: Fixa utseende här.

git status
→ Visar vilka filer som är ändrade, stageade eller otrackade

git log
→ Visar historik med tidigare commits (inkl. datum, namn, meddelande)

git remote -v
→ Visar vilken GitHub-repo projektet är kopplat till

git remote set-url origin <ny-url>
→ Byt repo-koppling (t.ex. om du byter GitHub-konto)

git branch -M master
→ Byter namn på din aktuella branch till master

git config --global user.name "Ditt Namn"
→ Ställer in ditt namn för Git-commits

git config --global user.email "din@mail.se"
→ Ställer in din e-postadress för Git-commits

git clone <url>
→ Hämtar ner ett befintligt repo till din dator (om du t.ex. jobbar från en ny dator)

git init
→ Startar ett nytt lokalt Git-projekt i mappen du är i
