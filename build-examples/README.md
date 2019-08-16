# Build Config Types

### Prerequisites
- login as you developer user
- create your own project

### Example:
#### Use `developer/developer` credentials:
```
oc login
oc new-project testproject
oc project testproject
```

## Docker Build
#### Creation Steps:
##### Create our resources:
```
oc create -f docker.yaml
```
##### Wait until our build will be completed:
```
oc get build
```
##### Run our build:
```
oc start-build docker-build
```
##### Check that our build is ok: 
```
oc get build
```

## Pipeline Build
#### Novice Creation Steps:

##### Make the Docker Build without two last steps.

##### Create our resources:
```
oc create -f pipeline-novice.yaml
```
##### Wait until our build will be completed:
```
oc get build
```
##### Run our build:
```
oc start-build pipeline-novice-build
```
##### Check that our build is ok: 
```
oc get build
```

#### Intermediate and Advanced Creation Steps:
##### Create our resources:
 ```
oc create -f pipeline-intermediate.yaml / oc create -f pipeline-advanced.yaml
```
##### Wait until our build will be completed:
```
oc get build
```
##### Run our build:
```
oc start-build pipeline-intermediate-build / oc start-build pipeline-advanced-build
```
##### Check that our build is ok: 
```
oc get build
```

## Custom Build 
By default Custom Build Type is turned off for authenticated users and we have to update policy for them:
```
oc login -u system:admin
oc policy add-role-to-group system:build-strategy-custom system:authenticated
oc policy who-can create builds/custom
```
 
If we want to clean:
```
oc policy remove-role-from-group system:build-strategy-custom system:authenticated
```
 
#### Creation Steps:
##### Create our resources: 
```
oc create -f custom.yaml
```
##### Wait until our build will be completed:
```
oc get build
```
##### Run our build:
```
oc start-build custom-build
```
##### Creation Check that our build is ok: 
```
oc get build
```