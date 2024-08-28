# Search in Repos and in Hub 

## Search in hub

```
helm search hub mariadb
# Show complete lines without cutting it of 
helm search hub mariadb --max-col-width=0
```

## Search in Repo 

```
# Search for all charts, that have mariadb in name or description 
helm search repo mariadb

# Show all versions of charts, that start with bitnami/mariadb 
helm search repo bitnami/mariadb --versions
```
