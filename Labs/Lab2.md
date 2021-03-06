# Lab 2: Cloud Foundry CLI

## Preparations
This lab requires that the Cloud Foundry CLI is installed and can be found in the path.

## Instructions
#### Cloud Foundry CLI Basics
1. Login to Cloud Foundry API Endpoint

	`> cf login -a https://{yourapiendpoint}`
 
2. Set org and space target using CLI

	`> cf target -o {yourorg} -s {yourspace}`
 

#### Lab 2.2: Pushing a .NET Core Application
1. Clone the .NET Core application [Workshop-Web-MVC-Core](https://github.com/corn-pivotal/Workshop-Web-MVC-Core)

	`> git.exe clone https://github.com/corn-pivotal/Workshop-Web-MVC-Core`
 
2. Open a Command Window or Powershell Window in the cloned directory

3. Run 'Dotnet Restore'

	`> dotnet restore`
 
4. Publish the source code using the *Release Configuration*

	`> dotnet publish -c Release`
 
5. Navigate to the folder where the source ocde was published

	`> cd bin\Release\netapp1_1\publish`
 
6. Push the source code to your API Endpoint

	`> cf push {yourappname} -b dotnet_core_buildpack` 

#### Lab 2.3: Pushing a .NET Classic Application
1. Clone the .NET Core application [Workshop-Web-MVC-452](https://github.com/corn-pivotal/Workshop-Web-MVC-452)

	`> git.exe clone https://github.com/corn-pivotal/Workshop-Web-MVC-452`
 
2. Open the solution in Visual Studio

3. Publish the source using a Folder profile

4. Navigate to the folder where the source code was published

5. Push the source code to your API Endpoint

	`> cf push {yourappname} -b hwc_buildpack -s windows2012R2` 
 
#### Lab 2.4: Scaling an Application
1. Scale the number of instances of an application

	`> cf scale {yourappname} -i 2`

2. Scale the memory and disk space of an application

	`> cf scale {yourappname} -m 1G -k 1G`

#### Lab 2.5: Creating and Binding Services
1. List the available services in the marketplace

	`> cf m`

2. Create a MySQL Service 

	`> cf create-service p-mysql 100mb mysqldb-{yourappname}`

3. Create a User Provided Service 

	`> cf create-user-provided-service myups-{yourappname} -p "{\"hostname\":\"hostname\",\"port\":\"1433\",\"name\":\"myappname\",\"username\":\"user\",\"password\":\"password\"}"`

4. Bind a Service to an Application

	`> cf bind-service {yourappname} mysqldb-{yourappname}`

#### Lab 2.6: Mapping and Unmapping Routes
1. Map a second route to your application - use the domain name used for the workshop 

	`> cf map-route {yourappname} {domainname} --hostname {yourappname}-dev` 

2. Unmap the route from your application

	`> cf unmap-route {yourappname} {domainname} --hostname {yourappname}-dev`

3. Delete orphaned routes 

	`> cf delete-orphaned-routes`

    
