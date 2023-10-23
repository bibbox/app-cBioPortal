# cBioPortal Installation Instructions 

Since the application can be installed within the BIBBOX or as stand-alone solution, you can find the install instructions within the BIBBOX, followed by the setup instructions, which will be needed after the application was successfully installed.


## Installation within in the BIBBOX

After you have chosen the App, which you would like to use as BIBBOX instance, you can chose between the available versions, as it is shown in the following figure.

figure xx

With the click on install a new window appears. which is illustrated in fiugre yy. You can define required entries. Some fields are pre-filled with entries that are suggested as possible options. If these fields are not refilled, these default values will be adopted as the associated entry.

figure yy

After confirming by clicking on install, the App will be installed as a BIBBOX instance.
When the installation is complete, you only need a few steps to use the APP for the first time, which are described below.

## Setup after BIBBOX or stand-alone installation

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
