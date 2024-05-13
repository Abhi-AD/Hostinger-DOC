# How to Import MySQL Database or SQL File
- Access MySQL with Root User
```sh
mysql -u root -p
```
- Create New Database
```sh
Syntax:- CREATE DATABASE <Database_name>;
Example:- CREATE DATABASE mias;
```
- Access Newly Created Database
```sh
Syntax:- USE <Database_name>;
Example:- USE mias;
```
- Import Database or SQL File
```sh
Syntax:- source <sql_file_path>
Example:- source /var/importeddb/mias.sql
```
# How to Export MySQL Database as SQL File
- Export MySQL Database as SQL File
```sh
Syntax:- mysqldump -u <db_user_name> -p <Database_Name> > <File_Path>/<File_Name>.sql
Example:- mysqldump -u root -p kilo > /var/exporteddb/kilo.sql
```