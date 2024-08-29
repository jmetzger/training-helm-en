# Mariadb 

## Install 

```
cd 
chmod g-r,o-r .kube/config
helm repo add bitnami https://charts.bitnami.com/bitnami
helm -n jochen2 install my-mariadb bitnami/mariadb --version 19.0.5 --create-namespace
```

```
# OR: upgrade and if not install -> install 
helm -n jochen2 upgrade my-mariadb bitnami/mariadb --install --version 19.0.5 --create-namespace
```

## Upgrade to primary / secondary 

```
cd
mkdir manifests
cd manifests/
mkdir mariadb-release
cd mariadb-release 
echo "archtitecture: replication" > values.yaml

```

```
architecture: replication
auth:
  rootPassword: zfGb7nFsMZ
  replicationPassword: myreplication
  forcePassword: true
```

