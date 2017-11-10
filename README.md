# PCF-DotNet-Workshop
## Pivotal Cloud Native Applications .NET Workshop
This one day hands-on classroom style session will provide developers with hands on experience building .NET Core 1.1 and .NET 4.6 applications for Pivotal Cloud Foundry. The session includes presentations, demos and hands on labs.

Note: You may need to follow these instructions here to set your proxy settings for the CLI: [Using the cf CLI with an HTTP Proxy Server](https://docs.cloudfoundry.org/cf-cli/http-proxy.html).

This workshop requires participants to have Visual Studio 2017 installed.  Visual Studio Code can be used for the .NET Core portion of the workshop.  Use the Windows instructions for the CF CLI.  
- [Download Visual Studio 2017 Community Edition](https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15)
- [Download Visual Studio Code](https://code.visualstudio.com/?wt.mc_id=vscom_downloads)
- [Download Windows Cloud Foundry CLI](https://cli.run.pivotal.io/stable?release=windows64&source=github)
- - -
#### Agenda
##### Introductions, Purpose, and Objectives

- Tell us about yourself 
- Team and Application you are working on
- Are you using PCF today ?

##### Session : Pivotal Cloud Foundry And Cloud Native
-  PCF and Cloud Native 
-  Define Cloud Native 
-  Why Cloud Native 
- Cloud Native Operability 

##### Session: PCF and .NET

- PCF and Dotnet Intersection 
- Demo CF push 
- Demo CF Cli 
- Discuss Stemcell / Buildpacks 
- Containers and Diego
- Windows Garden Containers 
- Dotnet Middleware { Build packs } 
- Demo Dotnet Buildpacks 


##### LAB 1 : 

Folks pair and start pushing Demo apps into the PCF env 
- CF PUSH 
- CF Scale 
- MAP Routes 
- Discuss Mechanics of CI / CD and Rollback 
- Discuss Blue Green Deployment 

##### Break 15 mins

##### LAB 2 : Introduction to Cloud Foundry CLI 

-	Lab 2.0: [Instructions](./Labs/Lab2.md)
	-   Lab 2.1: Introduction to Orgs, Spaces, and Roles
	-   Lab 2.2: Pushing a .NET Core Application
	-   Lab 2.3: Pushing a .NET Classic Application
	-   Lab 2.5: Creating and Binding to Services
	-   Lab 2.8: Application Logging
	-   Lab 2.9: Application Metrics


##### Demo/Discuss : PCF and SQL Server Integration

Demo focused on the basics of using Microsoft SQL Server with Pivotal Cloud Foundry.

-	Lab 3: [Introduction - Powerpoint]()

	*Advanced workshop focused on the integration of Microsoft SQL Server with Pivotal Cloud Foundry. Presentation topics include cloud native design, data migration, and security requirements. This is a hands-on workshop is designed to help developers create .NET applications from scratch and make changes to quickly enable SQL Server scaffolding and then update the application to take advantage of PCF.*
    
-	Lab 3.0: [Instructions](./Labs/Lab3.md)
	-   Lab 3.1: Simple integration with .NET Core using a User Provided Service
	-   Lab 3.2: Simple integration with .NET Framework using a User Provided Service
	-   Lab 3.3: Simple integration for Azure SQL using the Azure Broker Service


##### Lunch : 1 hr 


##### Session: DotNet Microservices and Demo 

Demo focused on the basics of integrating Pivotal's Configuration Services and Service Discovery capabilities with .NET Framework Applications.

-	Lab 4: [Introduction - Powerpoint]()

	*Advanced workshop focused on the integration of Service Discovery functionality in .NET client and server applications. Presentation topics include service discovery principles, configuration services, and security considerations. This is a hands-on workshop is designed to help developers create .NET Framework applications from scratch and make changes to quickly enable service discovery.*

-	Lab 4.0: [Instructions](./Labs/Lab5.md)
        -   Introduce SteelToe
	-   Lab 4.1: Demo Config Server
	-   Lab 4.2: Demo Service Discovery 
	-   Lab 4.2: Demo Hysterix 


##### Session Optional : CI-CD Pipelines with Team Services (Demos)
-	Demo 6: [Introduction - Powerpoint]()
	-   Demo 6.1: Setting Up Endpoints for Services
	-   Demo 6.2: Creating a .NET Core Build Job for PCF
	-   Demo 6.3: Creating a .NET Classic Build Job for PCF
	-   Demo 6.4: Creating a Deployment Definition for PCF
	-   Demo 6.5: Creating a Blue-Green Deployment Definition for PCF
-	Implementation Guide: [CI/CD Pipelines for VSTS/TFS](./documents/PivotalTeamFoundationServicesCICD.docx.pdf)  

