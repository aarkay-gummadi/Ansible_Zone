```yaml
---
pool:
  name: "Azure Pipelines"
  vmImage: ubuntu-18.04

trigger:
  - master

steps:
  - task: Maven@3
    inputs:
      mavenPomFile: 'pom.xml'
      goals: 'package'
      publishJUnitResults: true
      testResultsFiles: '**/surefire-reports/TEST-*.xml'
      jdkVersionOptions: '1.8'
```


```yaml
---
pool:
  name: Azure Pipelines
  vmImage: ubuntu-22.04

trigger:
  - main

steps:
  - task: Maven@3
    inputs:
      mavenPomFile: 'pom.xml'
      goals: 'package'
      publishJUnitResults: true
      testResultsFiles: '**/surefire-reports/TEST-*.xml'
      jdkVersionOptions: '1.17'
```


* If you observe the above two cases
* Azure Devops allows us to reuse using templates

Azure Pipeline Templates
----------------------------

* [refer here](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/templates?view=azure-devops) for the official docs
* We have created our first reusable template in templates folder
* Now lets create a reusable steps 








Afternoon 
---------






### Reusable Job and stage Templates

Service Connections
-------------------

* Azure Devops Service connections

Extensions
-------------

* Extensions in Azure DevOps are additional functionality provided by community.


Handling Artifacts
-------------------

* How to archive build artifacts
* Azure DevOps has a task to copy the artifact 



* The work done so far is copied to folder. To download the published artifact we have a task


* To store artifacts we have special softwares such as nexus, jfrog etc. Azure DevOps offers Azure Artifacts for the same purpose
* Azure Artifacts
* used goal deploy
* Azure Artifacts deploy (Lets see this tomorrow)

* Next Steps:
    * Releases and Release Pipelines
    * Secrets
    * Code, Docker and k8s Scan (DevSecOps on Azure DevOps Pipelines)
    * Azure Artifacts for maven