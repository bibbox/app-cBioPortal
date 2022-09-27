# cBioPortal BIBBOX application

This container can be installed as [BIBBOX APP](https://bibbox.readthedocs.io/en/latest/ "BIBBOX") or standalone.
 
After the installation follow these [instructions](INSTALL-APP.md)

## Hints
* approx. time with medium fast internet connection: **15 minutes**
* import your data see steps in [instructions](INSTALL-APP.md)


## Install within BIBBOX

Within BIBBOX you can use the [BIBBOX](https://bibbox.readthedocs.io/en/latest/ "BIBBOX") to install a lot of software tools. After the installation is finished you can start your application in the dashboard.

## Docker Images Used
 * [cbioportal/cbioportal](https://hub.docker.com/r/cbioportal/cbioportal), offical cBioPortal container 
 * [mysql](https://hub.docker.com/_/mysql), offical mysql container 
 * [cbioportal/session-service](https://hub.docker.com/r/cbioportal/session-service), offical cBioPortal-session container 
 * [mongo](https://hub.docker.com/_/mongo), offical mongoDB container 
 
## Standalone Installation

To install the app locally execute the commands:
* Clone the git repository: 
  * `git clone https://github.com/bibbox/app-cBioPortal`
* Change the current directory to app-cBioPortal: 
  * `cd app-app-cBioPortal/` 
* Create the docker network `bibbox-default-network`: 
  * `docker network create bibbox-default-network`
* Run **docker-compose up** in the root folder of the project: 
  * `docker-compose up -d`
* **Alternatively** on a *Linux* system run the bash script `intsall.sh` after cloning and change the working directory to the git repository directory.
 

After the installation (might take a few minutes) open **http://localhost:8080** in your browser to access cBioPortal.

## Mounted Volumes
* ./data/cbioportal/study/
* ./data/cbioportal/config/portal.properties
* ./data/cgds.sql
* ./data/seed.sql.gz
* ./data/cbioportal\_mysql\_data
* ./data/cbioportal\_mongo\_data

