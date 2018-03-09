# CDW
CDW: Connect the data of the world

The project  is for running the KAPUA project on Openshift.

## Presentation
see https://docs.google.com/presentation/d/1rskg76deerSPSr-z_j7XmmDLDvp7EZdHuil0hgSzR8M/edit#slide=id.p

## Installation

    oc create new-project kapua
    oc create -f kapua-template.yaml
    oc process --parameters kapua-template
    oc process  kapua-template |oc create -f -
or

    oc process  kapua-template -p ELASTIC_SEARCH_MEMORY=512m |oc create -f -

5 pods will be created an started. Wait util they are running.

## Access
### Console
The console can be accessed at the url of the kapua-console.

    oc get route kapua-console
   
login with kapua-sys/kapua-password
### API
The API can be accessed at the the url of the kapua-api.

    oc get route kapua-api
   
access the url by append /doc.

### MQTT
The MQTT can be accessed at the url of the kapua-broker.

    oc get route kapua-broker
   
This is a WebSocket interface!!!

## Contributor
Robert Baumgartner, Ingo Boering, Oliver Horn. Started at the SA Hackathon, Brno, Mar 8-9, 2018

## Open Tasks

### Scaling
test how scaling works with KAPUA on OpenShift

### use MariaDB
Currently only H2 database works for KAPUA, because the MySQL/MariaDB driver is not available on the KAPUA images.

Setup done with the following paramters:
* commons.db.name=$MYSQL_NAME / sampledb
* commons.db.username=$MYSQL_USER / user
* commons.db.password=$MYSQL_PASSWORD /password
* commons.db.jdbcConnectionUrlResolver=mariadb / MariaDB
* commons.db.jdbc.driver=org.mariadb.jdbc.Driver
* commons.db.connection.scheme=jdbc:mariab

see https://github.com/eclipse/kapua/issues/1498

## Tested on 
* minishift v1.11.0+d7f374a
* CDK v3.3.0-1
* OpenShift CDK 3.7.23
