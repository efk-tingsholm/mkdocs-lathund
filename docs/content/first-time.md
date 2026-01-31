# Första gången

## Skapa ett repo på GitHub
- Skapa ett nytt repo (gärna tomt)
- Kopiera repots URL (HTTPS eller SSH)

## Initiera Git lokalt
Stå i projektmappen:
```bash
git init
git status
```

## Koppla remote
```bash
git remote add origin <REPO-URL>
git remote -v
```

## Första commit + push
```bash
git add .
git commit -m "Initial commit"
git push -u origin main
```

## Om din default-branch heter `master`
```bash
git push -u origin master
```
