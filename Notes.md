# EF Migrations

## Set the dev environment variable
```powershell
$ENV:ASPNETCORE_ENVIRONMENT="Development"
```

## Add a new migration
```powershell
dotnet ef migrations add InitialCreate
```

## Update/Create Database
```powershell
dotnet ef database update
```