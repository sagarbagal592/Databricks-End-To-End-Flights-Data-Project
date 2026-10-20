# Databricks Setup
- We are using Databricks free edition to complete this project.
- Databricks UI is so advance that we can create catalog, schema and volume just by clicking, but here we learn how to create-update-delete them using code.

## Catalog
```sql
--- Creating Catalog

create catalog catalog_name;

--- Delete Catalog

drop catalog if exists catalog_name cascade;

cascade delete entire catalog with its schema, child objects

drop catalog if exists catalog_name restrict;

restrict will delete only empty catalog

```
## Schema
```sql
-- Creating Schema

create schema catalog.schema_name;

-- Deleting schema

drop schema if exists schema_name cascade/restrict
```
## Volume
```sql
---Creating volume

create volume catalog.schema.volume_name;

---Renaming volume

alter volume catalog.schema.volume_name
rename to new_volume;


---Deleting volume

drop volume catalog.schema.volume_name
```
## directory
```py
---Creating Directory

dbutils.fs.mkdirs("/Volumes/my_catalog/my_schema/my_volume/directory_name")

--Rename a directory

dbutils.fs.mv("path","path with new name", recurse = True)

--Delete Directory

dbutils.fs.rm("path",recurse = True)
```