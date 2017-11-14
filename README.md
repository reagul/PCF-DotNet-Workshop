# PCF-DotNet-Workshop

## Pivotal Cloud Native Applications .NET Workshop
This one day hands-on classroom style session will provide developers with hands on experience building .NET Core and .NET 4.6 applications for Pivotal Cloud Foundry. The session includes presentations, demos and hands on labs.

- ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Proxy issues while connecting to your PCF endpoint:  ![#f03c15](https://placehold.it/15/f03c15/000000?text=+)

You may need to follow these instructions here to set your proxy settings for the CLI: [Using the cf CLI with an HTTP Proxy Server](https://docs.cloudfoundry.org/cf-cli/http-proxy.html).
- - - 
#### Pre-Req

PCF Developer Account 

- Valid Pivotal Cloud Foundry Developer Account ** Find it on your Confluence Wiki **
- We have one for you. https://apps.run.haas-161.pez.pivotal.io/

Visual Studio 

- [Download Visual Studio 2017 Community Edition](https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15)
- [Download Visual Studio 2017 for Mac here ]( https://www.visualstudio.com/vs/visual-studio-mac/ ) 
- [Download Visual Studio Code](https://code.visualstudio.com/?wt.mc_id=vscom_downloads)

CF CLI 
- [Download Windows Cloud Foundry CLI](https://cli.run.pivotal.io/stable?release=windows64&source=github)
- [Download Mac Cloud Foundry CLI](https://cli.run.pivotal.io/stable?release=macosx64-binary&source=github)

- - -
#### Agenda


##### Session: Introductions, Purpose, and Objectives

- Tell us about yourself 
- Team and Application you are working on
- Are you using PCF today ?

##### Session: Pivotal at Dell Today 

- Silicon Valley State of Mind 

##### Session : CloudNative Journey with Pivotal Cloud Foundry
-  PCF and Cloud Native 
-  Define Cloud Native 
-  Why Cloud Native 
- Cloud Native Operability 

##### Session: PCF and .NET

- PCF and Dotnet Intersection 
- Demo CF push 
- Demo CF Cli 
- Demo Orgs, Spaces, and Roles
- Discuss Stemcell / Buildpacks 
- Containers and Diego
- Dotnet Design Considerations
- Dotnet Trouble shooting Tips
 

##### LAB 1 : Pushing apps on PCF  
Folks pair and start pushing Demo apps into the PCF env 

- Log into your PCF instance on CLI `cf login -a https://{yourapiendpoint}`
- `cf target` 

```diff
- We will work with both Classic and Dotnet Core versions for this Demo.
```
```diff
+ A) Dotnet Classic App {with Manifest file }: 
 - git clone https://github.com/reagul/pcf-dotnet-environment-viewer
 - cd ViewEnvironment. NOTE this is the dir that contains already compiled code for convinience
 - `cf push`
 
+ B) Dotnet Core App {without Manifest }:
 - git clone https://github.com/reagul/Workshop-Web-MVC-Core
 - cd Workshop-Web-MVC-Core
 - Run `dotnet restore`
 - mkdir PUBLISH 
 - Run `dotnet publish -f netcoreapp2.0 -r ubuntu.14.04-x64 -o PUBLISH`
 - Run `cf push {yourappname} -b dotnet_core_buildpack  -p  PUBLISH`
 
 ```
 
- Manifest : Change the `-name` in Manifest for Classic App and `cf push ` again
- Scale App : `cf scale myApp -i 5 `
- MAP Routes : `cf map-route {yourappname} {domainname} --hostname {yourappname}`. Why Multiple routes ?



*** Nifty Manifest Generator *** [here](http://cfmanigen.mybluemix.net/)

##### Break 15 mins @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

##### LAB 2 : Services / Logging / Metrics 

-  List the available services in the marketplace  `cf m`
- Create a MySQL Service
   `cf create-service p-mysql 100mb mysqldb-{yourappname}`
- Bind Service : Use the Dotnet classic app name instead of  {yourappname} 
   `cf bind-service {yourappname} mysqldb-{yourappname} ` 
- Open the Environment Viewer app and locate the MySQL environment Vars.
-   Application Logging : 
	`cf logs <appname>  --recent`
-   Application Metrics: Optional Demo PCF Metrics Viewer 

Special Mention - Trace Router 

##### Session Demo/Discuss : PCF and SQL Server Integration

Demo focused on the basics of using Microsoft SQL Server with Pivotal Cloud Foundry.

-  Integration with .NET Core using a User Provided Service
-  Integration with .NET Framework using a User Provided Service
-  Integration for Azure SQL using the Azure Broker Service
-  Credential Rotation with CredHub 

##### Session: CI/CD 

- Discuss Mechanics of CI / CD : Discuss Routing 
- How Rollback Works 
- Discuss Blue Green Deployment 
- Recorded Demo 

##### Lunch : 1 hr @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@


##### Session: DotNet Microservices and Demo 

Discuss Microservices on PCF 

- Typical Journey of Microservices 
- Considerations 
- [SteelToe](www.steeltoe.io)

##### Microservice Demos

-   Demo Config Server
    clone config repo from https://github.com/reagul/config-repo
    cf create-service p-config-server standard myConfigServer -c ./config-server.json
    clone Config sample from https://github.com/SteeltoeOSS/Samples
    cd Configuration/src/AspDotNetCore/SimpleCloudFoundry
    dotnet restore 
    mkdir PUBLISH
    dotnet publish -f netcoreapp2.0 -r ubuntu.14.04-x64 -o PUBLISH
    cf push -f manifest.yml -p PUBLISH
    
-   Demo Service Discovery 
-   Demo Hysterix
-   Demo PCF Stack Trace
-   Demo WCF / ASMX / Feature Toggle 

##### Break 15 mins @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

##### Security with PCF SSO #####

- Discuss PCF SSO 

##### Session Optional : DotNet Roadmap

- Discuss DotNet Roadmap for PCF 

##### Session: Pivotal Kontainer Services 

- Kubernetes on Steroids  [Read more here](https://pivotal.io/pks)

