# Data at Rest Encryption

----

## Installing File Key Management Plugin

1. Follow [2]
2. Follow [8]

Check if ``file_key_management.so`` is present at ``plugin_dir``

```sql
# find plugin_dir
mysql> SHOW VARIABLES LIKE '%_dir';

# find installed plugins
mysql> SHOW PLUGINS;

# find which tables are encrypted
mysql> SELECT name, encryption_scheme FROM INFORMATION_SCHEMA.INNODB_TABLESPACES_ENCRYPTION;
```

```bash
user@device:mariadb-10.5.8$ ./bin/mysqld --datadir='/data/directory' --plugin-load-add='file_key_management.so' --file-key-management-filename='/key/file/path'
```
----

#### Links

1. [Data-at-Rest Encryption Overview - MariaDb.com](https://mariadb.com/kb/en/data-at-rest-encryption-overview/)
2. [File Key Management Encryption Plugin - MariaDb.com](https://mariadb.com/kb/en/file-key-management-encryption-plugin/)
3. [Install Plugin - MariaDb.com](https://mariadb.com/kb/en/install-plugin/)
4. [mysqld_safe - dev.mysql.com](https://dev.mysql.com/doc/refman/5.7/en/mysqld-safe.html)
5. [Error: Cannot Open Shared Library - StackOverflow.com](https://stackoverflow.com/questions/28642274/error-1126-hy000-cant-open-shared-library-lib-mysqludf-sys-so-errno-193)
6. [Configuring MariaDB with Option Files - MariaDb.com](https://mariadb.com/kb/en/configuring-mariadb-with-option-files/)
7. [Plugin Overview - MariaDb.com](https://mariadb.com/kb/en/plugin-overview/)
8. [InnoDB Encryption Overview - MariaDb.com](https://mariadb.com/kb/en/innodb-encryption-overview/)
9. [Verifying Mariadb 10.1 encryption - MariaDb.com](https://mariadb.com/kb/en/verifying-mariadb-101-encryption/)
