# Project Notes

## Running the Solution

1. Set the **ASPNETCORE_ENVIRONMENT** env variable to either "Development" or "Production"

2. Ensure that DatingApp.SPA and DatingApp.API are in the same folder for build purposes.

3. Start the DatingApp.API project by running the following command (which will also enable a watch, to rebuild when source files are modified)
```bash
dotnet watch run
```

4. Run the build for the Angular project in DatingApp.SPA, so that the build goes to the DatingApp.API/wwwroot folder

5. Visit the URL as output by .NET Core (should be http://localhost:5000 by default)


## Testing The APIs With Postman
After running the DatingApp.API application, Open Postman and complete the following...

1. Import the **DatingAppLocal.postman_environment.json** environment file (this has a number of users and passwords configured as variables to use in the configured collection of APIs. Ensure that these values match the users in the database)

2. Import the **DatingApp.postman_collection.json** collection.

3. To use any of the authenticated services, first run the **Auth Login - Sets Token Variable** API request. If you want to change the user being authenticated, modify the JSON in the **body** of the request. The successful request will store the successful token into the token environment variable for use by subsequent API requests.


## Building Within WSL
If you are using WSL and VS Code, running a build will break intellisense in the VS Code editor. This happens of course because the compiled files will be compiled for Linux and not Windows - so to keep things simple while editing, run the dotnet build using PowerShell rather than bash.


## Set the dev environment variable
**With PowerShell**
```powershell
$ENV:ASPNETCORE_ENVIRONMENT="Development"
```
**With Bash/WSL**
```bash
export ASPNETCORE_ENVIRONMENT=Development
```


## EF Migrations

### Add a new migration
```powershell
dotnet ef migrations add InitialCreate
```


### Update/Create Database
```powershell
dotnet ef database update
```


### Seed data
This website can generate some basic JSON data useful for populating to a database
https://www.json-generator.com/