#Sintaxis Respaldo de una Base de Datos con todo
mysqldump -v --opt --events --routines --triggers --default-character-set=utf8 -u your_username -p -h ip your_db_name > db_backup_your_db_name_`date +%Y%m%d_%H%M%S`.sql

#Ejemplo
mysqldump -v --opt --events --routines --triggers --default-character-set=utf8 -u root -p -h 192.168.1.43 empresa > empresa_db_`date +%Y%m%d_%H%M%S`.sql 

#Sintaxis Respaldo solo la Estructura de la base de dato
mysqldump -v --opt --no-data --default-character-set=utf8 -u your_username -p -h ip your_db_name > db_structure_your_db_name_`date +%Y%m%d_%H%M%S`.sql

#Ejemplo
mysqldump -v --opt --no-data --default-character-set=utf8 -u root -p -h 192.168.1.43 empresa > db_estructura_empresadb_`date +%Y%m%d_%H%M%S`.sql


#Sintaxis Respaldo solo de la Informacion de la Base de datos
sqldump -v --opt --no-create-info --skip-triggers --default-character-set=utf8 -u your_username -p -h ip your_db_name > db_data_your_db_name_`date +%Y%m%d_%H%M%S`.sql

#Ejemplo
mysqldump -v --opt --no-create-info --skip-triggers --default-character-set=utf8 -u root -p -h 192.168.1.43  empresa > Datos_dbEmpresa_`date +%Y%m%d_%H%M%S`.sql


#Sintaxis Respado de alguna tablas especificas 
mysqldump -v --opt --default-character-set=utf8 -u root -p your_db_name table1 table2 table3 > db_tables_your_db_name_`date +%Y%m%d_%H%M%S`.sql

#Ejemplo 
mysqldump -v --opt --default-character-set=utf8 -u root -p -h 192.168.1.43 empresa empleados articulos > empresadb_tEmpleados_tArticulos_`date +%Y%m%d_%H%M%S`.sql

#Sintaxis respaldo de todas las tablas excepto las señalas
mysqldump -v --opt --default-character-set=utf8 -u your_username -p --ignore-table=bd.table1 --ignore-table=bd.table2 --ignore-table=bd.table3 your_db_name > db_tables_your_db_name_`date +%Y%m%d_%H%M%S`.sql

#Ejemplo
mysqldump -v --opt --default-character-set=utf8 -u root -p -h 192.168.1.43 --ignore-table=empresa.empleados --ignore-table=empresa.articulos empresa > dbtables_excepto_empleados_articulos_`date +%Y%m%d_%H%M%S`.sql


#Sintaxis Respaldo de Varias Bases de Datos
mysqldump -u Tu Usuario -p -h ip --databases BBDD1 BBDD2 BBDD3 > nombrebackup-`date +%Y%m%d_%H%M%S`.sql


#Ejemplo
mysqldump -u root -p -h 192.168.1.43 --databases empresa empresa1 > empresadb_empresa1db_`date +%Y%m%d_%H%M%S`.sql


#Sintaxis Restauracion de Tablas Bases de Datos 
mysql -u your_username --password=your_password your_db_name < db_backup_your_db_name_`date +%Y%m%d_%H%M%S`.sql


#Sintaxis de Restauracion de Base de datos sin mysqldump
mysql --user=TUUSUARIO --password=TUPASSWORD < nombrebackup-`date +%Y%m%d_%H%M%S`.sql


mysqldump --user=TUUSUARIO --password=TUPASSWORD --skip-opt NOMBREBD > nombrebackup-`date +%Y%m%d_%H%M%S`.sql