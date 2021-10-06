###Sequence and steps to get up and running

* run `dotnet build`
* update the `mysqlconnection` value in appsettings.json
* Run
```shell
dotnet ef dbcontext scaffold Name="mysqlconnection" "Pomelo.EntityFrameworkCore.MySql" -c "thedatabase"  -o "Models"
```
* Go to Startup.cs and uncomment DBContext registration `services.AddDbContext` (currently line 33 as of the first commit) and replace the Models.thedatabase with whatever dbcontext you used to scaffold the entities
* You can delete the weatherforecast controller and model if not needed
* You can now generate controllers, views, etc.
```shell
dotnet aspnet-codegenerator controller -name YourPreferredController -api -outDir Controllers -m YourModel -dc thedatabase
```