Resource Group
Resource Group Name: cms

SQL Database
DB name: cms
Server: cms123.database.windows.net
DB region: us-east
Admin login: cmsadmin
Admin password: CMS4dmin

Resource group: cms
DB workload env: Development
DB compute + storage: DTU - Basic
Press the "Next: Networking" button, then select "Public Endpoint", and set both of the Firewall rules that appear to "Yes".
Set everything else to default Run SQL queries in sql_scripts/ directory after completion, starting from the users table. Don't forget to take screenshots.

Storage Account
Resource group: cms1321
Storage account name: cms1321 (needs to be unique)
Advanced - Allow enabling anonymous access on individual containers: Enable
Advanced - Access tier: Cool
Network access: Enable public access from all networks (the default)
Create container named "images". Set its access level to Container.
From Security + networking > Access keys:
Blob Storage key: xR5Gjh49yb94o6o+yY1Cc1cJkOs05HRQvw8rSSd5sTxLD7Vi0E3kSaJUodWLVvXY9ZeMG6Q5nilq+AStsiI9Bw==
Blob connection string: DefaultEndpointsProtocol=https;AccountName=cms1321;AccountKey=xR5Gjh49yb94o6o+yY1Cc1cJkOs05HRQvw8rSSd5sTxLD7Vi0E3kSaJUodWLVvXY9ZeMG6Q5nilq+AStsiI9Bw==;EndpointSuffix=core.windows.net

Microsoft Entra ID 4.1. App Registration
Name: cmsEntraID
Who can use? "Accounts in any organizational directory (Any Microsoft Entra ID tenant - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox)" 4.2. Secret Creation
Secret description: test
Secret Key: 16b72f3c-a5d4-4502-bef5-102c0aafb57f
Client Secret: rpi8Q~64AfwOADjBNbG7wAZHlemphoBJqfAzIaOO
Application (client) ID: 6b75513e-7cb2-491b-aeb0-890c5ce1a415

Web App
Name: udacitycms.azurewebsites.net
Runtime stack: Python 3.10
Pricing Plan: Free F1
If you are getting a "Validation failed for a resource" error, pick a different region.
After creation:

Settings -> Environment variables - Add the following variables (sample values are included, replace them with your values):
BLOB_ACCOUNT: cms1321
BLOB_CONTAINER: images
BLOB_STORAGE_KEY: xR5Gjh49yb94o6o+yY1Cc1cJkOs05HRQvw8rSSd5sTxLD7Vi0E3kSaJUodWLVvXY9ZeMG6Q5nilq+AStsiI9Bw== - BLOB_CONNECTION_STRING: DefaultEndpointsProtocol=https;AccountName=cms1321;AccountKey=xR5Gjh49yb94o6o+yY1Cc1cJkOs05HRQvw8rSSd5sTxLD7Vi0E3kSaJUodWLVvXY9ZeMG6Q5nilq+AStsiI9Bw==;EndpointSuffix=core.windows.net
SQL_SERVER: cms123.database.windows.net
SQL_DATABASE: cms
SQL_USER_NAME: cmsadmin
SQL_PASSWORD: CMS4dmin
CLIENT_SECRET: rpi8Q~64AfwOADjBNbG7wAZHlemphoBJqfAzIaOO
SECRET_KEY: 16b72f3c-a5d4-4502-bef5-102c0aafb57f
CLIENT_ID: 6b75513e-7cb2-491b-aeb0-890c5ce1a415 Deployment Center

Source: GitHub
Pick the repo that contains the starter files.
Setting up OAuth2 At this point, your application should already be running. You should already be able to log in with username admin and password pass and you can create new posts or update existing ones.
The next part is getting the OAuth2 login to work.

Go to Microsoft Entra ID > App Registrations, click on the App Registration created earlier, and then pick Authentication from the left sidebar.

6.1. Microsoft Entra ID - Authentication - Add a Platform - Web

Redirect URIs: https://[IP ADDRESS FROM VM or WEB APP ADDRESS]/getAToken
logout URL: https://[IP ADDRESS FROM VM or WEB APP ADDRESS]/login
