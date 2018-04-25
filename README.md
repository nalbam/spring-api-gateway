# spring-api-gateway

## Docker
```
PORT=8081
PROFILE=default
CONFIG_SERVER_HOST=localhost
CONFIG_SERVER_PORT=8888
```

## Openshift
### Creating a project
```
oc new-project sample --display-name="Sample" --description="Sample Project"
oc project sample
```

### Creating new apps
```
oc new-app -f https://raw.githubusercontent.com/nalbam/spring-api-gateway/master/openshift/templates/spring.json \
           -e PROFILE=dev -e CONFIG_SERVER_HOST=config-server -e CONFIG_SERVER_PORT=8888
```

### Creating new pipeline
```
oc create -f https://raw.githubusercontent.com/nalbam/spring-api-gateway/master/openshift/templates/pipeline.yaml
```
