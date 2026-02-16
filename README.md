# MariaDB + phpMyAdmin Docker Setup

Ambiente Docker semplice per avviare:

- MariaDB
- phpMyAdmin
- Connessione esterna tramite MySQL Workbench o equivalente

---

## 📦 Requisiti

- Docker
- Docker Compose (v3.9+)

Verifica:

```bash
docker --version
docker compose version

```

## 🚀 Avvio

```bash
docker compose up -d
```

## 📡 Accesso

- MariaDB: 127.0.0.1:3306
- phpMyAdmin: 127.0.0.1:8081

## 🔑 Accesso interattivo

> Assunto che MARIADB_CONTAINER_NAME = 'my-mariadb'

```bash
docker exec -it my-mariadb bash
```

### Per entrare nella shell di mariadb come root

```bash
docker exec -it my-mariadb mariadb -u root -p
```

o direttamente da dentro il container

```bash
mariadb -u root -p
```

### Per entrare nella shell di mariadb come utente (esempio `myuser` per MARIADB_USER )

```bash
docker exec -it my-mariadb mariadb -u myuser -p
```

o direttamente da dentro il container

```bash
mariadb -u myuser -p
```

### Come credenziali usare le variabili di ambiente

| Variabile | Valore di default |
| --- | --- |
| MARIADB_ROOT_PASSWORD | supersecret |
| MARIADB_DATABASE | mydatabase |
| MARIADB_USER | myuser |
| MARIADB_PASSWORD | mypassword |

## ⛔ Stop

```bash
docker compose down
```

## 📝 Note

- É possibile utilizzare il file `.env` per configurare le variabili di ambiente
- I valori di default sono definiti nel file `.env.example`
- Quando si fa riferimento al nome dell'immagine o la porta si utilizza il valore definito nel file `.env`

## 🔧 Variabili di ambiente

| Variabile | Descrizione | Valore di default |
| --- | --- | --- |
| MARIADB_VERSION | Versione di MariaDB | 11.4 |
| PHPMYADMIN_VERSION | Versione di phpMyAdmin | latest |
| MARIADB_CONTAINER_NAME | Nome del container di MariaDB | my-mariadb |
| PHPMYADMIN_CONTAINER_NAME | Nome del container di phpMyAdmin | my-phpmyadmin |
| MARIADB_HOST_PORT | Porta esposta del container di MariaDB | 3306 |
| PHPMYADMIN_HOST_PORT | Porta esposta del container di phpMyAdmin | 8081 |
| MARIADB_ROOT_PASSWORD | Password di root per MariaDB | supersecret | 
| MARIADB_DATABASE | Nome del database | mydatabase |
| MARIADB_USER | Nome utente per MariaDB | myuser |
| MARIADB_PASSWORD | Password per MariaDB | mypassword |
| PHPMYADMIN_UPLOAD_LIMIT | Limite di caricamento per phpMyAdmin | 64M |
| TZ | Timezone | Europe/Rome |

## 📜 License

[License](LICENSE)
