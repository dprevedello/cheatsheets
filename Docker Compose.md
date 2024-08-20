# Docker Compose Cheat-Sheet

## Comandi di Base

| Comando | Descrizione |
| --- | --- |
| `docker compose up` | Avvia tutti i servizi definiti nel file `docker-compose.yml` |
| `docker compose up -d` | Avvia i servizi in modalità detached (in background) |
| `docker compose down` | Ferma e rimuove tutti i container, network, volumi e immagini creati da `up` |
| `docker compose start` | Avvia i container esistenti senza ricrearli |
| `docker compose stop` | Ferma i container senza rimuoverli |
| `docker compose restart` | Riavvia i container |
| `docker compose build` | Costruisce o ricostruisce i servizi definiti nel file `docker-compose.yml` |
| `docker compose pull` | Scarica le immagini dei servizi definiti nel file `docker-compose.yml` |
| `docker compose push` | Esegue il push delle immagini costruite verso un registry |
| `docker compose logs` | Mostra i log di tutti i servizi o di un servizio specifico |
| `docker compose logs -f` | Segue i log in tempo reale (simile a `tail -f`) |
| `docker compose ps` | Elenca tutti i container gestiti da Docker Compose |
| `docker compose exec <service> <command>` | Esegue un comando all'interno di un container in esecuzione |
| `docker compose run <service> <command>` | Avvia un nuovo container e esegue un comando (es. eseguire una shell interattiva) |
| `docker compose rm` | Rimuove i container fermati creati con `up` |
| `docker compose config` | Valida e visualizza la configurazione del file `docker-compose.yml` |
| `docker compose pause` | Sospende l'esecuzione di tutti i container |
| `docker compose unpause` | Riprende l'esecuzione dei container sospesi |

## Gestione delle Variabili d'Ambiente

| Comando | Descrizione |
| --- | --- |
| `docker compose --env-file <file>` | Specifica un file `.env` personalizzato per caricare le variabili d'ambiente |
| `docker compose config --env-file <file>` | Valida la configurazione del file `docker-compose.yml` usando un file `.env` specifico |

## Ridimensionamento dei Servizi

| Comando | Descrizione |
| --- | --- |
| `docker compose up --scale <service>=<num>` | Specifica il numero di istanze (repliche) di un servizio da eseguire |

## Network e Volumi

| Comando | Descrizione |
| --- | --- |
| `docker compose up --force-recreate` | Ricrea i container anche se non ci sono cambiamenti nel file `docker-compose.yml` |
| `docker compose up --no-build` | Avvia i servizi senza ricostruire le immagini, anche se il Dockerfile è stato modificato |
| `docker compose up --no-deps` | Avvia un servizio senza avviare i suoi servizi dipendenti |
| `docker compose down --volumes` | Rimuove i volumi associati ai container, oltre ai container stessi |
| `docker compose down --rmi all` | Rimuove le immagini costruite dai servizi oltre ai container e volumi |

## Debug e Monitoraggio

| Comando | Descrizione |
| --- | --- |
| `docker compose top` | Mostra i processi in esecuzione all'interno dei container |
| `docker compose events` | Monitora gli eventi in tempo reale legati ai container e ai servizi |
| `docker compose port <service> <private_port>` | Mostra la porta pubblica mappata a una porta di un servizio specifico |
| `docker compose version` | Mostra la versione corrente di Docker Compose |
