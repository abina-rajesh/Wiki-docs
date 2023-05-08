
[[_TOC_]]

# **TMDS**

Pelesys TMDS (Training Management and Deployment System suite) is a web-based solution providing training deployment and compliance management solutions for the commercial aviation industry.

![image.png](/.attachments/image-6f3c0dc4-c554-4ad1-af95-da77b655ade3.png)

# **TMDS Central**

“Central” access portal to all TMDS modules.

**Key Features:**

- User management
- Login and authentication
- User Roles, groups, organizations and locations
- Action and data permissions.


![image.png](/.attachments/image-e1ec53bc-9d4e-4610-bc09-e30d04b89d28.png)


# **DNS**

 For a server to be accessible on the public internet, it needs a public DNS record, and its IP address needs to be reachable on the internet .

1. Create DNS for GC, EGS, LMS-CE, QMS-CE,LMS-SE,GLX.

2. Enter DNS name and Public IP address.

![image.png](/.attachments/image-076f744c-2104-480a-9680-1bc238885f55.png)
![image.png](/.attachments/image-2ea00288-6c03-4de9-873e-a8d0fa5343a7.png)


# GLX
1. We can create GLX IIS site and database using Installer GUI.exe.

![image.png](/.attachments/image-817d911d-5757-4c1c-b89e-aec31b5e68e8.png)

2. Enter the configuration record name.

3. Enter Server IP Address to be hosted on site.

4. Enter your server credentials to create directory


![image.png](/.attachments/image-1c315619-9330-4e86-b8e5-c68229c8063c.png)

5. Create site root directory in web server.

![image.png](/.attachments/image-56c15fb8-cb96-43ed-9c32-2c99ec7c229c.png)

6. Click create new directory and mention root.dns name.

7. Enter App Pool Name (It should be database name)

8. Enter File service port.

-    We have to verify the all GLX binding port in IIS server. 

     For Example: If sites ended with 29215 port, we need to use 29216 port for new site  configuration

![image.png](/.attachments/image-44e3e889-ed61-4608-a5bb-409f08573155.png)

9. Enter SQL Server Name and credentials to create GLX Database.

![image.png](/.attachments/image-a7df739f-81a3-4c6f-b714-150e89ce610c.png)

10. Management Service Port - We can give any dummy number. It won't use for anything.

11. Click Next and select new install option.

![image.png](/.attachments/image-30212915-e756-4f47-9393-d7e13cd4fdd9.png)

12. Click Next. You can see below image to installation part of GLX.

![image.png](/.attachments/image-718a9e4e-eb6e-4196-a9e6-d48f13abd133.png)

13. Enable Everything except below items.
   
      Management Service Install. 
      File service Install.
      Crewpad Service Install.
      File Server Data update.

14.Click Install. It will take sometime to check and install everything.

![image.png](/.attachments/image-e41f757f-44c5-47e6-981b-d43cca3193ed.png)

15. Open GLX Web config file.

![image.png](/.attachments/image-7e4c1ec4-d055-4706-b948-92d1195a75d4.png)

**GC_API:**      GC URL
**GC Referrer:** TMS URL
**Client Name:**  root.dns name



16.Whitelist the TMS URL.

![image.png](/.attachments/image-c1831955-5b2e-4aba-bac2-49cecaa7b278.png)
 

**GLX IIS and Database:**

After installed the GLX, we can see the GLX IIS site and database in server. 

**Domain Update:**

 Open New Installation.SQL query and run the select * from domain to see domain is updated or not.

![image.png](/.attachments/image-2617b0f5-ed4e-460a-9f7e-9858ff54fdfd.png)


# TMS

1. Copy the TMS sites and Paste it to Production site website folder.

![image.png](/.attachments/image-2df72538-de65-4378-b47e-f06acbb7a09d.png)

2. Open TMS Web config file.

   TMS-> Web->Application->Web.config

![image.png](/.attachments/image-bbf4461c-c56a-4b56-90dd-17c7d73ddc30.png)

-   **GCApi Value**          : GC URL
-   **URL Galaxy Root Value**: GLX URL
-   **Client Name**          : root.dns name

![image.png](/.attachments/image-cda74d26-cf5b-405e-9bbc-4f94cd0d874e.png)

Save it and Close.

# EGS

**TMDS Exam Generation System (EGS):**


Web-based solution for designing and managing questions and exams.

**Key Features:**

- Question and exam versioning and approval workflows
- Rules…
- HTML5 Basic exams – online/offline exams compatible with 3rd party LMS systems
- Integration with LMS – publishing, debrief and analytics.

![image.png](/.attachments/image-296f97a6-a95c-4355-bc61-940ad7d81c91.png)


Open EGS web config file

![image.png](/.attachments/image-1cc09527-1330-409b-bc0c-d2f7040238d6.png)

**GC_URL**:     Enter GC URL
**Source_URL:** Enter EGS URL
**Connection String**: Enter EGS database name

![image.png](/.attachments/image-6ae31516-9e83-4924-8a43-ca26126d86de.png)

Save it and Close.

# GC

Open GC web config file.

![image.png](/.attachments/image-240e6e4f-11de-4047-b240-ed70e0a95273.png)

**Db Name:** Enter GC DB and GLX DB Name.

![image.png](/.attachments/image-59f5aa04-6115-4b75-b760-ac49def5727b.png)

![image.png](/.attachments/image-23eef8d2-7331-4942-a83f-ef412d45b398.png)

Save it and Close.

**LMS:**


Organizes, launches, and tracks all e-learning content.


**Key Features:**

- Manage AICC and SCORM courseware units.
- Compose course structures.
- Manage user enrolments and learning status.


# LMS-CE

Open LMS-CE web config file.

![image.png](/.attachments/image-b80ec8bb-f3f4-4f5b-8e7c-218c5d19c94c.png)

**DB Name:** GLX DB
**Client Name**: root.dns name

![image.png](/.attachments/image-ae99c7e3-6056-461d-81a8-7dbeb238aeeb.png)

![image.png](/.attachments/image-06eee38c-0bb4-4437-acde-a927a6b69d44.png)

Save it and close.

# LMS-SE

Its using for crewpad pro system.

Create WebCbt folder in LMS.

![image.png](/.attachments/image-710c6e49-107d-4f77-b343-d78a58684514.png)

Copy the webcbt folder path and run it on LMS-SE.

![image.png](/.attachments/image-f08bfc22-3f07-41c8-a45c-3b5bfb08f133.png)

Open LMS-SE web config file.

![image.png](/.attachments/image-75ff4178-74b2-4d23-977d-4e752f990adf.png)

**GC Referrer:** TMS site
**Package directory:** root.dns name

![image.png](/.attachments/image-a8d3e802-cc8f-472b-b315-95912f56fe1a.png)

![image.png](/.attachments/image-38944355-251a-4da0-8ba0-f8b89e03ffe2.png)

-   **GCApi Value**          : GC URL
-   **GC Referrer**          : TMS site URL

Save it and close.


# QMS-CE

Streamlines qualification processes to ensure employee qualifications remain current.
 
**Key Features**
- Generates user certificates when related training is complete.
- Uploading documents such as passports and licenses.
- Certificate approvals.
- Calculates user qualifications based on certificate and criteria rules.

![image.png](/.attachments/image-abed95c3-1cb1-447c-a1db-7234763d0336.png)


Open QMS-CE web config file.

![image.png](/.attachments/image-845d4ff3-1214-446e-bd16-72dedc4e4ce8.png)


**DB Name:** GLX DB Name
**GC URL :** Enter GC URL
**Source URL :** Enter QMS URL

![image.png](/.attachments/image-0a4aa4ec-6c16-40b1-bd63-285b9e56ed81.png)

Save it and Close.

**IIS SITE**

1. Create IIS site for TMS and all APIs.

![image.png](/.attachments/image-9c2bc6cb-cdc6-4390-8972-1621c922921d.png)

2. Binding - Https (443) & http (80).

3. Next click on created TMS site and go to SSL settings.


![image.png](/.attachments/image-a0e8d111-1f29-465b-b16d-ea5d622ac19e.png)

3. Apply Require SSL for TMS site.

4. Enter TMS URL in Error Pages redirect.

![image.png](/.attachments/image-0f718554-3119-495f-84c3-c3d78ed8465a.png)

5. Similarly we need to create IIS site for all APIs (EGS, GC, LMS-CE, LMS-SE, QMS-CE)

6. Only https binding is required for API site.

7. For All API site, need to set preload as true in advanced settings.

8. Generate Machine Key for EGS site.

![image.png](/.attachments/image-29e61b12-32aa-49da-8d1e-3a18d1f40587.png)

9. Copy the machine key value in EGS web config file.

10. Paste the value for all api web config file. It should be located under http runtime in webconfig

   ![image.png](/.attachments/image-cbd0deee-fceb-431f-833f-96117ebb352e.png).

**Application Pools:**

 For all API sites, should modify the below one in advanced settings.

**Start Mode** : Always running
**Idle Timeout minutes**: 0
**Idle Timeout Action** : Suspend

Expand the Generate Recycle Event Log entry
Set everything as true.

**Regular time interval minutes** : 0
click on specific time and click  on Time span array (box 3...)

![image.png](/.attachments/image-98c2ce92-c709-42fe-9017-bae3dbb8bbc0.png)

# SCH

**TMDS Scheduling System (SCH):**

Streamlines scheduling processes and tracks instructors, students and resources.

**Key Features:**
- Design courses with activities and resource type requirements like classroom or equipment
- Schedule students, instructors and resources into course sessions
- Instructors can generate QMS user certificates when students complete their training.


# ETR

It has separate document. You can check the TMDS sub document.

Next Release pipeline for new site.

-----------------------------

1) navigate to production database you want to make a backup of
2) In overview tab of database, click on copy

**Copy Properties**
|  **Property** | **Value** | |
| ------ | ------ | ------ |
| Database Name | Give it a unique name |
| Server | Create New Server |
| | **Server Properties** |
| | Server Name | Give it a unique name |
| | Location | Same as source database |
| | Authentication | Use SQL Authentication |
| | Server Admin Login | dbadm |
| | Password | Any password. Need to hand over to Devs |
| Want to Use SQL elastic Pool? | No |
| Compute + Storage |
| | Compute Tier | Serverless |
| | Compute Hardware | Max vCores = 4 |

3) Click OK -> Review + Create -> Create
4) Once the resources have been created navigate to the resource group of newly created SQL Server and Database
5) In overview tab, check boxes next to SQL Server and Database and click on Move -> To another subscription

| Subscription | ETR-Dev |
| -- | -- |
| Resource Group | Dev-WE |

6) Click Next -> Wait for validation
7) Next -> Check "I understand..." -> Next to begin move
8) After move is completed, notify devs and provide credentials for SQL Server













 
