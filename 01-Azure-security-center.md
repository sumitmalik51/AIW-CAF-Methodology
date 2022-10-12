# Exercise 01: Azure Security Centre/ Microsoft Defender for Cloud
## Lab objectives
In this lab, you will complete the following exercise:
1. Exploring Microsoft Defender for Cloud 
2. Configure Security Policies  
3. Secure Score 
4. Improving your Secure Posture 
5. Exploring Security Centre and Security benchmark 

# Task 1: Exploring Microsoft Defender for Cloud

### What is Microsoft Defender for Cloud?

Microsoft Defender for Cloud is a Cloud Security Posture Management (CSPM) and Cloud Workload Protection Platform (CWPP) for all your Azure, on-premises, and multicoloured (Amazon AWS and Google GCP) resources. Defender for Cloud fills three vital needs as you manage the security of your resources and workloads in the cloud and on-premises:

![image](https://user-images.githubusercontent.com/33771500/187170501-f78beb93-08d6-47f1-8fa7-bb8798b685a5.png)

- Defender for Cloud secure score **Continually Assesses** your security posture so you can track new security opportunities and precisely report on the progress of your security efforts.
- Defender for Cloud recommendations **Secures** your workloads with step-by-step actions that protect your workloads from known security risks.
- Defender for Cloud alerts **Defends** your workloads in real-time so you can react immediately and prevent security events from developing.

Defender for Cloud secure score continually assesses your security posture so you can track new security opportunities and precisely report on the progress of your security efforts.
Defender for Cloud recommendations secures your workloads with step-by-step actions that protect your workloads from known security risks.
Defender for Cloud alerts defends your workloads in real time so you can react immediately and prevent security events from developing.

1. In the VM, double-click on the **Azure portal shortcut** on the desktop.

    ![](images/portal.png "Select Azure Portal")
    
1. Click on the **Environment Details** tab located next to the Lab Guide tab and Copy the **Username and Password**.

    ![](images/details.png "environment details")

1. Log in to Azure with the username **<inject key="AzureAdUserEmail" />** and click on **Next**.

    ![](images/username.png "Username")

1. Enter a password **<inject key="AzureAdUserPassword" />** and click on **Sign in**.

    ![](images/password.png "Password")
    
   > **Note:** If there's a popup entitled **Stay signed in?** with buttons for **No** and **Yes** - Choose **No**.
    
    ![](images/staysigned.png "signed")
        
   > **Note:** If there's another popup entitled **Help us protect your account** click **Skip for now (14 days until this is required)**

    ![](images/skipfornow.png "skipfornow")
           
1. If the **Welcome to Microsoft Azure** popup window appears, click **Maybe Later** to skip the tour.

    ![](images/skiptour1.png "skiptour")

1. Search for **Microsoft Defender for Cloud (1)** in Azure portal search bar and then click on **Microsoft Defender for Cloud (2)**.
    
    ![](images/defender.png "Microsoft Defender")

1. On the Microsoft Defender for Cloud, Under Management Click on the **Environment settings**.

    ![](images/settings.png "environment details")
    
1. Select the **subscription or workspace** that you want to protect.

    ![](images/subsciptionss.png "subscriptions")
 
1. Select **Enable all** to enable all the plans for Defender for Cloud and then click on  **Save**.

    ![](images/enabled-defender.png "enabled all")
    
1. Back on **Microsoft Defender for Cloud** page under General Click on **Inventory**.

    ![](images/inventory.png "inventory")
    
1. From the **Inventory** tab, click on the **Add non-Azure servers**.

    ![](images/add-inventory.png "add-inventory")
    
1. On **Onboard servers to Defender for Cloud** page, click on **Upgrade** next to the existing **log analytics workspace** named  to upgrade. This will allow Azure Defender protection for your resources.

    ![](images/upgrade-inventory.png "upgrade-inventory")
    
1. Once the Defender plans is added you will see another notification which says **Successfully added Defender plans** as shown below.

    ![](images/saved-inventory.png "saved-inventory")
    
1. Now, close the blade and go back to **Inventory** tab and then you will see few connected resources. If you didn't see any resource, you will have to click on Refresh button at the top.

1. You can also find the **Virtual machines** enabled available in the resources list because **LogAnalytics** agent is already enabled for it and the same Log Analytics workspace is connected to Security Center. 

    ![](images/installed-inventory1.png "installed-inventory")

1. On Microsoft Defender for Cloud Under cloud security click on **Security posture**. Here you can get an overview of your security secure, unhealthy resources, and            recommendations.
    
    ![](images/securityposture1.png "overview security posture")
   
1. On Microsoft Defender for Cloud Under cloud security click on **Regulatory compliance**. you can get insights into your compliance posture based on continuous            assessment of both Azure and hybrid cloud environments. This tile shows the following standards which are **Azure Security Benchmark** and **Lowest compliance          regulatory standards**.

    ![](images/compliance.png "overview of regulatory compliance")
    
1. On Microsoft Defender for Cloud Under cloud security click on **Workload protections**. you can see the coverage of your **connected resources** for the currently selected subscription. Additionally, you can also view the recent **security alerts**, color-coded by severity.

    ![](images/workloads.png "Workload protections")
    
    
# Task 2: Configure Security Policies

### What is a security policy?

- An Azure Policy definition, created in Azure Policy, is a rule about specific security conditions that you want to be controlled. Built-in definitions include things like controlling what type of resources can be deployed or enforcing the use of tags on all resources. You can also create your own custom policy definitions.

- To implement these policy definitions (whether built-in or custom), you'll need to assign them. You can assign any of these policies through the Azure portal, PowerShell, or Azure CLI. Policies can be disabled or enabled from Azure Policy.

- There are different types of policies in Azure Policy. Defender for Cloud mainly uses 'Audit' policies that check specific conditions and configurations and then report on compliance. There are also "Enforce' policies that can be used to apply security settings.

## Explore Cloud Policy

1. From Defender for Cloud's menu, select **Environment settings**. Here you'll be able see the subscription.

    ![](images/settings.png "environment details")
    
1. Select the relevant **subscriptions and workspaces**.

    ![](images/subsciptionss.png "subscriptions")

1. On the left-hand side Blade under Policy settings, click on **Security policy (1)** and then click on **Assign policy (2)**.
    
    ![](images/securitypolicy.png "security policy")

1. On the Azure Security Benchmark page, Click on **Non-compliance messages (1)** and then select all **Policy definations (2)**, then click on **Review + create          (3)**.

    ![](images/noncomplaince.png "non complaince")

1. Now click on **Create**.

    ![](images/createsave.png "Create")

1. Under the Security policy you can also find **Industry & regulatory standards**, which can be configured with ASC default initiative.

    ![](images/regulatorystandards.png "regulatory standards")

1. Wait for a couple of minutes and then **Refresh** the browser page to see the Industry & regulatory standards enabled.

    ![](images/refresh.png "Refresh")
    
## Explore Azure Policy

1. Search for **Policy (1)** in Azure portal search bar and then click on **Policy (2)**.

    ![](images/policy1.png )
    
1. From the left navigation pane, under the **Authoring** section, click on **Definitions(1)**. This is where you can explore the built-in policy definitions and          initiatives.
1. From the top menu use the filter ribbon, set the Definitions Type as **Initiative(2)** and select **Security Center(3)** from the Category filter.

    ![](images/policy2.png )
    
1. You can now see built-in initiatives used by Microsoft Defender for Cloud. You can choose one of them. Below is an example.

    ![](images/policy3.png )
  
1. On the Configure Azure Defender to be enabled on SQL Servers and SQL Managed Instances page click on **Assign**.

    ![](images/policy4.png )

1. On the **Basics** tab. Click on **Scope[...] (1)** and then select **Subscription (2)** and **Resource Group (3)**, then click on **Save (4)**.

    ![](images/policy5.png )
    
1. Click on **Non-compliance messages (1)** and then select all **Policy definations (2)**, then click on **Review + create (3)**.

    ![](images/policy6.png )
    
1. Now click on **Create**.

    ![](images/policy7.png )

1. Once the Policy is assigned you will see another notification which says **Role Assignments creation succeeded** and **Creating initiative assignment succeeded** as    shown below.

    ![](images/policy8.png )
    
1. To see current assignments, click on **Assignments** from the left navigation pane under **Authoring**. Policy initiatives have a different name for the                assignments, for example:

    ![](images/policy9.png )

# Task 3: Secure Score 

### What is a Secure Score?
- It helps you understand your current security situation.
- It helps you improve your security situation by giving recommendations.
- A secure score is a way to achieve your goal: the higher the score, the lower the risk level.

### Access and track your secure score

1. Search **Microsoft Defender for Cloud (1)** and Select **Microsoft Defender for Cloud (2)**.

    ![](images/defender.png "Microsoft Defender")

1. On the Microsoft Defender for Cloud overview page, you can see your **secure score**.

    ![](images/securescore1.png "secure score")

1. Click on **Security Posture**.

    ![](images/posture.png "security posture")

1. Here you can get an overview of your security secure, unhealthy resources, and recommendations.

    ![](images/securescore2.png "overview security posture")

# Task 4: Improving your Secure Posture 

1. Search **Microsoft Defender for Cloud (1)** and Select **Microsoft Defender for Cloud (2)**.

    ![](images/defender.png "Microsoft Defender")
    
1. On the Microsoft Defender for Cloud menu under General click on **Recommendations. (1)** and then click on **All Recommendations (2)**.

    ![](images/recommendations.png "recommendations")

1. Click on those names that have **unassigned** status below is an example.

    ![](images/unassigned.png "unassigned status")
    
1. Under Affected resources select your **virtual machine (1)** and then click on a **fix (2)**.

    ![](images/fix.png "fix")

1. On the JIT VM access configuration menu click on **Save**.

    ![](images/jitvm.png "save")


# Task 5: Exploring Security Centre and Security benchmark

Azure Security Center by Microsoft is a solution that provides unified security management across hybrid cloud workloads. It offers threat protection for data centres within both cloud workloads and on-premises.

1. In the Azure portal, Search **Azure Security Centre (1)** and then click **Azure Security Centre (2)**. 

    ![](images/securitycentre.png "security centre")
     
1. On the Security Centre | Getting started blade, click **Install agents (1)** and then click **Install agents (2)**.

    ![](images/agent.png "security agent")

1. On the Security Centre | Overview blade, review the **Secure Score**.

    ![](images/securescore1.png "secure score")
    

    
    
1. Click on the **Next** button present in the bottom-right corner of this lab guide. 











