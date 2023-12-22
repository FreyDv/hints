# PostgresREST

### How to install and run on mac m1 with installed brew

First of all you need of course postgres installed and running on your machine!

You can download and run docker image using next command:

Download and run postgres docker image

```bash
sudo docker run --name tutorial -p 5433:5432 \
                -e POSTGRES_PASSWORD=mysecretpassword \
                -d postgres
```
This will run the Docker instance as a daemon and expose port 5433 to the host system
so that it looks like an ordinary PostgreSQL server to the rest of the system.

Or you can follow nex perfect guide:
https://www.moncefbelyamani.com/how-to-install-postgresql-on-a-mac-with-homebrew-and-lunchy/
---
#### Run postgres
```bash
brew services start postgresql
```
---
#### Stop postgres
```bash
brew services stop postgresql
```
---

### Install postgrest:

MAC: 
```bash
brew install postgrest
```

Linux
```bash
pacman -S postgrest
```

Windows
```bash
choco install postgrest
scoop install postgrest
```
---
Check heals and ready to run status of just installed postgrest
Linux
```bash
postgrest -h
```
It should print the help page with its version and the available options.

---


Config file for postgrest better create in root dir with any name for example anyname.conf
```textmate
db-uri="postgres://userNameOfDB:password@HOST:PORT/DBNAME"
db-schemas="sw360"
db-anon-role="sw360"
server-port=3995
```

real example:
```textmate
db-uri = "postgres://sw360:changeme@localhost:5432/sw360db"
db-schemas = "sw360"
db-anon-role = "sw360"
server-port = 3995
```

to run postgrest with config file that have name that you provide due creation file 'anyname.conf', you just create use next command:
```bash
postgrest anyname.conf
```

real example
```bash
postgrest  sw-postgrest-local.conf
```

to check run 
```bash
curl http://localhost:3995/player
```

for all other info visit 


https://postgrest.org/en/stable/references/api/tables_views.html




