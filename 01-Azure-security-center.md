# Exercise 01: Azure Security Center/ Microsoft Defender for Cloud
## Lab objectives
In this lab, you will complete the following exercise:
1. Exploring Microsoft Defender for Cloud 
2. Configure Security Policies  
3. Secure Score 
4. Improving your Secure Posture 
5. Exploring Security Center and Security benchmark 

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

1. If you have not Signed in to Azure portal already, follow the steps from page 1 of the lab guide to sign in.

1. Search for **Microsoft Defender for Cloud (1)** in Azure portal search bar and then click on **Microsoft Defender for Cloud (2)**.
    
    ![](images/defender.png "Microsoft Defender")

1. On the Microsoft Defender for Cloud, Under Management Click on the **Environment settings**. Here you'll be able see the subscription.

    ![](images/settings.png "environment details")
    
1. Select the **subscription or workspace** that you want to protect.

    ![](images/subsciptionss.png "subscriptions")
 
1. Select **Enable all (1)** to enable all the plans for Defender for Cloud and then click on  **Save (2)**.

    ![](images/plans1.png "enabled all")
    
1. Back on **Microsoft Defender for Cloud** page under General Click on **Inventory**.

    ![](images/118.png "inventory")
    
1. From the **Inventory** tab, under general click on **Add non-Azure servers**.

    ![](images/119.png "add-inventory")
    
1. On **Onboard servers to Defender for Cloud** page, click on **Upgrade** next to the existing **log analytics workspace** named  to upgrade. This will allow Azure Defender protection for your resources.

    ![](images/onboard1.png "upgrade-inventory")
    
1. Once the Defender plans is added you will see another notification which says **Successfully added Defender plans** as shown below.

    ![](images/onboard2.png "saved-inventory")
    
1. Now, close the blade and go back to **Inventory** tab and then you will see few connected resources. If you didn't see any resource, you will have to click on          Refresh button at the top.

    ![](images/onboard.png "Onboard")

1. You can also find the **Virtual machines** enabled available in the resources list because **Log Analytics** agent is already enabled for it and the same Log Analytics workspace is connected to Security Center. 

    ![](images/120.png "installed-inventory")

1. On Microsoft Defender for Cloud page, under cloud security click on **Security posture**. Here you can get an overview of your security secure, unhealthy resources,    and recommendations.
    
    ![](images/securityposture1.png "overview security posture")
   
1. On Microsoft Defender for Cloud page, under cloud security click on **Regulatory compliance**. you can get insights into your compliance posture based on continuous    assessment of both Azure and hybrid cloud environments. This tile shows the following standards which are **Azure Security Benchmark** and **Lowest compliance          regulatory standards**.

    ![](images/compliance.png "overview of regulatory compliance")
    
1. On Microsoft Defender for Cloud page, under cloud security click on **Workload protections**. you can see the coverage of your **connected resources** for the          currently selected subscription. Additionally, you can also view the recent **security alerts**, color-coded by severity.

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

1. On the Azure Security Benchmark page, under **Basics** tab, leave everything to default and click on **Next**.

    ![](images/101.png "environment details")
    
 1. Under **Advanced** tab, leave everything to default and then click on **Next**.

    ![](images/102.png "environment details")
    
2. Under **Parameters** tab, leave everything to default and then click on **Next**.

    ![](images/103.png "environment details")
    
3. Under **Remediation** tab, leave everything to default and then click on **Next**.

    ![](images/104.png "environment details")

1. Now under **Non-compliance messages (1)** and then select all **Policy definitions (2)**, then click on **Review + create          (3)**.

    ![](images/noncomplaince.png "non complaince")

1. Now click on **Create**.

    ![](images/createsave.png "Create")
    
1. Once the initiative assignment succeeds, you will get a notification in top right corner of the screen mentioning the same.

    ![](images/403.png "environment details")

1. Now you will be presented by **Industry & regulatory standards** under the Security policy, which can be configured with ASC default initiative.

    ![](images/regulatorystandards.png "regulatory standards")

1. Wait for a couple of minutes and then **Refresh** the browser page to see the Industry & regulatory standards enabled.

    ![](images/refresh.png "Refresh")
    
## Explore Azure Policy

1. Search for **Policy (1)** in Azure portal search bar and then click on **Policy (2)**.

    ![](images/policy1.png )
    
1. From the left navigation pane, under the **Authoring** section, click on **Definitions (1)**. This is where you can explore the built-in policy definitions and          initiatives. From the top menu use the filter ribbon, set the Definitions Type as **Initiative (2)** and select **Security Center (3)** from the Category filter.

    ![](images/policy2.png )
    
1. You can now see built-in initiatives used by Microsoft Defender for Cloud. Here click on **Azure Security Benchmark**.

    ![](images/105.png )
  
1. On the **Azure Security Benchmark** Initiative Definition page click on **Assign**.

    ![](images/106.png )

1. On the **Basics** tab. Click on **Scope[...] (1)** and then select **Subscription (2)** and **Resource Group (3)**, then click on **Select (4)**, followed by          clicking on **Next (5)**

    ![](images/107.png )
    
1. Under **Advanced** tab, leave everything to default and then click on **Next**.

    ![](images/108.png "environment details")
    
1. Now under **parameters** tab, leave everything to default and then click on **Next**.

    ![](images/109.png "environment details")
    
1. Now under **Remediation** tab, leave everything to default and then click on **Next**.

    ![](images/110.png "environment details")
    
1. Now on the **Non-compliance messages** tab, select all **Policy definitions (1)**, then click on **Review + create (2)**.

    ![](images/111.png )
    
1. Now click on **Create**.

    ![](images/fix8.png )

1. Once the Policy is assigned you will see another notification which says **Creating initiative assignment succeeded** as shown below.

    ![](images/113.png )
    
1. To see current assignments, click on **Assignments** from the left navigation pane under **Authoring**, and here you can see **Azure Securtiy Benchmark** assigned.

    ![](images/114.png )
    
1. Now under Policy page, click on **Overview (1)** and then click on **Azure Security Benchmark (2)**.

    ![](images/115.png )
    
1. Under Azure Security Benchmark Initiative compliance page, click on **Non-compliant resources (1)**, and then click on a resource from the list **(2)**.

    ![](images/azure12.png )

1. Now you will be able to see the compliance state of the resource in detail.

    ![](images/azure1.png )
    
    
# Task 3: Secure Score 

### What is a Secure Score?
- It helps you understand your current security situation.
- It helps you improve your security situation by giving recommendations.
- A secure score is a way to achieve your goal: the higher the score, the lower the risk level.

### Access and track your secure score

1. Search **Microsoft Defender for Cloud (1)** and Select **Microsoft Defender for Cloud (2)**.

    ![](images/defender.png "Microsoft Defender")

1. On the Microsoft Defender for Cloud overview page, you can see your **secure score**.

    ![](images/posture.png "secure score")

1. Click on **Security Posture**.

    ![](images/posture.png "security posture")

1. Here you can get an overview of your **security secure, unhealthy resources, and recommendations**.

    ![](images/securescore2.png "overview security posture")
    
1. The bottom section lists the subscriptions and their current secure scores. To view the recommendations behind the score, click on **View recommendations**.

    ![](images/secure1.png)
    
1. Close the **View recommendations** page to return to **Recommendations** page.

    ![](images/secure2.png)
    
1. On the **Recommendations (1)** page, pay attention to the first part of the page; the **summary view (2)**. It includes the current **Secure Score**, progress on       the **Recommendations status** (both completed security controls and recommendations) and **Resource health** (by severity).

    ![](images/secure3.png)
    
1. From the top menu, click on the **Download CSV report** button – this allows you to get a snapshot of your resources, their health status and the associated            recommendations. You can use this file for pivoting and reporting.

    ![](images/secure4.png)
    
1. Under **Recommendation**, Click on **Manage access and permissions** and select **Guest Configuration extension should be installed on machines** from the drop-down    list. 

    ![](images/secure5.png)
    
1. On the top section, notice the following:

   - Title of the recommendation: **Guest Configuration extension should be installed on machines**
   - Severity indicator: **Medium**
   - Freshness interval: **30 Min** 

    ![](images/secure6.png)
    
1. The next important part is the **Remediation Steps** which contains the remediation logic where you can remediate the selected resources. 
1. Under **Affected resources (1)**, **select a resource** (the single **Virtual machine (2)** on the Unhealthy resources) and click on **Fix (3)**. This will  automatically apply the remediation on the selected resource.

    ![](images/121.png)
    
1. This will open a new window - **Fixing resources**, review the implications for this remediation and click on **Fix 1 resource**.

    ![](images/fix1.png)
    
1. Wait for a notification: ✅ **Remediation successful** - Successfully remediated the issues on the selected resources.
   > **Note**: It can take several minutes after remediation completes to see the resources in the 'healthy resources' tab. You can move to next task and come back                   later to check on this.
    
    ![](images/secure9.png)

# Task 4: Improving your Secure Posture 

1. Search **Microsoft Defender for Cloud (1)** and Select **Microsoft Defender for Cloud (2)**.

    ![](images/defender.png "Microsoft Defender")
    
1. Click on **Recommendations (1)** from the left side pane. Expand **Remediate vulnerabilities (2)** security control (which contains all recommendations related to      security vulnerabilities). Make sure you have **Machines should have a vulnerability assessment solution (3)** recommendation listed here.

   > Note: If you don't see the above recommendation that means it is not loaded yet and it could take up to 24 hours for all the recommendations to show up. It is possible that during lab time this may not show up – which is the case sometimes. You can note down this step number then continue to the next exercise and verify this later.

    ![](images/posture1.png)

1. Click on **Machines should have a vulnerability assessment solution** recommendation and open it.
1. Click to expand **Remediation steps (1)** – then click on the **Quick fix logic (2)** option to expose an automatic remediation script content (ARM template). Once    done, **Close (3)** this window. 

    ![](images/posture2.png)

1. From the **Affected resources (1)** tab, select  **JumpVM-DID (2)** virtual machines. Click on **Fix (3)**.

    ![](images/123.png)

1. On the **Choose a vulnerability assessment solution** select **Deploy integrated vulnerability scanner powered by Qualys (included in Microsoft Defender for            servers)**. Click on  **Proceed**.

    ![](images/posture4.png)

1. A window of **Fixing resources** will open, on this page review the list of VMs and click on **Fix 1 resources**.

    ![](images/124.png)

1. Remediation is now in process. Microsoft Defender for Cloud will deploy the Qualys VM extension on the selected VMs, so you track the status using the notification area or by using Azure activity log. **Wait for 5-10 minutes for the process to complete**.

1. Ensure the VM extension is deployed on the relevant machines:
    - Search for **Virtual Machines** in the search box located on the top of the **Azure Portal** page and click on it.
    - Select **labvm-DID**. next, click on **Extensions + applications** under the **Settings** section.
    - Ensure that **WindowsAgent.AzureSecurityCenter** extension is installed, and the status is **Provisioning succeeded**.

    
    ![](images/posture6.png)


# Task 5: Exploring Security Center and Security benchmark

Azure Security Center by Microsoft is a solution that provides unified security management across hybrid cloud workloads. It offers threat protection for data centers within both cloud workloads and on-premises.

## Explore Security Center

1. In the Azure portal, Search **Azure Security Center (1)** and then click **Azure Security Center (2)**. 

    ![](images/securitycentre.png "security centre")
     
1. On  Getting started blade, click **Install agents (1)** and then click **Install agents (2)**.

    ![](images/agent.png "security agent")

1. Back on Getting started blade, click **Upgrade** and then click **Open security center**.

    ![](images/center1.png "Open security center")

1. Note that the **Subscriptions** icon on the **top menu bar** allows you to view and filter subscriptions. In this lab, we will use only one subscription, but for      your reference, selecting different/additional subscriptions will adjust the interface to reflect the security posture for the specified subscription.

    ![](images/defender1.png "Subscription")

1. Click on the **What’s new** button – a new tab will open with the latest release notes where you can stay updated on the new features, bug fixes and more.

    ![](images/defender2.png "Whats new")
    
1. Note the **high-level numbers** at the top menu; This view allows you to see a summary of your **Azure subscriptions, Assessed resources, Active recommendations and    Security alerts.**

    ![](images/defender3.png "high level numbers")

1. On the **Overview** page, and look at the **Security posture** tile, you can see your current score along with the number of **Completed controls and Completed        recommendations**. Clicking on this tile will redirect you to drill down view across subscriptions.
    
    ![](images/defender4.png "security posture")

1. On the Microsoft Defender for Cloud blade, under the **General** section, select the **Inventory** button.

    ![](images/defender5.png)

1. Hover to the **Summaries strip** at the top of the page.

    ![](images/defender6.png)

   > **Note**: In your environment, these numbers may not be the same, since it varies in time

1.  Notice the **total number of resources**, The total number of resources are the ones that are connected to the Microsoft Defender for Cloud and NOT the total           number of resources that you have in your subscriptions.

1. Notice the number of **unhealthy resources**, The unhealthy resources are the resources with actionable recommendations based on the selected filter.

1. Notice the **unmonitored resources**, The unmonitored resources indicate if there are resources with Log Analytics agent deployed but with health issues. Since we      enabled the auto-provisioning in the previous module, all existing VMs are covered and connected, which means they are monitored.

1. Use the **Filter by name (1)** box to search for **Virtual machine**. You should now see a filtered view containing your desired resource: **JumpVM-DID**. Hover on the      red bar in the **recommendations** column to see a tooltip with the **active recommendations (2)**. You should expect to see **Active-xx of xx Recommendations**      these are the active recommendations you must attend.

    ![](images/fix2.png)

1. Open the resource health pane by selecting the resource. Click on **JumpVM-DID (1)**. Alternately. you can also right-click on any resource and select **view           resource**. You may not see **view resource** directly due to different screen resolutions, then you have to click on **ellipse(...) (2) and then select **view               resource (3)**.

    ![](images/fix3.png)

1. On the resource health pane for **JumpVM-ODL**, review the virtual machine information alongside the recommendation list.

    ![](images/fix4.png)

    > **Note**: It could take up-to 24 hours for all the recommendations to show up. And it is possible that during the lab time this may not show up – which is the         case sometimes. If you don't see the data in **recommendations**. You can continue to the next exercise and verify this later.

1. Go back to the Inventory page in the filter menu, select the **Resource Groups (1)** filter and then provide the value **JumpVM-rg (2)** (Unselect remaining),          and click on **Ok (3)**. Using this filter, you can see all resources related to the predefined Kubernetes resources which are monitored with active                    recommendations.

      ![](images/fix5.png)

    > **Note:** The list can be filtered and sorted.
    
1. On the **Inventory** page, Select the **virtual machine** and then from the top menu, click on **Assign tags**

    ![](images/126.png)

1. On the **Assign tags** blade, Assign **Environment** as the name and **Production** as the value and click on **Save**.

    ![](images/fix7.png)

1. Wait for a notification: ✅ **Successfully assigned the tag**.

    ![](images/defender13.png)
    
1. From the filter pane, select **Defender  for Cloud (1)** filter and set value to **On** and click on **OK**. On the **Resource Groups (2)** select **JumpVM-rg**        (Unselect remaining) and again click on **Ok**

    ![](images/127.png)

1. From the top menu bar, click on **Download CSV report (3)**. You will get a snapshot to work on it offline already filtered. You can also right-click on any of the    resources and upgrade to Microsoft Defender  for Cloud plan (when applicable).

1. Wait for a notification: ✅ **Your CSV report is ready**.

    ![](images/defender15.png)

1. From the top menu, click on **Open query**.

    ![](images/128.png)
    
1. On the **Azure Resource Graph Explorer** blade, click on **Run Query (1)**. This query is editable based on the requirement.

    ![](images/defender17.png)

1. Save the query for later use by clicking on **Save as** from the top menu. You can use it to create periodic reports. Name the report as **asc-filtered-query** and      select **save**.
 
   ![](images/defender18.png)

## Explore Security benchmark

1. Search for **Policy (1)** in Azure portal search bar and then click on **Policy (2)**.

    ![](images/policy1.png)
    
1. Select **Definitions (1)** from the left navigation pane.

1. From the top menu, select **+ Initiative definition (2)** to add a new initiative

    ![](images/benchmark1.png)
 
1. On the New Initiative definition page, select the following:
    - Initiative location: Select your Subscription
    - Name: **Contoso Security Benchmark**
    - Description: Baseline for security policies to appear alongside the built-in recommendations
    - Category: Select **Create new** and type: **Contoso**
    - Version: **1**
    - Click **Next**

    ![](images/benchmark2.png)

1. On the Policies tab, select **Add policy definition(s) (1)**.
1. The Add policy definition(s) pane open Search **Storage accounts should restrict network access (2)** and select the **Storage accounts should restrict network        access (3)** and click on **Add (4)**. Select **Review + Create (5)**.

    ![](images/benchmark3.png)

1. Click on **Create**.

    ![](images/benchmark4.png)

1.  Wait for a notification: ✅ **Successfully saved initiative definition**.

    ![](images/benchmark5.png)

## Add a custom initiative to your subscription

1. Search for **Microsoft Defender for Cloud (1)** in Azure portal search bar and then click on **Microsoft Defender for Cloud (2)**.
    
    ![](images/defender.png "Microsoft Defender")

1. On the Microsoft Defender for Cloud, Under Management Click on the **Environment settings**.

    ![](images/settings.png "environment details")
    
1. Select the **subscription or workspace** that you want to protect.

    ![](images/subsciptionss.png "subscriptions")
        
1. Under policy setting, Click on **Security Policy**.

    ![](images/security1.png)

1. On the Security policy page, under **Your custom initiatives**, click **Add a custom initiative**.

    ![](images/security2.png)

1. Your newly created initiative is listed: **Contoso Security Benchmark**. Select **Add**.

    ![](images/security3.png)

1. On the **Assign Initiative** page leave everything as default and select **Review + Create**.

    ![](images/security4.png)
    
1. Now click on **Create**.

    ![](images/security5.png)

1. Your custom initiative is now assigned.

    ![](images/security6.png)













