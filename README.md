# CoE Starter Kit Audit Logs Sync Flow V3

Option for CoE Starter Kit Audit Logs Sync Flow using new Audit Logs Query Graph API (preview). Current V2 sync flow uses old Office 365 Management API which has limitations not allowing to define this audit log events . With Graph API we can do this by defining 

https://learn.microsoft.com/en-us/graph/api/security-auditcoreroot-list-auditlogqueries?view=graph-rest-beta&tabs=http

## Installation

Download the latest version of the solution and import to the same environment where you have CoE Kit Core Components installed using **CoE Kit service account**.

1. Update the permissions of the Entra ID app registration to use **AuditLogsQuery.Read.All** Application permissions and grant the consent

   ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/6117dde1-281f-4e57-92ca-1b11b60f2ce6)

   <br>
2. If you have been using current **Admin | Audit Logs | Sync Audit Logs (V2)** flow then stop the flow in **Center of Excellence - Core Components** solution

   ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/87eaaf70-808c-4654-a499-e8b7cda91c64)

   <br>
4. Make sure that the **Admin | Audit Logs | Update Data (V2)** flow turned on

   ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/158cc437-6598-44f6-bf66-4b24e0b0c05d)

   <br>
6. Update the Audit Logs - Audience environment variable by using Coe Admin Command Center or in Default solution to use Graph API URL > https://graph.microsoft.com

   ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/05ea356e-a6ab-4dbc-acf3-8c1763abc751)

    <br>
7. If you have not configured Audit Logs sync before then set the Audit Logs Client ID and Client Secret environment variables as well
   
9. Flow is running every 6 hours by default querying last 6 hour of LaunchedApp, DeleteApp and DeleteFlow events. If you want to change the frequency then change the interval of the trigger and you also need to change the time

   ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/af0fc134-4bcf-4b20-92af-402b92e1f993)

   <br>
10. ??

   
