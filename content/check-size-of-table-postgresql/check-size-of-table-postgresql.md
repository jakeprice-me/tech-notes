---
aliases:
  - check-size-of-table-postgresql
archive_links: 
category: postgresql
classification: public
date: 2020-09-22T12:50:20
date_modified: 2020-09-22T12:50:20
draft: false
id: 20200922125020
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [postgresql, psql, tables, size, database]
title: Check Size of a Table in PostgreSQL
type: tech-note
---

To get an overview of how much space is taken by each table in a database.

```sh
psql --host=<host> --dbname=<dbname> --username=<username> --command='SELECT relname as "Table", pg_size_pretty(pg_total_relation_size(relid)) As "Size", pg_size_pretty(pg_total_relation_size(relid) - pg_relation_size(relid)) as "External Size" FROM pg_catalog.pg_statio_user_tables ORDER BY pg_total_relation_size(relid) DESC;'
```

The SQL above, in a prettier format looks like this:

```sql
SELECT
   relname as "Table",
   pg_size_pretty(pg_total_relation_size(relid)) As "Size",
   pg_size_pretty(pg_total_relation_size(relid) - pg_relation_size(relid)) as "External Size"
   FROM pg_catalog.pg_statio_user_tables ORDER BY pg_total_relation_size(relid) DESC;
```

Get the size of all objects:

```sh
psql --host=<host> --dbname=<dbname> --username=<username> --command='SELECT relname AS objectname, relkind AS objecttype, reltuples AS "#entries", pg_size_pretty(relpages::bigint*8*1024) AS size FROM pg_class WHERE relpages >= 8 ORDER BY relpages DESC;' > db_table_object_size.txt
```

Again, the SQL, in a prettier format:

```sql
SELECT
   relname AS objectname,
   relkind AS objecttype,
   reltuples AS "#entries", pg_size_pretty(relpages::bigint*8*1024) AS size
   FROM pg_class
   WHERE relpages >= 8
   ORDER BY relpages DESC;
```