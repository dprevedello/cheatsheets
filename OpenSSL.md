# OpenSSL Cheat-Sheet

## Gestione dei Certificati

| Comando | Descrizione |
| --- | --- |
| `openssl req -new -key <key> -out <csr>` | Genera una nuova richiesta di firma del certificato (CSR) |
| `openssl req -x509 -key <key> -in <csr> -out <cert>` | Genera un certificato autofirmato |
| `openssl x509 -in <cert> -text -noout` | Visualizza i dettagli di un certificato |
| `openssl x509 -in <cert> -pubkey -noout` | Estrae la chiave pubblica da un certificato |
| `openssl x509 -in <cert> -fingerprint -noout` | Mostra la fingerprint di un certificato |

## Gestione delle Chiavi

| Comando | Descrizione |
| --- | --- |
| `openssl genrsa -out <key> 2048` | Genera una nuova chiave privata RSA |
| `openssl rsa -in <key> -pubout -out <pub_key>` | Estrae la chiave pubblica da una chiave privata |
| `openssl rsa -in <key> -out <new_key>` | Converte una chiave privata in un altro formato |
| `openssl rand -hex 16` | Genera una stringa esadecimale casuale |

## Firma dei Certificati

| Comando | Descrizione |
| --- | --- |
| `openssl ca -in <csr> -out <cert>` | Firma una richiesta di certificato |
| `openssl ca -config <config> -in <csr> -out <cert>` | Firma una richiesta di certificato con una configurazione personalizzata |
| `openssl verify -CAfile <ca> <cert>` | Verifica un certificato rispetto a un file CA |

## Conversione dei Certificati

| Comando | Descrizione |
| --- | --- |
| `openssl pkcs12 -export -in <cert> -inkey <key> -out <file>` | Converte un certificato e una chiave nel formato PKCS#12 |
| `openssl pkcs12 -in <file> -out <cert> -nodes` | Estrae un certificato e una chiave da un file PKCS#12 |
| `openssl x509 -in <cert> -outform DER -out <file>` | Converte un certificato nel formato DER |
| `openssl x509 -in <cert> -outform PEM -out <file>` | Converte un certificato nel formato PEM |

## Crittografia e Decrittografia

| Comando | Descrizione |
| --- | --- |
| `openssl enc -aes-256-cbc -salt -in <file> -out <encrypted_file>` | Cifra un file con AES-256-CBC |
| `openssl enc -d -aes-256-cbc -in <file> -out <decrypted_file>` | Decifra un file cifrato con AES-256-CBC |
| `openssl dgst -sha256 FILE` | Calcola l'hash SHA-256 di un file |
| `openssl dgst -md5 FILE` | Calcola l'hash MD5 di un file |

## Varie

| Comando | Descrizione |
| --- | --- |
| `openssl version` | Mostra la versione di OpenSSL |
| `openssl s_client -connect <host>:<port>` | Si connette a un server usando SSL/TLS |
| `openssl s_server -accept <port> -cert <cert> -key <key>` | Avvia un server SSL/TLS |
| `openssl speed` | Esegue test di benchmark sugli algoritmi di OpenSSL |
| `openssl ciphers -v` | Elenca tutti i cifrari disponibili |
| `openssl rand -base64 32` | Genera una stringa casuale in base64 |
| `openssl rand -base64 -out <file> 32` | Genera una stringa casuale in base64 e la salva in un file |
| `openssl rand -out <file> 32` | Genera una stringa binaria casuale e la salva in un file |
| `openssl rand -hex 32` | Genera una stringa esadecimale casuale |
