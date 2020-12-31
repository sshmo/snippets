# Installation
  
  # 
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


# pip install psycopg2 - error: command 'x86_64-linux-gnu-gcc' failed with exit status 1 [duplicate]

  sudo apt install libpq-dev
  pip3 install psycopg2
  
  
