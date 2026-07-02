# Notas de PostgreSQL

## Construir PosgreSQL:

```bash
curl -LO https://ftp.postgresql.org/pub/source/v18.3/postgresql-18.3.tar.gz
./configure --prefix=/home/user/postgresql-18.3/opt
make
make install
# Build Extensions
cd /home/user/postgresql-18.3/contrib
make
make install

ls /home/user/postgresql-18.3/contrib/share/extensions
```

Ver si esta todo correcto:

```bash
cd opt
opt $ bin/pg_config --bindir
/home/user/postgresql-18.3/opt/bin
opt $ bin/pg_config --libdir
/home/user/postgresql-18.3/opt/lib
opt $ bin/pg_config --sharedir
/home/user/postgresql-18.3/opt/share

```

## Primer arranque de PostgreSQL

Crear directorios base:

```bash
mkdir -p /var/psql/data
mkdir -p /var/psql/log
```

Ver version de `initdb`:

```bash
initdb --version
# initdb (PostgreSQL) 18.0
```

Inicializar cluster por primera vez:

```bash
initdb -D /var/psql/data/
```

Comprobar version usada para inicializar:

```bash
cat /var/psql/data/PG_VERSION
# 18
```

Conectar a PostgreSQL indicando host, puerto, base de datos y usuario:

```bash
psql -h localhost -p 15433 -d postgres -U userexample
```

> Nota: el usuario administrador inicial suele ser el mismo que ejecuto `initdb`.

---

## Sesion base de pruebas en `psql`

Mostrar version del backend:

```sql
SHOW server_version;
```

Ejemplo

```bash
postgres=# show server_version;
 server_version 
----------------
 18.3
(1 row)
```

Mostrar rol y base actual (cada conexión de un cliente solo trabaja con una database
a la vez. No obstante se puede cambiar la base de datos en la misma conexión):
Es un meta-comando de psql. Su función es mostrar la información de la conexión actual
a la base de datos.  Al ejecutarlo, muestra datos como:

1. Base de datos a la que estás conectado
2. Usuario con el que te conectaste
3. Host (servidor)
4. Puerto

```psql
\conninfo
```

Ejemplo:

```bash
postgres=# \conninfo
      Connection Information
      Parameter       |   Value   
----------------------+-----------
 Database             | postgres
 Client User          | userexample
 Host                 | localhost
 Host Address         | 127.0.0.1
 Server Port          | 5433
 Options              | 
 Protocol Version     | 3.0
 Password Used        | false
 GSSAPI Authenticated | false
 Backend PID          | 938
 SSL Connection       | false
 Superuser            | on
 Hot Standby          | off
(13 rows)
```

Limpiar pantalla:

```psql
\! clear
```

Ver historial de comandos:

```psql
\s
```

Listar bases de datos:

```psql
\l
\l+
```

Listar schemas de la base conectada:

```psql
\dn *
```

Recordemos que: Un schema (esquema) es un espacio de nombres (namespace) dentro de
una base de datos que permite organizar y agrupar objetos como:

1. Tablas
2. Vistas
3. Funciones
4. Secuencias
5. Tipos de datos
6. Índices

PostgreSQL incluye un schema llamado ```public``` por defecto. Si no especificas un schema,
todos los objetos se crean ahí.  El schema public existe por defecto pero viene vacío.
Es simplemente un contenedor listo para que tú crees tus objetos dentro de él.

Ejemplo: Mostrar el schema por defecto

```bash
postgres=# \dn public;
      List of schemas
  Name  |       Owner       
--------+-------------------
 public | pg_database_owner
(1 row)
```

Search Path: El search_path define en qué schemas busca PostgreSQL cuando no especificas uno
explícitamente. Por defecto es "$user", public, es decir, primero busca un schema con el
nombre del usuario actual y luego en public.

```bash
postgres=# show search_path;
   search_path   
-----------------
 "$user", public
(1 row)
```

```bash
-- Ver schemas existentes
\dn

-- Ver el search_path actual (orden de búsqueda de schemas)
SHOW search_path;

-- Cambiar el search_path
SET search_path TO ventas, public;
```

Nota: Todas las tablas siempre pertenecen a un schema. Las tablas internas que ya existen
en el servidor están en sus propios schemas. Lo que ocurre cuando se ejecuta \dn es que solo
muestra los schemas del search_path, no se ve los schemas del sistema.

Ver todos los schemas incluidos los del sistema:

```bash
\dnS
```

Ejemplo:

```bash
postgres-# \dnS
            List of schemas
        Name        |       Owner       
--------------------+-------------------
 information_schema | exampleuser
 pg_catalog         | exampleuser
 pg_toast           | exampleuser
 public             | pg_database_owner
(4 rows)
```

Listar roles (usuarios):

```psql
\dg
\dg+
\du
```

Crear schemas:

```sql
CREATE SCHEMA control;
CREATE SCHEMA schema01;
CREATE SCHEMA schema02;
```

Crear tablas:

```sql
CREATE TABLE control.my_first_table (first_column text, second_column integer);
CREATE TABLE control.products (product_no integer, name text, price numeric);

CREATE TABLE schema01.table_uno (first_column text, second_column integer);
CREATE TABLE schema02.table_dos (first_column text, second_column integer);
```

Listar todas las tablas existentes (muestra a que schema pertenecen):

```psql
\dt *.*
```

Listar todas las tablas del sistema (muestra ):

```psql
\dtS
```

Listar tablas de de schema de ejemplo `control`:

```psql
\dt control.*
```

Insertar filas:

```sql
INSERT INTO control.my_first_table VALUES ('uno', 1);
INSERT INTO control.my_first_table VALUES ('dos', 2);
INSERT INTO control.my_first_table VALUES ('tres', 3);

INSERT INTO schema01.table_uno VALUES ('uno', 1);
INSERT INTO schema01.table_uno VALUES ('dos', 2);

INSERT INTO schema02.table_dos VALUES ('uno', 1);
```

---

## Extensions

Vimos como se compilaban las extensions disponibles en la distribución de PostgreSQL,
directorio contrib.

Listar las extensiones disponibles:

```sql
SELECT * FROM pg_available_extensions;
```

Listar las extensiones activadas en esta instancia:

```bash
\dx
```

Existen también muchas extensiones que no forman parte de la distribución de PostgreSQL,
hay que bajarse los fuentes y compilarlas independientemente. Por ejemplo:

```bash
https://github.com/EnterpriseDB/system_stats
```

## Roles y privilegios

Crear roles base:

```sql
CREATE ROLE role_all_schemas_rw;
CREATE ROLE role_all_schemas_ro;
CREATE ROLE role_control_schema_rw;
```

Listar atributos de roles no internos:

```sql
\x on
SELECT * FROM pg_roles WHERE rolname !~ '^pg_';
\x off
```

Ver atributos de un rol especifico:

```sql
SELECT * FROM pg_roles WHERE rolname = 'userexample';
```

Comentar un rol:

```sql
COMMENT ON ROLE userexample IS 'El superusuario';
```

### 03.1 Gestion de object privileges (grants)

Dar todos los privilegios sobre todas las tablas de un schema:

```sql
GRANT ALL PRIVILEGES ON ALL TABLES IN SCHEMA control TO role_control_schema_rw;
```

Dar solo lectura:

```sql
GRANT SELECT ON ALL TABLES IN SCHEMA control TO role_control_schema_rw;
```

Revocar todos los privilegios:

```sql
REVOKE ALL ON ALL TABLES IN SCHEMA control FROM role_control_schema_rw;
```

Listar object privileges de tablas:

```psql
\dp control.*
\dp control.products
```

Listar privilegios de un rol sobre tablas:

```sql
SELECT *
FROM information_schema.role_table_grants
WHERE grantee = 'role_control_schema_rw';
```

Eliminar roles y usuarios:

```sql
DROP ROLE user_ro_all;
DROP ROLE user_rw_all;

REVOKE USAGE ON SCHEMA control FROM role_control_schema_rw;
REVOKE ALL ON ALL TABLES IN SCHEMA control FROM role_control_schema_rw;
DROP ROLE role_control_schema_rw;
```

---

## 04) Sesion completa de ejemplo

### 04.1 Crear roles base y grants

```sql
CREATE ROLE role_all_schemas_rw;
GRANT USAGE ON SCHEMA control TO role_all_schemas_rw;
GRANT USAGE ON SCHEMA schema01 TO role_all_schemas_rw;
GRANT USAGE ON SCHEMA schema02 TO role_all_schemas_rw;
GRANT ALL PRIVILEGES ON ALL TABLES IN SCHEMA control TO role_all_schemas_rw;
GRANT ALL PRIVILEGES ON ALL TABLES IN SCHEMA schema01 TO role_all_schemas_rw;
GRANT ALL PRIVILEGES ON ALL TABLES IN SCHEMA schema02 TO role_all_schemas_rw;
SELECT * FROM information_schema.role_table_grants WHERE grantee = 'role_all_schemas_rw';

CREATE ROLE role_all_schemas_ro;
GRANT USAGE ON SCHEMA control TO role_all_schemas_ro;
GRANT USAGE ON SCHEMA schema01 TO role_all_schemas_ro;
GRANT USAGE ON SCHEMA schema02 TO role_all_schemas_ro;
GRANT SELECT ON ALL TABLES IN SCHEMA control TO role_all_schemas_ro;
GRANT SELECT ON ALL TABLES IN SCHEMA schema01 TO role_all_schemas_ro;
GRANT SELECT ON ALL TABLES IN SCHEMA schema02 TO role_all_schemas_ro;
SELECT * FROM information_schema.role_table_grants WHERE grantee = 'role_all_schemas_ro';

CREATE ROLE role_control_schema_rw;
GRANT USAGE ON SCHEMA control TO role_control_schema_rw;
GRANT ALL PRIVILEGES ON ALL TABLES IN SCHEMA control TO role_control_schema_rw;
SELECT * FROM information_schema.role_table_grants WHERE grantee = 'role_control_schema_rw';
```

### 04.2 Crear usuarios con login

```sql
CREATE ROLE user_rw_all WITH LOGIN PASSWORD 'my-secret' INHERIT;
CREATE ROLE user_ro_all WITH LOGIN PASSWORD 'my-secret' INHERIT;
CREATE ROLE user_control_rw WITH LOGIN PASSWORD 'my-secret' INHERIT;
```

### 04.3 Asignar usuarios a roles

```sql
GRANT role_control_schema_rw TO user_control_rw;
GRANT role_all_schemas_ro TO user_ro_all;
GRANT role_all_schemas_ro TO user_ro_all;
GRANT role_all_schemas_rw TO user_rw_all;
```

---

## 05) Conexion y comandos utiles de `psql`

Probar conexion:

```bash
pg_isready -d postgres -h 127.0.0.1 -p 5000 -U postgres
```

Abrir cliente:

```bash
psql -U postgres -h localhost -p 5000
```

Comandos frecuentes:

- `\l`: listar databases
- `\c db_name`: cambiar de database
- `\dt`: listar tablas
- `\d`: describir tablas
- `\d tab_name`: describir tabla especifica
- `\dn`: listar schemas
- `\dv`: listar vistas
- `\df`: listar funciones
- `\du`: listar usuarios/roles
- `\s`: historial
- `\o file_name`: guardar salida en fichero
- `\i file_name`: ejecutar script
- `\g`: repetir ultimo comando
- `\a`: alternar alineacion de salida
- `\h`: ayuda SQL
- `\?`: ayuda de `psql`
- `\! cls`: limpiar pantalla (Windows)
- `\q`: salir

---

## 06) Que es un schema en PostgreSQL

Un schema es una coleccion con nombre de objetos de una base de datos: tablas, vistas, funciones, secuencias, indices, constraints, etc.

Jerarquia:

1. Una instancia PostgreSQL puede tener multiples databases.
2. Cada database puede tener multiples schemas.
3. Cada schema puede tener multiples tablas.

Ejemplo: database `postgres` con schemas `ecommerce`, `auth`, etc.

---

## 07) Consultas rapidas de catalogo

Listar schemas disponibles:

```sql
SELECT nspname FROM pg_catalog.pg_namespace;
SELECT schema_name FROM information_schema.schemata;
```

O desde `psql`:

```psql
\dn
```

Listar todas las tablas de todos los schemas:

```psql
\dt *.*
```

Listar tablas de un schema:

```psql
\dt control.*
```

Borrar base de datos:

```sql
DROP DATABASE odoo;
```

Version de la instancia:

```sql
SHOW server_version;
```

Databases de la instancia:

```sql
SELECT datname, datistemplate FROM pg_database;
```

Schemas de la database actual:

```sql
SELECT * FROM information_schema.schemata;
```

Database y schema actuales:

```sql
SELECT current_catalog;
SELECT current_schema;
```

Directorio de datos (`PGDATA`):

```sql
SHOW data_directory;
```

Ficheros de configuracion:

```sql
SELECT name, setting
FROM pg_settings
WHERE category = 'File Locations';
```

Toda la parametrizacion en runtime:

```sql
SHOW all;
SELECT * FROM pg_settings;
```

Tablespaces y ruta fisica:

```sql
SELECT *, pg_tablespace_location(oid)
FROM pg_tablespace;
```

OID de una database (para ubicar ficheros):

```sql
SELECT oid FROM pg_database WHERE datname = 'learning';
```

Patron habitual:

```text
<POSTGRESQL_DIRECTORY>/data/base/<OID>
```

Ejemplo:

```text
/var/psql/data/base/49182
```

---

## 08) Training

### 08.1 Libros 

PostgreSQL: Up and Running (3rd ed.) — Regina Obe, Leo Hsu
No es “internals deep” de código, pero da base excelente del sistema (tipos, índices, planner, etc.) y te prepara para 
entender decisiones del core.

PostgreSQL 14 Internals — Egor Rogov (PDF/online)
Muy orientado a “cómo funciona por dentro” (heap, MVCC, WAL, vacuum, buffers). Es de lo más cercano a un 
“libro de internals” moderno y práctico. Suele existir también como “PostgreSQL 13/15 Internals” según versión.

The Internals of PostgreSQL — Hironobu SUZUKI (online)
Explica con diagramas y narrativa clara: almacenamiento, procesos, planner/optimizer, WAL, checkpoints. 
Muy buen primer “internals map”.

Database Internals — Alex Petrov
No es Postgres específico, pero te da fundamentos (LSM/B-Tree, WAL, MVCC, replication) que hacen que el código 
de Postgres tenga mucho más sentido.

Designing Data-Intensive Applications — Martin Kleppmann
Tampoco es Postgres específico, pero es excelente para entender tradeoffs (replicación, particionado, transacciones) 
que aparecen constantemente en discusiones de hackers/committers.

### 08.2 Recursos oficiales

Documentación y recursos “oficiales” para core development

PostgreSQL Developer Documentation
Developer’s Guide y Documentation for Developers (cómo compilar, estilo de código, cómo enviar parches, backpatching, etc.)
Source Code Documentation (comentarios en src/backend, guías de subsistemas)
README y docs dentro del repo En el árbol del código fuente hay documentos clave (según versión):
src/backend/access/transam/README (transacciones / WAL / commit log)
src/backend/storage/README (buffers, lock manager, etc.)
src/backend/optimizer/README (planner/optimizer: fundamental)
src/backend/access/heap/README (heap storage)
src/backend/replication/README (replicación)
src/backend/executor/README (executor)
Estos “README” del repo son de lo más valioso para pasar de teoría a implementación real.

### 08.3 Papers y blogs

https://www.postgresql.org/developer/coding/
https://blog.cleverelephant.ca/2022/10/postgresql-links.html
https://pganalyze.com/blog
https://www.citusdata.com/blog/
https://www.cybertec-postgresql.com/en/postgresql-blog/
https://www.enterprisedb.com/blog
https://rhaas.blogspot.com/ Robert Haas
https://momjian.us/main/blogs/pgblog.html Bruce Momjian
https://www.pgcon.org/
https://www.postgresql.eu/
http://postgresonline.com/
https://planet.postgresql.org/
https://wiki.postgresql.org/wiki/Main_Page
https://www.postgresql.org/docs/books/
https://www.postgis.us/

## 09. Internals Deep Dive

### PostgreSQL Database Objects

Databases:
Each PostgreSQL service houses many individual databases.

Schemas:
Most database objects first belong to a schema, which belongs to a database. When you create a new database, 
PostgreSQL automatically creates a schema named **public** to store objects that you create. If you have few tables, 
using public would be fine. But if you have thousands of tables, you should organize them into different schemas.

Tables:
In PostgreSQL, tables are first citizens of their respective schemas, which in turn are citizens of the database.

Views:
Almost all relational database products offer views as a level of abstraction from tables. In a view, you can query 
multiple tables and present additional derived columns based on complex calculations. Views are generally read-only, 
but PostgreSQL allows you to update the underlying data by updating the view, provided that the view draws from a 
single table.

Extensions:
Extensions allow developers to package functions, data types, casts, custom index types, tables, attribute variables, 
etc., for installation or removal as a unit. You should follow the developer’s instructions on how to install the 
extension files onto your server, which usually involves copying binaries into your PostgreSQL installation folders 
and then running a set of scripts. Once done, you must enable the extension for each database separately.

Functions:
You can program your own custom functions to handle data manipulation, perform complex calculations, or wrap similar 
functionality. Create functions using PLs. PostgreSQL comes stocked with thousands of functions, which you can view in 
the postgres database that is part of every install.

Languages:
Create functions using a PL. PostgreSQL installs three by default: SQL, PL/pgSQL, and C. You can easily install 
additional languages using the extension framework or the CREATE PRODCEDURAL LANGUAGE command. Languages currently 
in vogue are PL/Python, PL/V8 (JavaScript), and PL/R.

Operators:
Operators are nothing more than symbolically named aliases such as = or && for functions. In PostgreSQL, you can 
invent your own. This is often the case when you create custom data types.

Foreign tables and foreign Data Wrappers:
Foreign tables are virtual tables linked to data outside a PostgreSQL database. Once you’ve configured the link, 
you can query them like any other tables. Foreign tables can link to CSV files, a PostgreSQL table on another server, 
a table in a different product such as SQL Server or Oracle, a NoSQL database such as Redis, or even a web service 
such as Twitter or Salesforce. Foreign Data Wrappers (FDW) are the underlying technology that makes foreign tables 
possible. Foreign data wrappers (FDWs) facilitate the magic handshake between PostgreSQL and external data sources. 
FDW implementations in PostgreSQL follow the SQL/Management of External Data (MED) standard.

Triggers and trigger functions:
You will find triggers in all enterprise-level databases; triggers detect data-change events. When PostgreSQL fires 
a trigger, you have the opportunity to execute trigger functions in response. A trigger can run in response to 
particular types of statements or in response to changes to particular rows, and can fire before or after a 
data-change event.

Catalogs:
Catalogs are system schemas that store PostgreSQL builtin functions and metadata. Every database contains two 
catalogs: **pg_catalog**, which holds all functions, tables, system views, casts, and types packaged with PostgreSQL; 
and **information_schema**, which offers views exposing metadata in a format dictated by the ANSI SQL standard. For 
example the most commonly used views in the PostgreSQL information_schema are columns, which list all table columns 
in a database; tables, which list all tables (including views) in a database; and views, which list all views and 
the associated SQL to rebuild the view.

Types:
Type is short for data type. Every database product and every programming language has a set of types that it 
understands: integers, characters, arrays, blobs, etc. PostgreSQL has composite types, which are made up of other types.
Whenever you create a new table, PostgreSQL automatically creates a composite type based on the structure of the table.
This allows you to treat table rows as objects in their own right. You’ll appreciate this automatic type creation when 
you write functions that loop through tables.

Full text search objects:
Full text search (FTS) is a natural language–based search. This kind of search has some “intelligence” built in. 
Unlike regular expression search, FTS can match based on the semantics of an expression, not just its syntactical makeup.

Casts:
Casts prescribe how to convert from one data type to another. They are backed by functions that actually perform 
the conversion. In PostgreSQL, you can create your own casts and override or enhance the default casting behavior.

Sequences:
A sequence controls the autoincrementation of a serial data type. PostgresSQL automatically creates sequences when 
you define a serial column, but you can easily change the initial value, step, and next available value. Because 
sequences are objects in their own right, more than one table can share the same sequence object. This allows you to 
create a unique key value that can span tables

Rules:
Rules are instructions to rewrite an SQL prior to execution.

GUC: 
Is an acronym for Grand Unified Configuration, but it means nothing more than configuration settings in PostgreSQL.

### Main Configuration files
Three main configuration files control operations of a PostgreSQL server:

**postgresql.conf**
Controls general settings, such as memory allocation, default storage location for new databases, the IP addresses 
that PostgreSQL listens on, location of logs, and plenty more.

**pg_hba.conf**
Controls access to the server, dictating which users can log in to which databases, which IP addresses can connect, 
and which authentication scheme to accept.

**pg_ident.conf**
If present, this file maps an authenticated OS login to a PostgreSQL user. People sometimes map the OS root account 
to the PostgresSQL superuser account, postgres.

*Note*: PostgreSQL officially refers to **users as roles**. Not all roles need to have login privileges. For example, 
group roles often do not. **We use the term user to refer to a role with login privileges**.

*Note*: Recuerda como ver la ubicación de estos ficheros en runtime:

```sql
SELECT name, setting FROM pg_settings WHERE category = 'File Locations';
```







1. **Instance**: proceso servidor en ejecucion.
2. **Database cluster**: conjunto de databases servidas por una instancia.
3. **PGDATA**: directorio con los ficheros del cluster.
4. Tras `initdb`, aparecen `template0`, `template1` y `postgres`.
5. **Catalogo**: metadatos en tablas `pg_*`; parte es compartida a nivel cluster.
6. **OID**: identificador de 32 bits usado como PK en muchos catalogos.
7. **Schemas**: namespaces de objetos.
8. Schemas por defecto:
   - `public`
   - `pg_catalog`
   - `information_schema`
   - `pg_toast`
   - `pg_temp`
9. La conexion de cliente trabaja sobre una sola database cada vez.
10. **Tablespaces**: distribucion fisica de datos.
11. Un tablespace puede ser usado por varias databases.
12. Tablespaces por defecto:
   - `pg_default` (`PGDATA/base`)
   - `pg_global` (`PGDATA/global`)
13. Nuevos tablespaces crean enlace simbolico en `PGDATA/pg_tblspc`.
14. **Relations**: tablas, vistas, indices, secuencias, etc.
15. **Files/Forks**:
   - Main: datos principales
   - FSM: espacio libre
   - VM: visibilidad de tuplas
16. Segmentacion de ficheros: por defecto a 1 GB.
17. Ajuste de segment size en build:

```bash
./configure --with-segsize
```

Nota recomendada:

- <https://www.postgresql.fastware.com/blog/how-postgresql-maps-your-tables-into-physical-files>

---

## 10. Notas de codigo fuente

Punto de entrada del backend:

- `src/backend/main/main.c`

```c
int main(int argc, char *argv[]) {
    [...]
    PostmasterMain(argc, argv); /* does not return */
    abort();                    /* should not get here */
}
```

Arranque habitual mediante `pg_ctl`:

- `src/bin/pg_ctl/pg_ctl.c`

```c
int main(int argc, char **argv)
{
    static struct option long_options[] = {
        {"help", no_argument, NULL, '?'},
        {"version", no_argument, NULL, 'V'},
        {"log", required_argument, NULL, 'l'},
        {"mode", required_argument, NULL, 'm'},
        {"pgdata", required_argument, NULL, 'D'},
        {"options", required_argument, NULL, 'o'},
        {"silent", no_argument, NULL, 's'},
        {"timeout", required_argument, NULL, 't'},
        {"core-files", no_argument, NULL, 'c'},
        {"wait", no_argument, NULL, 'w'},
        {"no-wait", no_argument, NULL, 'W'},
        {NULL, 0, NULL, 0}
    };
    [...]
}
```
