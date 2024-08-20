# Git

## Gestione del Repository

| Comando | Descrizione |
| --- | --- |
| `git init` | Inizializza un nuovo repository Git |
| `git clone <url>` | Clona un repository remoto |
| `git status` | Mostra lo stato dell'albero di lavoro |
| `git add <file>` | Aggiunge un file all'area di staging |
| `git commit -m <message>` | Esegue il commit delle modifiche nel repository |
| `git push` | Invia le modifiche al repository remoto |
| `git pull` | Scarica le modifiche dal repository remoto |
| `git fetch` | Recupera le modifiche dal repository remoto |
| `git merge <branch>` | Unisce un branch nel branch corrente |
| `git branch` | Elenca tutti i branch |
| `git branch <branch>` | Crea un nuovo branch |
| `git checkout <branch>` | Passa a un branch |
| `git checkout -b <branch>` | Crea e passa a un nuovo branch |
| `git branch -d <branch>` | Elimina un branch |
| `git log` | Mostra i log dei commit |
| `git diff` | Mostra le differenze tra i commit |
| `git blame <file>` | Mostra chi ha modificato ogni riga in un file |
| `git reflog` | Mostra un log delle modifiche a HEAD |
| `git reset --hard <commit>` | Reimposta il repository a un commit |
| `git revert <commit>` | Annulla un commit |
| `git stash` | Accantona le modifiche nella directory di lavoro |
| `git stash pop` | Applica le modifiche accantonate nella directory di lavoro |
| `git tag <tag>` | Crea un tag per un commit |

## Configurazione

| Comando | Descrizione |
| --- | --- |
| `git config --global user.name <user>` | Imposta il nome utente per Git |
| `git config --global user.email <email>` | Imposta l'email utente per Git |
| `git config --global core.editor <editor>` | Imposta l'editor di testo predefinito per Git |
| `git config --global color.ui auto` | Abilita l'output colorato per Git |

## Repository Remoti

| Comando | Descrizione |
| --- | --- |
| `git remote add <repository> <url>` | Aggiunge un repository remoto |
| `git remote -v` | Elenca i repository remoti |
| `git remote show <repository>` | Mostra informazioni su un repository remoto |
| `git remote rename <repository> <new_repository>` | Rinomina un repository remoto |
| `git remote remove <repository>` | Rimuove un repository remoto |
