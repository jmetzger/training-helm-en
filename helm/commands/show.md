# Show information from a chart 

```
helm show values bitnami/mariadb
helm show values bitnami/mariadb | grep -B 20 -i "image:"
```

```
# Show Chart-Definitions, Readme a.s.o. (=everything) - templates are missing / but saved in data in etcd  
helm show all bitnami/mariadb 
```

```
helm show readme
helm show readme bitnami/mariadb
helm show chart bitnami/mariadb
```

