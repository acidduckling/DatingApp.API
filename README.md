# Build Notes
If you are using WSL and VS Code, running a build will break intellisense in the VS Code editor. This happens of course because the compiled files will be compiled for Linux and not Windows - so to keep things simple while editing, run the dotnet build using PowerShell rather than bash.

# Set the dev environment variable
**With PowerShell**
```powershell
$ENV:ASPNETCORE_ENVIRONMENT="Development"
```
**With Bash/WSL**
```bash
export ASPNETCORE_ENVIRONMENT=Development
```

# EF Migrations

## Add a new migration
```powershell
dotnet ef migrations add InitialCreate
```

## Update/Create Database
```powershell
dotnet ef database update
```

## Seed data
https://www.json-generator.com/

# Running the Solution

1. Set the **ASPNETCORE_ENVIRONMENT** env variable to either "Development" or "Production"
2. Ensure that DatingApp.SPA and DatingApp.API are in the same folder for build purposes.
3. Start the DatingApp.API project by running the following command
```bash
dotnet watch run
```
4. Run the build for the Angular project in DatingApp.SPA, so that the build goes to the DatingApp.API/wwwroot folder
5. Visit the URL as output by .NET Core (should be http://localhost:5000 by default)