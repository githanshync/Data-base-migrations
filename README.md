# Data Base Sql Server migration.
# Example to migrate SQL Server tables.
## Minimum requirements:

- Visual Studio 2019 (import the solution Data-base-migrations).

- SQL Server 2017 or SQL Server Express 2017 (source database - target database).

- Download WideWorldImporters-Full.bak backup of sample database "WideWorldImporters" and restore into source server:
https://github.com/Microsoft/sql-server-samples/releases/tag/wide-world-importers-v1.0

## To run the ssis package.

In the source database with user sa:

- Create login sou_user1 with privilege "db_datareader" on the sample database "WideWorldImporters".

In the target database with user sa:

- Create the "Destiny" database.

- Copy the tables (without data) from "WideWorldImporters" to "Destiny": Application.dbo.cities, Application.dbo.cities_archive, Application.dbo.countries and Application.dbo.countries_archive.

- Create login des_user1 and grant the "db_datareader" and "db_datawriter" privileges on the "Destiny" database.

- Grant the user des_user1 "Alter" privilege on the newly created tables in the "Destiny" database.

## In the Visual Studio project:

- In connection manager Update "Server or file name" field with your server name or ip and instance (source database - target database): [SERVER1]\[MSSQLSERVER]
 
- And update the passwords created for sou_user1 and des_user1 in the connection manager.
