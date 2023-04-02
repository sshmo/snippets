# Installation
  
  [Ubuntu 20.04 PostgreSQL Installation](https://linuxconfig.org/ubuntu-20-04-postgresql-installation)
  
    sudo apt-get update
    
    sudo apt-get install libpq-dev
    
    sudo apt install postgresql-client
    which psql
    usr/bin/psql

    sudo apt install postgresql
    which pg_config
    usr/bin/pg_config

    sudo service postgresql start
    * Starting PostgreSQL 12 database server

    sudo service postgresql status
    12/main (port 5432): online

    ss -nlt
    State            Recv-Q            Send-Q                       Local Address:Port                       Peer Address:Port           Process
    LISTEN           0                 128                              127.0.0.1:5432                            0.0.0.0:*

# Create a db

  [How To Use PostgreSQL with your Django Application on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-use-postgresql-with-your-django-application-on-ubuntu-14-04)
  
    sudo su - postgres

    psql

    CREATE DATABASE product_db;

    CREATE USER product_user WITH PASSWORD 'password';
    
    ALTER USER product_user CREATEDB; # for running tests

    ALTER ROLE myprojectuser SET client_encoding TO 'utf8';
    ALTER ROLE myprojectuser SET default_transaction_isolation TO 'read committed';
    ALTER ROLE myprojectuser SET timezone TO 'UTC';

    GRANT ALL PRIVILEGES ON DATABASE product_db TO product_user

    /q

    exit

    # checking a db via localhost
    psql -U someuser -h 127.0.0.1 database

    \list or \l: list all databases
    \dt: list all tables in the current database using your search_path
    \dt *.: list all tables in the current database regardless your search_path
    \l+: list all databases and shows the disk usage as well


# pip install psycopg2 - error: command 'x86_64-linux-gnu-gcc' failed with exit status 1 [duplicate]

    sudo apt install libpq-dev
    pip3 install psycopg2
  
# Creating test database for alias 'default'... Got an error creating the test database: permission denied to create database
  
    # In database creation add folloing:
    ALTER USER product_user CREATEDB; # for running tests
  
