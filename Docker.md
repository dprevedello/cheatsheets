# Docker

## Esecuzione dei Container

| COMANDO | DESCRIZIONE |
| --- | --- |
| `docker run <image>` | Avvia un nuovo container da un'immagine |
| `docker run -it <image>` | Avvia un nuovo container in modalità interattiva |
| `docker run --rm <image>` | Avvia un nuovo container e lo rimuove al termine |
| `docker create <image>` | Crea un nuovo container |
| `docker start <container>` | Avvia un container |
| `docker stop <container>` | Arresta un container in modo corretto |
| `docker kill <container>` | Termina un container (SIGKILL) |
| `docker restart <container>` | Arresta e riavvia un container in modo corretto |
| `docker pause <container>` | Mette in pausa un container |
| `docker unpause <container>` | Riprende l'esecuzione di un container sospeso |
| `docker rm <container>` | Rimuove un container |

## Gestione Massiva dei Container

| COMANDO | DESCRIZIONE |
| --- | --- |
| `docker stop $(docker ps -q)` | Per arrestare tutti i container in esecuzione |
| `docker stop $(docker ps -a -q)` | Per arrestare tutti i container, sia in esecuzione che fermati |
| `docker kill $(docker ps -q)` | Per terminare tutti i container in esecuzione |
| `docker kill $(docker ps -a -q)` | Per terminare tutti i container, sia in esecuzione che fermati |
| `docker restart $(docker ps -q)` | Per riavviare tutti i container in esecuzione |
| `docker restart $(docker ps -a -q)` | Per riavviare tutti i container, sia in esecuzione che fermati |
| `docker rm $(docker ps -q)` | Per eliminare tutti i container in esecuzione |
| `docker rm $(docker ps -a -q)` | Per eliminare tutti i container, sia in esecuzione che fermati |
| `docker pause $(docker ps -q)` | Per sospendere tutti i container in esecuzione |
| `docker pause $(docker ps -a -q)` | Per sospendere tutti i container, sia in esecuzione che fermati |
| `docker start $(docker ps -q)` | Per avviare tutti i container in esecuzione |
| `docker start $(docker ps -a -q)` | Per avviare tutti i container, sia in esecuzione che fermati |
| `docker rm -vf $(docker ps -a -q)` | Per eliminare tutti i container, inclusi i volumi associati |
| `docker rmi -f $(docker images -a -q)` | Per eliminare tutte le immagini |
| `docker system df` | Mostra lo spazio utilizzato da tutte le immagini/container/volumi/cache |
| `docker buildx prune -f` | Cancella la cache di build dei container |
| `docker system prune` | Per eliminare tutte le immagini, container, cache e volumi inutilizzati o sospesi |
| `docker system prune -a` | Per eliminare tutte le immagini, usate e inutilizzate |
| `docker system prune --volumes` | Per eliminare tutti i volumi docker |

## Ispezione dei Container

| COMANDO | DESCRIZIONE |
| --- | --- |
| `docker ps` | Elenca i container in esecuzione |
| `docker ps --all` | Elenca tutti i container, compresi quelli fermati |
| `docker logs <container>` | Mostra l'output di un container |
| `docker logs -f <container>` | Segue in tempo reale l'output di un container |
| `docker top <container>` | Elenca i processi in esecuzione in un container |
| `docker diff` | Mostra le differenze con l'immagine (file modificati) |
| `docker inspect` | Mostra le informazioni di un container (in formato json) |

## Esecuzione di Comandi

| COMANDO | DESCRIZIONE |
| --- | --- |
| `docker attach <container>` | Si collega a un container |
| `docker cp <container>:<container-path> <host-path>` | Copia file dal container |
| `docker cp <host-path> <container>:<container-path>` | Copia file nel container |
| `docker export <container>` | Esporta il contenuto di un container (come archivio tar) |
| `docker exec <container>` | Esegue un comando all'interno di un container |
| `docker exec -it <container> /bin/bash` | Apre una shell interattiva all'interno di un container (in alcune immagini, usa /bin/sh se /bin/bash non è presente) |
| `docker wait <container>` | Attende la terminazione del container e restituisce il codice di uscita |

## Immagini

| COMANDO | DESCRIZIONE |
| --- | --- |
| `docker image ls` | Elenca tutte le immagini locali |
| `docker history <image>` | Mostra la cronologia di un'immagine |
| `docker inspect <image>` | Mostra le informazioni (in formato json) |
| `docker tag <image> <tag>` | Applica un tag a un'immagine |
| `docker commit <container> <image>` | Crea un'immagine da un container |
| `docker import <url>` | Crea un'immagine da un archivio tar |
| `docker rmi <image>` | Elimina immagini |
| `docker pull <user>/<repository>:<tag>` | Scarica un'immagine da un registro |
| `docker push <user>/<repository>:<tag>` | Carica un'immagine su un registro |
| `docker search <test>` | Cerca un'immagine nel registro ufficiale |
| `docker login` | Effettua il login a un registro |
| `docker logout` | Effettua il logout da un registro |
| `docker save <user>/<repository>:<tag>` | Esporta un'immagine o un repository come archivio tar |
| `docker load` | Carica immagini da un archivio tar |

## Volumi

| COMANDO | DESCRIZIONE |
| --- | --- |
| `docker volume ls` | Elenca tutti i volumi |
| `docker volume create <volume>` | Crea un volume |
| `docker volume inspect <volume>` | Mostra le informazioni (in formato json) |
| `docker volume rm <volume>` | Distrugge un volume |
| `docker volume ls --filter="dangling=true"` | Elenca tutti i volumi non referenziati da alcun container |
| `docker volume prune` | Elimina tutti i volumi non referenziati da alcun container |
| `docker run --rm --volumes-from <container> -v $(pwd):/backup busybox tar cvfz /backup/backup.tar.gz <container-path>` | Effettua un backup di un container |
| `docker run --rm --volumes-from <container> -v $(pwd):/backup busybox sh -c "cd <container-path> && tar xvfz /backup/backup.tar.gz --strip 1"` | Ripristina un container da un backup |
