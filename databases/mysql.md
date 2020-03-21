# MySQL Cheat Sheet

### Installation
```shell
sudo apt update
sudo apt install mysql-server
sudo mysql_secure_installation
```

```
In Ubuntu systems running MySQL 5.7 (and later versions), 
the root MySQL user is set to authenticate using the auth_socket plugin by default 
rather than with a password. This allows for some greater security and usability 
in many cases, but it can also complicate things when you need to allow an external program
(e.g., phpMyAdmin) to access the user.

In order to use a password to connect to MySQL as root, 
you will need to switch its authentication method from auth_socket to mysql_native_password. 
To do this, open up the MySQL prompt from your terminal:|
```

```shell
sudo su
mysql -u root -p
```

```mysql
SELECT user,authentication_string,plugin,host FROM mysql.user;
```

```
Output
+------------------+-------------------------------------------+-----------------------+-----------+
| user             | authentication_string                     | plugin                | host      |
+------------------+-------------------------------------------+-----------------------+-----------+
| root             |                                           | auth_socket           | localhost |
| mysql.session    | *THISISNOTAVALIDPASSWORDTHATCANBEUSEDHERE | mysql_native_password | localhost |
| mysql.sys        | *THISISNOTAVALIDPASSWORDTHATCANBEUSEDHERE | mysql_native_password | localhost |
| debian-sys-maint | *CC744277A401A7D25BE1CA89AFF17BF607F876FF | mysql_native_password | localhost |
+------------------+-------------------------------------------+-----------------------+-----------+
4 rows in set (0.00 sec)
```


```sql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
FLUSH PRIVILEGES;
exit
```


### Create user
```sql
CREATE USER 'sammy'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'sammy'@'localhost' WITH GRANT OPTION;
```


### MySQL status
```bash
systemctl status mysql.service
```

### Enable connection by set up user password
```sql
SET PASSWORD FOR 'root'@'localhost' = PASSWORD('root')
FLUSH PRIVILEGES;
```

```sql
# optional
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'password';
```
