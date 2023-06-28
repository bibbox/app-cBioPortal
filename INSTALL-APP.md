## cBioPortal Installation Instructions 

### cBioPortal

Be patient this can take a while.

### When you start this the first time only one demo data et is loaded

![Screenshot01](assets/install-screen-01.png)


### You can check the demo data set by selecting it an clicking on Explore Selected Studies

![Screenshot02](assets/install-screen-02.png)


#### Exploring Studies
A overview summary is presented when studies are expolred

![Screenshot03](assets/install-screen-03.png)

### Upload your own data

To upload your own data perform the following steps:

* Upload your data to the BIBBOX-Server into the `<instantce_name>/data/cbioportal/study` folder (e.g. via fileZilla ask your server administor for access)
* Connect to your BIBBOX server via `ssh`
* Perform the following commands:
  * `cd /opt/bibbox/instances/<instance_name>`
  * `docker exec <instance_name>-cbioportal-container metaImport.py -u http://localhost:8080 -s /study/<study_name>/ -o`
  * Depending on the data set you might need to import the gene panel first:
    * `docker exec <instance_name>-cbioportal-container bash -c 'cd /cbioportal/core/src/main/scripts/ && ./importGenePanel.pl --data /gene_panels/gene_panel.txt`


## After the installation
Have a nice ride with the Admins youngtimer.

![FINAL](assets/install-screen-final.jpg)
