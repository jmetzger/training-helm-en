# Commands 

## Installation 

```
helm repo add bitnami https://charts.bitnami.com/bitnami 
helm -n jochen2 install my-mariadb bitnami/mariadb --version 19.0.5 --create-namespace
helm -n jochen2 upgrade my-mariadb bitnami/mariadb --install --version 19.0.5 --create-namespace
```

## After installation 

```
# show all realeases 
helm -n jochen list
# all namespaces 
helm list -A
```

```
# get specific information from release
# use value file (if there was one)
helm -n jochen get values my-mariadb
helm -n jochen get notes my-mariadb
helm -n jochen get manifest my-mariadb
```

## Communicating with chart 

```
helm show values bitnami/mariadb 
```


# helm repo commands 

```
helm repo list 
helm repo add bitnami https://charts.bitnami.com/bitnami 
helm repo remove bitnami 
helm repo update
```

## See all versions of a chart 

```
helm search repo mariadb -l
```
