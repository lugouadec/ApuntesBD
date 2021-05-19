# Sintaxis Respaldo de la Estructura y los Datos de la  Base de Datos 
    mysqldump -v --opt --events --routines --triggers --default-character-set=utf8 -u your_username -p -h ip your_db_name > db_backup_your_db_name_`date +%Y%m%d_%H%M%S`.sql ` 
# Ejemplo
~~~
mysqldump -v --opt --events --routines --triggers --default-character-set=utf8 -u root -p -h 192.168.1.43 empresa > empresa_db_`date +%Y%m%d_%H%M%S`.sql 
~~~
# Sintaxis Respaldo solo la Estructura de la Base de Datos
~~~
mysqldump -v --opt --no-data --default-character-set=utf8 -u your_username -p -h ip your_db_name > db_structure_your_db_name_`date +%Y%m%d_%H%M%S`.sql
~~~
# Ejemplo
~~~
mysqldump -v --opt --no-data --default-character-set=utf8 -u root -p -h 192.168.1.43 empresa > db_estructura_empresadb_`date +%Y%m%d_%H%M%S`.sql
~~~

# Sintaxis Respaldo Solo de los Datos de una Base de Datos
~~~
mysqldump -v --opt --no-create-info --skip-triggers --default-character-set=utf8 -u your_username -p -h ip your_db_name > db_data_your_db_name_`date +%Y%m%d_%H%M%S`.sql
~~~
# Ejemplo
~~~
mysqldump -v --opt --no-create-info --skip-triggers --default-character-set=utf8 -u root -p -h 192.168.1.43  empresa > Datos_dbEmpresa_`date +%Y%m%d_%H%M%S`.sql
~~~

# Sintaxis Respado Tablas especificas de una Base de Datos 
~~~
mysqldump -v --opt --default-character-set=utf8 -u root -p your_db_name table1 table2 table3 > db_tables_your_db_name_`date +%Y%m%d_%H%M%S`.sql
~~~

# Ejemplo 
~~~
mysqldump -v --opt --default-character-set=utf8 -u root -p -h 192.168.1.43 empresa empleados articulos > empresadb_tEmpleados_tArticulos_`date +%Y%m%d_%H%M%S`.sql
~~~

# Sintaxis Respaldo de todas las tablas excepto las señalas
~~~
mysqldump -v --opt --default-character-set=utf8 -u your_username -p --ignore-table=bd.table1 --ignore-table=bd.table2 --ignore-table=bd.table3 your_db_name > db_tables_your_db_name_`date +%Y%m%d_%H%M%S`.sql
~~~
# Ejemplo
~~~
mysqldump -v --opt --default-character-set=utf8 -u root -p -h 192.168.1.43 --ignore-table=empresa.empleados --ignore-table=empresa.articulos empresa > dbtables_excepto_empleados_articulos_`date +%Y%m%d_%H%M%S`.sql
~~~

# Sintaxis Respaldo de Una o Varias Bases de Datos
~~~
mysqldump -u Tu Usuario -p -h ip --databases BBDD1 BBDD2 BBDD3 > nombrebackup-`date +%Y%m%d_%H%M%S`.sql
~~~

# Ejemplo
~~~
mysqldump -u root -p -h 192.168.1.43 --databases empresa empresa1 > empresadb_empresa1db_`date +%Y%m%d_%H%M%S`.sql
~~~

# Sintaxis para la Restauracion de las Tablas o Datos de Tablas de una Bases de Datos 
~~~
mysql -u your_username -p your_db_name < db_backup_your_db_name_`date +%Y%m%d_%H%M%S`.sql
~~~

# Ejemplo 
~~~
mysql -u root -p empresa < db_backup_your_db_name_`date +%Y%m%d_%H%M%S`.sql
~~~


# Sintaxis de Restauracion de Una o Varias Base de Datos en un Script
~~~
mysql -u your_username -p < nombrebackup-`date +%Y%m%d_%H%M%S`.sql
~~~

# Ejemplo
~~~
mysql -u your_username -p < nombrebackup-`date +%Y%m%d_%H%M%S`.sql
~~~
