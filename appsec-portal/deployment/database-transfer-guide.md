---
description: >-
  By following the steps outlined in this guide, you can safely and effectively
  transfer the AppSec Portal's database to a new host
---

# Database transfer guide

This guide outlines the steps to transfer a database using Docker and various commands. The process involves creating a database dump, transferring it to a remote server, and restoring it in a new container. If you have changed the default values for DB\_USERNAME and DB\_NAME, make sure to use your custom values in the commands provided below. Otherwise, the values of _**postgres**_ should be used for both.

### Step 1: Preparing the New Host

Before transferring the database to the new host, ensure that the AppSec Portal is [installed](installation.md) and properly set up on new host. Follow the steps below to prepare the new host for the database migration:

1. Ensure that the AppSec Portal configuration is correctly set up on the new host, including database connection parameters. If the DB\_USERNAME and DB\_NAME was changed during the setup, make sure to use the custom values in the configuration.
2. Drop the Existing Database Inside the container, execute the following command to drop the existing database:

```
docker exec -i appsec-portal_postgres_1 dropdb -U <DB_USERNAME> <DB_NAME>
```

3. Create a New Database. While still inside the container, create a new database with the same name using the following command:

```
docker exec -i appsec-portal_postgres_1 createdb -U <DB_USERNAME> <DB_NAME>
```

### Step 2: Create a Database Dump on the Current Host

1. Open a terminal or command prompt. Navigate to the directory where you want to create the database dump file.

```
cd /path/to/destination_directory
```

2. Execute the following command to create a database dump from the current host:

```
docker exec -i appsec-portal_postgres_1 pg_dump -U <DB_USERNAME> <DB_NAME> > pg_dump
```

The pg\_dump file will be created in the previously specified directory.

### Step 3: Transfer the Database Dump to the New Host

Copy the database dump file (pg\_dump) to the new host using a secure method, such as SCP (Secure Copy) or any other file transfer mechanism you prefer.

### Step 4: Restore the Database on the New Host

1. Once the database dump file is on the new host, open a terminal or command prompt on the new host. Navigate to the directory where the database dump file is located.

```
cd /path/to/source_directory
```

2. Copy the database dump file into the appsec-portal\_postgres\_1 container on the new host:

```
docker cp pg_dump appsec-portal_postgres_1:/pg_dump
```

3. Restore the database from the dump on the new host inside the container:

```
docker exec -it appsec-portal_postgres_1 psql -U <DB_USERNAME> -d <DB_NAME> -f /pg_dump
```

Congratulations! You have successfully transferred the database.

{% hint style="info" %}
You can also use this guide to restore the database from a backup by skipping steps 2 and 3.
{% endhint %}
