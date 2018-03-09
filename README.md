# CDW
CDW: Connect the data of the world

The project  is for running the KAPUA project on Openshift.

## Installation
'''
oc create new-project kapua
oc create -f kapua-template.yaml


## Contributor
Robert Baumgartner
Ingo Boering
Oliver Horn

## Open Tasks

### Scaling
test how scaling works

### use MariaDB
Currently only H2 database works for KAPUA, because the MySQL/MariaDB driver is not available on the KAPUA images.

## Tested on MiniShift/CDK
minishift v1.11.0+d7f374a
CDK v3.3.0-1

