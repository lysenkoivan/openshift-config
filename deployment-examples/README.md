# Deployment

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

## Simple Deployment
#### Create our resources:
```
oc create -f simple-app.yml
```

## Auto scaling Deployment
#### Create our resources:
```
oc create -f autoscaling-app.yml
```

### Testing Deployments Steps:
##### Go to `/auth` to get token.
##### Go to `/unprotected` and check the access.
##### Go to `/protected?token=<token>` and check the access.
##### Go to `/memory-usage/<memories_mb>?time=<seconds>` to check high availability or auto scaling by memory usage.
##### Go to `/cpu-usage/<cores_number>?time=<seconds>` to check  high availability or auto scaling by cpu usage.

