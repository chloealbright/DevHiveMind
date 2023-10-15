## Docker

docker run --name containerName -p 5432:5432 -e POSTGRES_PASSWORD=test -d postgres

docker exec -it containerName psql -U postgres



## Create the file repository configuration:

sudo sh -c 'echo "deb [http://apt.postgresql.org/pub/repos/apt](http://apt.postgresql.org/pub/repos/apt) $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'

## Import the repository signing key:

wget --quiet -O - [https://www.postgresql.org/media/keys/ACCC4CF8.asc](https://www.postgresql.org/media/keys/ACCC4CF8.asc) | sudo apt-key add -

## Update the package lists:

sudo apt-get update

# Install the latest version of PostgreSQL.

### If you want a specific version, use 'postgresql-12' or similar instead of 'postgresql':

sudo apt-get -y install postgresql

Copy Script

psql postgres -c "CREATE USER postgres WITH PASSWORD '[post]' SUPERUSER;"




As in all bases the PsorgreSQL comes with a built in system account named also postgres with a user account postgres. Think of this account as the sa account in MS SQL. Postgres account is not configured with a password and therefore it won't be  viable to log into the server  and use  the postgres user account without first creating a password for it.  

# Create the file repository configuratio 

sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list' 

# Import the repository signing key: 

wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add - 

update 

# Install the latest version of PostgreSQL. 

# If you want a specific version, use 'postgresql-12' or similar instead of 'postgresql': 

sudo apt-get -y install postgresql 

pgadmin4 

sudo curl https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo apt-key add 

sudo sh -c 'echo "deb https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update' 

sudo apt install pgadmin4 

psql postgres -c "CREATE USER postgres WITH PASSWORD '[post]' SUPERUSER;" 

PostgreSQL comes with a built in system account named also postgres with a user account postgres. Think of this account as the sa account in MS SQL. Postgres account is not configured with a password and there fore it wont be  viable to log into the server  and use  the postgres user account without first creating a password for it. You need to do the following : 

sudo su -l postgres 

psql 

\password postgres 

CREATE USER jac WITH SUPERUSER CREATEDB CREATEROLE PASSWORD '[pop]'; 

CREATE DATABASE test WITH OWNER andrei; 

CREATE DATABASE 

postgres=# \connect test; 

This will log you in as the postgres user. PostgresSQL comes with a build in command line  server and database management tool called psql. With this you now can access the  server and the databases. The first step is to create a password for the postgres user. This is needed as for security  as well as for later if you need to connect to a GUI management tool. 

postgres=# grant all privileges on database mydb to myuser;



Use single quotes on table insert  values 

@Joshua Carpentier the primary issue with your insert is that TIMESTAMPTZ is a postgres type, not a value. What you want is probably CURRENT_TIMESTAMP, which is a key word that returns the current datetime. You could also do something like '20220730'::TIMESTAMP which type casts a string to a timestamp.





postgresql 

CREATE ROLE jac LOGIN 

sudo -u postgres createuser -s jac 

createdb mydb 

postgres psql 

sudo -u postgres psql 

SELECT jac 

sudo -u postgres psql 

sudo -u postgres dropuser -s jac 

sudo -u postgres dropuser jac 

sudo -u postgres psql 

postgres psql 

psql 

mydb psql 

psql mydb 

createdb Portfolio 

psql Portfolio  

npm install -g npm@6.14.14 

sudo npm install -g npm@6.14.14 

psql Portfolio  

npm install 

npm run resolve 

npm audit 

npm start 

sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list' 

wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add - 

sudo apt-get update 

sudo apt-get -y install postgresql 

postgres 

pg_ctlcluster 

  sudo systemctl start postgresql@13-main 

    pg_ctlcluster 13 main start 

postgresql 

CREATE ROLE jac LOGIN 

sudo -u postgres createuser -s jac 

createdb mydb 

postgres psql 

sudo -u postgres psql 

SELECT jac 

sudo -u postgres psql 

sudo -u postgres dropuser -s jac 

sudo -u postgres dropuser jac 

sudo -u postgres psql 

postgres psql 

psql 

mydb psql 

psql mydb 

createdb Portfolio 

psql Portfolio  

cd frontend/ 

npm install --legacy-peer-deps 

npm audit fix
