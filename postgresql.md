# PostgreSQL

```sh
apt install postgresql
```

Připojení do databáze: `psql`
- `\conninfo` (zobrazí informace o připojení)
- `\q` (exit)
- `\l` (zobrazí databáze)
- `\c db` (připojí do databáze)
- `\dt` (zobrazí tabulky)
- `\d tabulka` (sloupečky tabulky)

Konfigurační soubory

```
# /etc/postgresql/13/main/postgresql.conf
listen_addresses = 'localhost'
port = 5432
```

```
# /etc/postgresql/13/main/pg_hba.conf
local   all         postgres                         peer
local   all         all                              md5
host    all         all             127.0.0.1/32     md5
host    all         all             ::1/128          md5
```
