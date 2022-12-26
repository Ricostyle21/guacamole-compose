# guacamole-compose

Docker Compose yml file for running Apache Guacamole with PostgreSQL 14.2 in 1 stack.

# Apache Guacamole with docker-compose
Apache Guacamole is a clientless remote desktop gateway. It supports standard protocols like VNC, RDP, and SSH. For more information: 
http://guacamole.apache.org/
https://hub.docker.com/r/guacamole/guacamole

## Quickstart
```
git clone https://gitlab.com/Ricostyle21/guacamole-compose.git
cd docker-guacamole/
docker-compose up -d
```
Your guacamole server should be available at `http://HOST_IP:8080/guacamole`. The default username is `guacadmin` with password `guacadmin`. This user should be cloned, and deleted immediately.

#### To shutdown Guacamole server:
```
docker-compose down
```
#### To reset/delete Guacamole data (database)
```
rm -rf '/home/$USER/dockerdata/guacamole/postgres/data'
```
---
#### Notes:
An `initdb.sql` file needs to be created as per https://guacamole.apache.org/doc/gug/guacamole-docker.html.
Run the following code to generate the file:
```
docker run --rm guacamole/guacamole /opt/guacamole/bin/initdb.sh --postgres > /home/$USER/dockerdata/guacamole/postgres/init/initdb.sql
```
