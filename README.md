# cBioPortal BIBBOX application

This container can be installed as [BIBBOX APP](https://bibbox.readthedocs.io/en/latest/ "BIBBOX App Store") or standalone. 

After the docker installation follow these [instructions](INSTALL-APP.md).

## Standalone Installation 

Clone the github repository. If necessary change the ports in the environment file `.env` and the volume mounts in `docker-compose.yml`.

```
git clone https://github.com/bibbox/app-cBioPortal
cd app-cBioPortal
docker network create bibbox-default-network
docker-compose up -d
```

The main App can be opened and set up at:
```
http://localhost:8080
```

## Install within BIBBOX

Visit the BIBBOX page and find the App by its name in the store. Click on the symbol and select install. Then fill the parameters below and name your App, click install again.

## Docker Images used
  - [cbioportal/cbioportal](https://hub.docker.com/r/cbioportal/cbioportal) 
  - [mysql](https://hub.docker.com/r/mysql) 
  - [cbioportal/session-service](https://hub.docker.com/r/cbioportal/session-service) 
  - [mongo](https://hub.docker.com/r/mongo) 


 
## Install Environment Variables

  
The default values for the standalone installation are:

  
## Mounted Volumes
### cbioportal/cbioportal Conatiner
  - *./data/cbioportal/study:/study/*
  - *./data/cbioportal/config/portal.properties:/cbioportal/portal.properties:ro*
### mysql Conatiner
  - *./data/cgds.sql:/docker-entrypoint-initdb.d/cgds.sql:ro*
  - *./data/seed.sql.gz:/docker-entrypoint-initdb.d/seed.sql.gz:ro*
  - *./data/cbioportal_mysql_data:/var/lib/mysql*
### mongo Conatiner
  - *./data/cbioportal_mongo_data:/data/db*

