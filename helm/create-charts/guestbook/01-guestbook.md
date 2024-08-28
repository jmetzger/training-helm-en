# Create our first helm chart 

## Step 1: Create namespace and structure of helm chart 

```
cd
```

```
helm create guestbook
# now we have in folder "guestbook" 
# charts/
# Chart.yaml
# templates
# values.yaml 
```

## Step 2: Explore templates folder and cleanup 

```
cd templates
ls -la
rm -fR tests
```

## Step 3: Explore the Chart.yaml 

```
cd ..
cat Chart.yaml
```

```
# type: Application or Library # please explain !
# dependencies - what other charts are needed - we will download them by helm command and they will be put in the charts - folder
```

## Step 4: Add redis as dependency 

```
# find the redis chart 
helm search hub --max-col-width=0  redis | grep bitnami
# adding the repo for bitnami
helm repo add bitnami https://charts.bitnami.com/bitnami
```

```
# now find the availabe versions (these are the chart versions
helm search repo redis --versions
```

```
nano Chart.yaml
```

```
# now add the dependency-block at the end of the file
dependencies:
  - name: redis
    version: "17.14.x"  # quotes are important here
    repository: https://charts.bitnami.com/bitnami
```

```
# Save the file and leave nano:
STRG + o + RETURN -> then -> STRG + x
```

```
cd ..
helm dependency update guestbook
```

```
# explore the newly populated folder
cd guestbook/charts
ls -la
cd ../..
```

## Step 5: Modifying the values.yaml file 

```
# the version might have changed since i wrote this / adjust
helm show values charts/redis-17.14.5.tgz
# what are the service name of the redis leader and the redis follower
helm show values charts/redis-17.14.5.tgz | grep -B 4 -i fullnameoverride
```

```
# the service names need to be adjusted, add the following to the values.yaml
# The guestbook - application needs the redis - services called. redis-leader and redis-follower
```

```
cd
cd guestbook
nano values.yaml
```

```
# add at the end of the file
redis:
  fullnameOverride: redis

# enable unauthorized access to redis
  usePassword: false
# Disable AOF persistence
  configmap: |-
    appendonly no 
```

```
# save file and exit
STRG + o + ENTER -> then -> STRG + x 
```

```
# now check, if this really worked
cd
cd guestbook 
helm template . | grep -A 20 master/service
```

## Setting the right repo and the right version 

```
cd
cd guestbook
cat templates/deployment.yaml
```

```
# Which version do it need ? 
https://kubernetes.io/docs/tutorials/stateless-application/guestbook/#creating-the-guestbook-frontend-deployment
# Stand 2023-08-08
gcr.io/google_samples/gb-frontend:v5
```

```
# nano Chart.yaml 
# korrigieren
appVersion: "v5"
```

```
# nano values.yaml
image:
  repository: gcr.io/google_samples/gb-frontend
``` 

## Step 6: Changing LoadBalancer to NodePort 

```
# nano values.yaml 
service:
  type: NodePort
  port: 80 
```

## Step 7: Installing helm chart 

```
helm install my-guestbook guestbook -n jochen --create-namespace
kubectl -n jochen get all 

```


## Reference:

  * https://kubernetes.io/docs/tutorials/stateless-application/guestbook/
