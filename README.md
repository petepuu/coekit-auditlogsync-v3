# CoE Starter Kit Audit Logs Sync Flow V3

This is another option for CoE Starter Kit Audit Logs Sync Flow using new Audit Logs Query Graph API (preview). Current V2 sync flow uses old Office 365 Management API which has limitations not allowing us to define what events we want to query from the Audit Log causing performance and throttling issues especially in large busy tenants. With Graph API we can query only events we need reducing amount of Power Platform requests needed to process the events 

https://learn.microsoft.com/en-us/graph/api/security-auditcoreroot-list-auditlogqueries?view=graph-rest-beta&tabs=http

## Installation and configuration

Download the latest version of the solution and import to the same environment where you have CoE Kit Core Components installed using **CoE Kit service account**.

![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/703e2280-52a4-4156-9466-4f650702ecee)

<br><br>
1. Update the permissions of the Entra ID app registration to use **AuditLogsQuery.Read.All** Application permissions and grant the consent. If you do not have the Entra ID application created for this yet then follow the official CoE Kit instructions how to create application for this https://learn.microsoft.com/en-us/power-platform/guidance/coe/setup-auditlog-http#create-a-microsoft-entra-app-registration-for-the-office-365-management-api

   ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/6117dde1-281f-4e57-92ca-1b11b60f2ce6)

   <br>
2. If you have been using current **Admin | Audit Logs | Sync Audit Logs (V2)** flow then stop the flow in **Center of Excellence - Core Components** solution

   ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/87eaaf70-808c-4654-a499-e8b7cda91c64)

   <br>
4. Make sure that the **Admin | Audit Logs | Update Data (V2)** flow is turned on

   ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/158cc437-6598-44f6-bf66-4b24e0b0c05d)

   <br>
6. Update the **Audit Logs - Audience** environment variable by using Coe Admin Command Center or in Default solution to use Graph API URL > https://graph.microsoft.com

   ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/05ea356e-a6ab-4dbc-acf3-8c1763abc751)

    <br>
7. If you have not configured Audit Logs sync before then set the **Audit Logs - ClientID** and **Audit Logs - Client Secret** or **Audit Logs - Client Azure Secret** if secret is stored in Azure KeyVault

   ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/1c022d7b-5ba2-4545-8726-2d3d87b27ab6)

   <br>
9. Browse to the **Audit Logs Sync V3** solution and open the **Admin | Audit Logs | Sync Audit Logs (V3)** flow details page
    
    ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/ce49509b-41eb-4193-a4e0-f246403b415f)

    <br>
11. Flow is running every 6 hours by default querying last 6 hour of LaunchedApp, DeleteApp and DeleteFlow events. If you want to change the frequency then change the interval of the trigger and you also need to change the time otherwise move to next step

     ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/c172cf74-0963-4134-868c-caa3c2ebf063)
    <br><br><br>
    ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/03f7ae30-6dcb-44d3-9b7a-6d1dcbd3a8f2)

   <br>

12. Turn on the flow

    ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/cd76d8ae-2f34-4389-b568-d18149c3dbdb)

13. Run the flow

    ![image](https://github.com/petepuu/coekit-auditlogsync-v3/assets/8307644/28bc3e29-4ab3-4826-bd56-bbbc0d56b8af)

    
   



    

   
