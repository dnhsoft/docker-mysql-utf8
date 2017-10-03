# docker-mysql-utf8
Inherits the standard mysql image and adds utf-8 support.
See https://hub.docker.com/_/mysql/ for more details.

```
mysql> show variables like "%character%";
+--------------------------+----------------------------+
| Variable_name            | Value                      |
+--------------------------+----------------------------+
| character_set_client     | utf8mb4                    |
| character_set_connection | utf8mb4                    |
| character_set_database   | utf8mb4                    |
| character_set_filesystem | utf8mb4                    |
| character_set_results    | utf8mb4                    |
| character_set_server     | utf8mb4                    |
| character_set_system     | utf8                       |
| character_sets_dir       | /usr/share/mysql/charsets/ |
+--------------------------+----------------------------+
```

Run the following if you have existing database and you are switching from other encoding to utf8mb4:
```
mysqlcheck -u root -p --auto-repair --optimize --all-databases
```
