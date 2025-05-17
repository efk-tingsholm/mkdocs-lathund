# Publicera till GitHub Pages med MkDocs

## 1. Skapa ett nytt repo på GitHub

1. Gå till [github.com](https://github.com)
2. Klicka på **"New repository"**
3. Skriv ett namn (t.ex. `programmering-1`)
4. Lämna övriga alternativ tomma (ingen README eller licens)
5. Välj **Public**
6. Klicka **Create repository**

> Då visas instruktioner för hur du kopplar ett lokalt projekt till repot

---

## 2. Koppla ditt lokala MkDocs-projekt till GitHub

1. Öppna terminal i din projektmapp
2. Kör följande kommandon, ett i taget (byt ut ditt användarnamn och repo-namn):

```powershell
# Initierar ett nytt git-repo i din mapp, git börjar hålla koll på filer här
# Skapas en dold mapp som innehåller historik, config, övrig info, etc etc.
git init      

# Lägger till alla filer i projektet till versionshantering, de blir "stageade",
# punkten är för "allt i den här mappen och under", hade kunnat vara
# exempelvis gitt add "min-fil.txt" 
git add .  

# Alla stage:ade filer läggs ihop till ett "snaphsot", sparas i git med en kommentar, -m står för message.
# En "commit" innehåller innehållet i filerna, datum och tid, vem som ändrat och kommentaren.
# Det är ett krav att ha ett meddelande, kort beskrivning av vad som gjorts.
git commit -m "Första versionen" 

# Skapar huvudgren och döper den till "master", som den tidigare brukade heta tydligen.
# Numer gör git huvud-branchen till main istället, men på inrådan av chatGPT så kör vi med master
# -M betyder att även om en branch redan finns så byter den namn till vårt angivna namn
git branch -M master     

# Kopplar projektet till ditt GitHub-repo, 
# git remote - kommando för att hantera remote-repositories, som man kan pusha kod till
# add - lägga till en ny remote repo
# origin - bara ett namn egentligen, kan eg. vara vad som helst, men klassiskt, enl chatGPT
git remote add origin https://github.com/DITT-ANVÄNDARNAMN/REPO-NAMN.git  

# Skicka mitt valda innehåll till den fjärrplats jag kallat `origin`, till branchen `master`
# git push - kommandot som skickar ändringar till fjärrservern, github i detta fallet
# -u - Står för: --set-upstream, kopplar ihop min lokala branch med den på servern, så man slipper skriva hela kommandot nästa gång
# Efter detta kan man skriva bara "git push"
git push -u origin master    
```

- OBS: Glöm inte att ersätta med dina riktiga uppgifter.
- Git måste vara installerat, kolla med git --version.
- Kan kontrollera vilka filer som är valda via `add` med git --status.

---

## 3. Publicera med MkDocs till GitHub Pages

När projektet är kopplat till GitHub:

```powershell
mkdocs gh-deploy
```

Det gör automatiskt:

1. Rensar `/site`-mappen i ditt projekt, d.v.s. tar bort gamla HTML-filer från tidigare byggen.
2. Kör `mkdocs build` – konverterar Markdown-filer till HTML i `site/`-mappen
3. Skapar/uppdaterar en branch i repon som heter `gh-pages`, det blir alltså en branch parallellt med vår master, med bara den färdiga hemsidan i. 
4. GitHub Pages känner igen branchen med namnet `gh-pages` och visar automatiskt innehållet som en webbsida.
5. Ger också den färdiga webblänken till hemsidan via terminalen.

* Bygger sidan, rensar gamla byggen
* Laddar upp till (skapar/uppdaterar) en branch som heter `gh-pages`
* Ger dig en färdig webblänk, t.ex.:
  `https://dittnamn.github.io/programmering-1/`

> Du kan nu länka till sidan direkt för dina elever eller kollegor

---

## 4. Uppdatera hemsidan
Att uppdatera hemsidan i `gh-pages`-branchen och att uppdatera `master`-branchen görs separat. 

Rekommendation att alltid göra båda, `master` fungerar som en backup och `gh-pages` är det som syns.

Ordningen spelar ingen roll, d.v.s. gh-pages eller git först.

I en terminal i projekt-mappen:
```powershell
# Uppdaterar den faktiska hemsidan
mkdocs gh-deploy

# Uppdaterar master-branchen med det nya innehållet
# Behöver göra både add, commit och push
git add .
git commit -m "Uppdaterat lektion 3."
git push
```


---

## 5. Ta bort ett gammalt GitHub-repo

Om du vill ta bort en testsida eller ett gammalt repo:

1. Gå till projektets sida på [github.com](https://github.com)
2. Klicka på fliken **Settings**
3. Scrolla längst ner till **Danger Zone**
4. Klicka **Delete this repository**
5. Bekräfta genom att skriva repots namn

> Du behöver **inte** radera något via terminal eller git om du ändå inte använder den mappen längre lokalt.

---

## Tips

* Du behöver **inte** köra `mkdocs build` innan `gh-deploy` – det ingår i kommandot
* Du kan radera din lokala testmapp via Utforskaren efteråt
* Du kan ha **flera projekt**, var och en på sin egen webbadress via GitHub Pages

---
