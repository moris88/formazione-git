# Comandi

## Configurazione

### Configurazione globale

```bash
git config --global user.name "Nome Cognome"
git config --global user.email "
```

### Configurazione locale

```bash
git config user.name "Nome Cognome"
git config user.email "
```

### Visualizzazione configurazione

```bash
git config --list
```

## Inizializzazione

### Inizializzazione di un repository

```bash
git init
```

### Clonazione di un repository

```bash
git clone <url>
```

## Stato dei file

### Visualizzazione dello stato dei file

```bash
git status
```

### Visualizzazione delle differenze

```bash
git diff
```

### Visualizzazione delle differenze in staging

```bash
git diff --staged
```

## Gestione dello staging

### Aggiunta di file allo staging

```bash
git add <file>
```

### Aggiunta di tutti i file allo staging

```bash
git add .
```

### Rimozione di file dallo staging

```bash
git reset HEAD <file>
```

## Operazioni sui file

### Commit

```bash
git commit -m "Messaggio del commit"
```

### Rimozione di file

```bash
git rm <file>
```

### Spostamento di file

```bash
git mv <file> <nuovo_file>
```

## Annullamento e cronologia delle modifiche

### Annullamento delle modifiche

```bash
git checkout -- <file>
```

### Annullamento dello staging

```bash
git reset HEAD <file>
```

### Cronologia delle modifiche

```bash
git log
```

## Tag e alias

### Creazione di un tag

```bash
git tag -a <tag> -m "Messaggio del tag"
```

### Visualizzazione dei tag

```bash
git tag
```

### Creazione di un alias

```bash
git config --global alias.<alias> <comando>
```

## I rami (branch)

### Creazione di un ramo

```bash
git branch <branch>
```

### Visualizzazione dei rami

```bash
git branch
```

### Cambio di ramo

```bash
git checkout <branch>
```

### Creazione di un ramo e cambio

```bash
git checkout -b <branch>
```

## Rami e merging

### Fusione di un ramo

```bash
git merge <branch>
```

### Rimozione di un ramo

```bash
git branch -d <branch>
```

## Fusione di rami (branch)

### Risoluzione dei conflitti

```bash
git mergetool
```

### Annullamento della fusione

```bash
git merge --abort
```

## Rebasing

### Rebase di un ramo

```bash
git rebase <branch>
```

### Continuazione del rebase

```bash
git rebase --continue
```

### Annullamento del rebase

```bash
git rebase --abort
```

## Sincronizzazione

### Pull

```bash
git pull
```

### Push

```bash
git push
```

### Fetch

```bash
git fetch
```

### Pull con rebase

```bash
git pull --rebase
```

### Push di un tag

```bash
git push origin <tag>
```

### Push di un ramo

```bash
git push origin <branch>
```

### Pull di un ramo

```bash
git pull origin <branch>
```

### Fetch di un ramo

```bash
git fetch origin <branch>
```

## Ignorare file

### Creazione di un file .gitignore

```bash
touch .gitignore
```

### Ignorare un file

```bash
echo "<file>" >> .gitignore
```

### Ignorare una cartella

```bash
echo "<cartella>/" >> .gitignore
```

## Altro

### Visualizzazione della documentazione

```bash
git help
```

### Visualizzazione della documentazione di un comando

```bash
git help <comando>
```
