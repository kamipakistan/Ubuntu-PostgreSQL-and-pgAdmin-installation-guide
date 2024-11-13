# PostgreSQL and pgAdmin Setup Script for Ubuntu

Welcome to the PostgreSQL and pgAdmin setup script! This script will guide you through the installation of PostgreSQL, user and database configuration, and the installation of pgAdmin using the official repository.

## Introduction

PostgreSQL is a powerful open-source relational database management system, and pgAdmin is a popular administration and management tool for PostgreSQL. This script simplifies the process of setting up PostgreSQL and pgAdmin on your Ubuntu system.

To install PostgreSQL and pgAdmin4 on Ubuntu, you can follow these steps:
## 1. Install PostgreSQL:
Open a terminal and run the following commands:

```bash
sudo apt update
sudo apt install postgresql postgresql-contrib
```
This will install the PostgreSQL database server and additional contrib packages.

## 2. Start and Enable PostgreSQL:
After installation, PostgreSQL should start automatically. You can check its status with:

```bash
sudo systemctl status postgresql
```
If it's not running, you can start it with:

```bash
sudo systemctl start postgresql
```
You can also enable it to start on boot:

```bash
sudo systemctl enable postgresql
```

## 3. Set up a PostgreSQL User and Database:
By default, PostgreSQL creates a user named `postgres`. You can switch to this user and access the PostgreSQL command prompt:

```bash
sudo -u postgres psql
```
Inside the PostgreSQL prompt, you can `Reset` PostgreSQL User `Password` and create a `new_user` and a `database`:

### a. Reset PostgreSQL User Password
If needed, you can reset the password for a PostgreSQL user using the `ALTER USER` command. Replace `username` and `new_password` with your desired values.

```bash
psql -U postgres
ALTER USER username WITH PASSWORD 'new_password';
\q
```
Remember to replace "username" and "new_password" with the actual values.

### b. Create a New PostgreSQL User and Database
You can choose to create a new PostgreSQL user and database using the following commands. This step is optional.

```bash
sudo -u postgres psql
CREATE USER your_username WITH PASSWORD 'your_password';
CREATE DATABASE your_database;
GRANT ALL PRIVILEGES ON DATABASE your_database TO your_username;
\q
```
Replace `your_username` with the desired username and `your_password` with the desired password.


## 4. Install pgAdmin using the Official Repository
a. **Setup the repository**
 
Install the public key for the repository (if not done previously):
```
curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg
```
Create the repository configuration file:
```
sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
```
b. **Install pgAdmin**

Install for both desktop and web modes:
```
sudo apt install pgadmin4
```
Install for desktop mode only
```
sudo apt install pgadmin4-desktop
```
Install for desktop mode only:
```
sudo apt install pgadmin4-desktop
```

Install for web mode only: 
```
sudo apt install pgadmin4-web 
```
Configure the webserver, if you installed pgadmin4-web:
```
sudo /usr/pgadmin4/bin/setup-web.sh
```
That's it! You've successfully set up PostgreSQL and pgAdmin on your Ubuntu system. Feel free to customize and use this script according to your needs.
