# globomantics-cs

GloboTicket ASP.NET App:
https://github.com/RolandGuijt/ps-microservices-getting-started

- Can also build test cases for Swagger API / microservices

Steps: follow the online README.md

dotnet --list-sdks
dotnet tool install --global dotnet-ef

dotnet build

Modify appsettings.json (2 backend services):
From: "DefaultConnection": "Server=(localdb)\\MSSQLLocalDB;..."
To:   "DefaultConnection": "Server=localhost\\SQLEXPRESS19;..."

Running migrations:
First, navigate into the GloboTicket\GloboTicket.Services.EventCatalog folder and run the dotnet ef database update command.
Then, navigate into the \GloboTicket\GloboTicket.Services.ShoppingBasket folder and run the dotnet ef database update command.

dotnet ef database update
Run "dotnet tool restore" to make the "dotnet-ef" command available.

Console Output:
C:\dev\cs\ps-microservices-getting-started\GloboTicket\GloboTicket.Services.EventCatalog>dotnet tool restore
Tool 'dotnet-ef' (version '3.1.5') was restored. Available commands: dotnet-ef

Restore was successful.

C:\dev\cs\ps-microservices-getting-started\GloboTicket\GloboTicket.Services.EventCatalog>dotnet ef database update
Build started...
Build succeeded.
Done.

Result: GloboTicketEventCatalogDb created (verified under SSMS)

Redo for Shopping Basket
Result: GloboTicketShoppingBasketDb created (verified under SSMS)


Need SQL Server Express:
https://www.microsoft.com/en-ca/sql-server/sql-server-downloads

Security Update: KB5014356 - Description of the security update for SQL Server 2019 GDR: June 14, 2022
https://support.microsoft.com/en-us/topic/kb5014356-description-of-the-security-update-for-sql-server-2019-gdr-june-14-2022-568fdeaa-f05a-4f2e-8be5-b0a15d99fd8a


For each Services project: 
Tools | command line | Developer command prompt 
dotnet run

Result:
https://localhost:5001/swagger/index.html
https://localhost:5002/swagger/index.html

For web project, run from VS 2022:
Frontends | GloboTicket.Web: Debug | Start new instance
