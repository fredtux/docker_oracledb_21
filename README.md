# Docker container for Oracle Database 21c
This project uses code from: [https://github.com/oracle/docker-images/tree/main/OracleDatabase/SingleInstance](https://github.com/oracle/docker-images/tree/main/OracleDatabase/SingleInstance)

In addition it uses **docker-compose** for a more streamlined experience

# Installation
## Step 1
Get the Linux x86-64 **zip** of Oracle Database **21c** from [Oracle Database Software Downloads](https://www.oracle.com/database/technologies/oracle-database-software-downloads.html)

Place the **LINUX.X64_213000_db_home.zip** file in the **21.0.3** folder

## Step 2
Build the docker image using
```bash
./buildContainerImage.sh -v 21.3.0 -t docker_oracledb_21 -s -i
```

## Step 3
Start the container. When it's run the first time wait for the database to be configured
```bash
docker-compose up
```

## Step 4
Connect using the static IP **172.20.128.2** on port **1521** with the SID **ORCLCDB** username **SYSTEM** and password **fmilove**

# Daily usage
Spun up the container using
```bash
docker-compose up
```

# Miscellaneous
## Change password
Use this command
```bash
docker exec docker_oracledb_21 ./setPassword.sh <your password>
```

## Use sqlplus from inside the container
Enter the container using 
```bash
docker exec -it docker_oracledb_21 /bin/bash
```
Connect using sqlplus
```bash
sqlplus / as sysdba
```
