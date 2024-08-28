# Overview 

## Components of helm charts

### Chart.yml 

### Chart.lock (generated automatically) 

#### _helper.tpl 

  * Not considered, parsed a manifests 
  * Hold snippets (named templates) can be included with "include" (Preferred) or "template"
  * Best practice: name of named template with  define ChartName.Property z.B. botti.fullname 

#### NOTES.txt 

  * is shown, after installation of chart with helm install 
    * or: with helm get notes 
   
```
# after installation
# helm install my-botti -n my-application --create-namespace botti
helm get -n my-application notes my-botti
```

### charts/

  * Hier dependencies are downloaded which are given in Charts.yml 


