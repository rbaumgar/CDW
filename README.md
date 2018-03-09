# CDW
CDW: Connect the data of the world

The project  is for running the KAPUA project on Openshift.

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

## Tested on MiniShift/CDK
minishift v1.11.0+d7f374a
CDK v3.3.0-1

