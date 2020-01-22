# Install Postgresql 12 on Ubuntu or Linux Mint 19.2 Tina


```sh
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
```


## Add Postgresql repository

### For Ubuntu
```sh
echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" | sudo tee  /etc/apt/sources.list.d/pgdg.list
```

### For Linux Mint 19.2 Tina
```sh
echo "deb http://apt.postgresql.org/pub/repos/apt bionic-pgdg main" | sudo tee  /etc/apt/sources.list.d/pgdg.list
```

```sh
sudo apt update
sudo apt install postgresql-12 postgresql-client-12 postgresql-server-dev-12 
```

## Install PgAdmin 4
```sh
sudo apt install pgadmin4
```

## Postgresql management commands:

```sh
# Creating user
sudo -u postgres createuser <username>

# Creating Database
sudo -u postgres createdb <dbname>
```

### Use psql
```sh
sudo -u postgres psql

psql=# alter user <username> with encrypted password '<password>';

CREATE DATABASE <dbname>;
CREATE USER <username> WITH ENCRYPTED PASSWORD '<password>';
GRANT ALL PRIVILEGES ON DATABASE <dbname> TO <username>;
```
