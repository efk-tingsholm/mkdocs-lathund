# Jobba från ny/annan dator

## Förutsättningar
Fixa Git + Python + pip. För mer info se "first-time" Kontrollera i valfri terminal:

```bash
git --version  
#git version 2.49.0.windows.1

python --version
# Python 3.14.0

pip --version
# pip 25.1.1 from ...
```
> Notera, dessa är bara exempelversioner, ej nödvändigt med samma version.

## Installera MkDocs + Material
```bash
pip install mkdocs mkdocs-material

# Vid krångel använd hela kommandot: 
# python -m pip install mkdocs mkdocs-material
```

## Hämta länk till repo
Du har en repository på GitHub där projektet finns, klicka på den gröna rutan "Code" och kopiera länken, något i stil med : https://github.com/DITT-ANVÄNDARNAMN/REPO-NAMN.git  

## Klona repot 
För att hämta ner projektet från GitHub, använd länken från förra steget.
Notera, git clone skapar en undermapp från mappen där du är.
```bash
git clone https://github.com/DITT-ANVÄNDARNAMN/REPO-NAMN.git  
```

## Starta lokal server
Navigera till projektmappen och starta som vanligt. 
```bash
cd REPO-NAMN
mkdocs serve
```
> Kommandot måste köras i mappen där mkdocs.yml ligger.

Notera, om mkdocs serve inte rebuildar när du sparar: kolla click och pinna 8.2.1 enligt nedan:
```bash
python -m pip show click
python -m pip install "click==8.2.1"
```
