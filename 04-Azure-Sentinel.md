# Exercise 4: Azure Sentinel
## Lab objectives
In this lab, you will complete the following exercise:
1. What is Microsoft Sentinel
1. Onboard Azure Subscription to Azure sentinel
1. Onboard the Web App – IaaS server to sentinel
1. Explore and query logs


# Task 1: What is Microsoft Sentinel?

Microsoft Sentinel is a scalable, cloud-native solution that provides:
- Security information and event management (SIEM).
- Security orchestration, automation, and response (SOAR).

 Microsoft Sentinel delivers intelligent security analytics and threat intelligence across the enterprise. With Microsoft Sentinel, you get a single solution for attack detection, threat visibility, proactive hunting, and threat response.

Microsoft Sentinel is your bird's-eye view across the enterprise alleviating the stress of increasingly sophisticated attacks, increasing volumes of alerts, and long resolution time frames.
1. **Collect data at cloud scale** across all users, devices, applications, and infrastructure, both on-premises and in multiple clouds.
1. **Detect previously undetected threats**, and minimize false positives using Microsoft's analytics and unparalleled threat intelligence.
1. **Investigate threats with artificial intelligence**, and hunt for suspicious activities at scale, tapping into years of cyber security work at Microsoft.
1. **Respond to incidents rapidly** with built-in orchestration and automation of common tasks.

    ![](images/core-capabilities.png "core-capabilities")
    
# Task 2: Onboard Azure Subscription to Azure sentinel

1. In Azure portal, Search **microsoft-sentinel (1)** and Select **microsoft-sentinel (2)**.

    ![](images/microsoft-sentinel.png "microsoft-sentinel")
 
1. On the Microsoft Sentinel page, Click on **Create**.

    ![](images/click-create.png "Create")

1. If there is no already a Log Analytic workspace that you can use click **Create a new workspace**.

     ![](images/loganalytics.png "log analytics")
     
1. On **Log Analytics workspace** page, provide the information as mentioned below,
   - Subscription: **Leave it as default**
   - Resource Group: Enter **JumpVM-rg**.
   - Name: Enter a Unique value.
   - Region: Select **East US** from the drop-down list
   - Click on **Review and Create** to continue.

     ![](images/create-log.png " create log analytics")
  
1. If Validations is passed click on **Create** to create your new Log Analytics workspace.

     ![](images/passed-log.png " Passed log analytics")
    
   >**NOTE**: It may take a Couple of minutes for the workspace to be Created.

1. Once the Log Analytics workspace is added you will see notification which says **Successfully added Log Analytics workspace** as shown below.

      ![](images/sentinel1.png)

1. Click on **ADD**.

      ![](images/click-add.png "click on add")
      
1. Once the Microsoft Sentinel is added you will see another notification which says **Successfully added Azure Sentinel** as shown below.

      ![](images/sentinel2.png)

1. This is the default page you will be taken to once your new Azure Sentinel instance has been created. After this, the overview page will be the default page shown.

     ![](images/news-sentinel.png "news-sentinel")
     

     
     
# Task 3: Onboard the Web App – IIS server to sentinel


# Task 4: Explore Azure Sentinel and query logs

1. Now, click on the **Workbooks** from the left pane under the Threat Management section and search for WAF and select **Microsoft Web Application Firewall (WAF) -      Azure WAF** from the search result.

     ![](images/401.png "news-sentinel")

1. Then from the bottom-right corner of the Azure portal, click on **Save** and then on **OK** to save the workbook.

    ![](images/402.png "news-sentinel")
    
1. Once the **Workbook** is added. you will see notification which says **Workbook 'Microsoft Web Application Firewall (WAF) - Azure WAF saved successfully** as shown    below.



1. On Microsoft Sentinel blade, under configuration click on **Setting (1)** and then click on **workspace setting**.


1. On the Log Analytics workspace page, under Connect a data source click on **Azure virtual machines (VMs)**.


1. 

  
