The Postgres data folder on Prod host was full, thus we have to move it to another folder.

Following instructions on link, https://www.digitalocean.com/community/tutorials/how-to-move-a-postgresql-data-directory-to-a-new-location-on-ubuntu-16-04

the data directory was successfully moved under /var/snssstools/pgsql/data on Prod host, 

locate  postgresql.conf

#then modify data_directory with vi in the conf file
vi /<file_path>/postgresql.conf

data_directory = '/var/snssstools/pgsql/data' 

the only catch you is two config files need to be modified besides the one mentioned in link, 

verify the file /usr/lib/systemd/system/postgresql.service , make sure PGDATA is set to new data directory as below,

#Location of database directory
Environment=PGDATA=/var/snssstools/pgsql/data
then restart postgres service with

systemctl daemon-reload
sudo systemctl restart postgresql

#then double check data directory with 
service postgresql status

...
├─18660 /usr/bin/postgres -D /var/snssstools/pgsql/data -p 5432

...
