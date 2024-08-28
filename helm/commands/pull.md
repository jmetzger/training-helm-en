# Download Chart und eventually untar it (also a specific version) 

```
# First we need to set the repo - entry 
helm repo add bitnami https://charts.bitnami.com/bitnami 

# download the latest availabe chart 
helm pull bitnami/mariadb

# Downloads a specific version 
helm pull bitnami/mariadb --version 12.1.6
# untar it if wanted 
# tar xvf mariadb-12.1.6.tgz

# Quick version 
helm pull bitnami/mariadb --version 12.1.6 --untar
```
