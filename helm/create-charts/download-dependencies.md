# Download Dependencies 

## Voraussetzung: 

  * Dependencies are in Chart.yml  
  * Achtung: Version ist the version of the chart not the App !!! 

## The first time 

```
# 1. All dependencies are downloaded as .tgz - archives 
     -> into the chart folder 
# 2. Eine Chart.lock - datei wird erstellt. (hält den aktuellen Stand fest)
# helm dependancy update $CHART_PATH
# Explained beneath in the Walkthrough 
helm dependancy update botti 
```

## The 2. time (if Chart.lock is there, but charts/ does not need to be there  

```
helm dependancy build botti 
```

## List all dependencies 

```
helm dependancy list botti
```


## Walkthrough 

```
cd
helm create botti
```

```
cd botti
# add dependency
nano Chart.yml
```

```
# at the end of the file add

# After that save and exit STRG + O + ENTER , STRG  + X
```

```
# Update to download depdendancies 
cd ..
helm dependency update botti 
cd botti/charts
ls -la
cd ../../
```

```
# Add repo to be able to do helm dependency build
rm -fR botti/charts
# Chart.lock needs to be there
ls -la botti/Chart.lock

# Add repo / needs to be there, otherwice 
helm repo add bitnami https://charts.bitnami.com/bitnami
helm dependency build botti
```
