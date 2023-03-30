# postgreSQL 14
```cmd
# Actualizar sistema e instalar dependencias
sudo apt update -y

sudo apt install vim curl wget gpg gnupg2 software-properties-common apt-transport-https lsb-release ca-certificates -y

# Agregar repositorio
apt policy postgresql

curl -fsSL https://www.postgresql.org/media/keys/ACCC4CF8.asc|sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/postgresql.gpg

sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'

sudo apt update

# Instalar PostgreSQL 14 PostgreSQL 14.6 
sudo apt install postgresql-14

# Ver el estado del servicio
systemctl status postgresql@14-main.service

# Administrar acceso remoto
sudo sed -i '/^host/s/ident/md5/' /etc/postgresql/14/main/pg_hba.conf

sudo sed -i '/^local/s/peer/trust/' /etc/postgresql/14/main/pg_hba.conf

sudo vim /etc/postgresql/14/main/pg_hba.conf

sudo vim /etc/postgresql/14/main/postgresql.conf

# Reiniciar Postgresql y volver a habilitarlo
sudo systemctl restart postgresql
sudo systemctl enable postgresql

# Administrar usuarios
sudo -u postgres psql

CREATE ROLE $user WITH LOGIN SUPERUSER CREATEDB CREATEROLE PASSWORD $password;
-- Verificar privilegios
\du
-- Crear base de datos y su usuario administrador
create database Home;
grant all privileges on database Home to $user;
```


## Configurar archivo /etc/postgresql/14/main/pg_hba.conf
Buscar: "IPv4 local connections:"  
```
host    all             all             127.0.0.1/32            scram-sha-256  
host    all             all             0.0.0.0/0                md5  
```
Buscar: "IPv4 local connections:"  
```
host    all             all             ::1/128                 scram-sha-256  
host    all             all             0.0.0.0/0                md5
```
## Configurar archivo /etc/postgresql/14/main/postgresql.conf
Buscar CONNECTIONS AND AUTHENTICATION  
Buscar la variable listen_addres y cambiar el valor que tiene asignado por '*'
`liste_addres = '*'`
