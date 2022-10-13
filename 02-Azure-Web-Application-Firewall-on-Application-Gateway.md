# Exercise 2: Azure Web Application Firewall on Application Gateway
## Lab objectives
In this lab, you will complete the following exercise:

1. Configure WAF to Protect your web application
2. Publish your application to the internet with the application gateway
3. Monitor attacks against your web application
4. Customize WAF rules
5. Attack simulation

# Task 1: Configure WAF to Protect your web application

### What is Azure Web Application Firewall ?
Microsoft Azure also has a WAF service that provides centralized protection of your web applications from common exploits and vulnerabilities. The Azure Web Application Firewall is one of the features of Azure Application Gateway (layer 7 load balancer) and its main goal is to protect a web application to common attack like SQL injections, cross-site scripting and others. Also it is following the Open Web Application Security Project (OWASP) Core Rule Set. Azure WAF service offers you to select some or all of the rules from the OWASP Core Rule Set.

Azure Application Gateway has a public IP, or front end, and your application users will use this IP address to connect to your application gateway. Application Gateway is going to take the incoming traffic and, based on a few rules, redirect the traffic to the appropriate back end in the backend pool. You can have app services, virtual machines, virtual machine scale sets, or even other IP addresses in the backend pools.

 ![](/images1/applicationgateway.png "application gateway")
 
 ## Task 1: Configure WAF to Protect your web application
 
 1. Search **Application Gateway (1)** and then select **Application Gateway(2)**.
 
      ![](images/searchgateway.png "search gateway")
    
 1. Select your **Application Gateway**.

      ![](images/appgateway.png "select gateway")
      
 1. On the Application gateway blade click on **Health Probes(1)** setting and then click on **Add(2)**.

      ![](images/addhealthprobes.png "Health Probes")
      
 1. Follow the below instructions under **Add health probe** page:
    
    - Enter Name of the probe : **my-probe (1)**
    - Keep Protocol as **HTTP (2)**.
    - Choose Pick host name from backend HTTP settings as **Yes (3)**.
    - Choose Pick port name from backend settings as **Yes (4)**
    - Enter the relative **Path** of the probe as **/weatherforecast (5)**
    - Enter the **Interval (seconds)** : **30 (6)**
    - Enter the **Timeout (seconds)**  : **30 (7)**
    - Enter the **Unhealthy threshold** : **3 (8)**
    - Choose Use probe matching conditions as **Yes (9)**.
    - Enter the value of HTTP response status code match: **200-399 (10)**.
    - **Uncheck** the box next to **I want to test the backend health before adding the health probe (11)**
    - Click on **Add (12)**.
 
      ![](/images1/newhealthprobe.png "probe name")
  
 1. On the Application gateway blade click on **Backend setting(1)** under Settings tab and then select **Backendsetting(2)**.

      ![](/images1/backendsettings.png "backend setting name")
      
 1. Follow the below instructions under **Add Backend settings** :
    
    - Choose override with new host name as **YES**.
    - Select Host name Override : **Pick host name from Backend target**.
    - Choose Use Custom probe as **YES**.
    - Select your Custom probe as **my-probe**.
    - Click on **Save**.
 
      ![](images/edit1.png "Overwrite some changes")
      
 1. Now, on the Application gateway blade click on **Backend health** setting and check that status is **Healthy**.
 
      ![](images/backend-health.png "Backend Health")
  
 1. Navigate back to home page and search for **Application Firewall Policies (1)** from search bar and select it **(2)**.

      ![](images1/firewallpolicies.png)
 
 1. Click on **firewallpolicy** under Web Application Firewall page and click on **Associated Application gateways** under Settings from Application Gateway WAF policy page.

     ![](/images1/firewallpolicy.png)
     
 1. Under **Associated Application gateway** page, click on **+ Add association (1)** and select **Application Gateway(2)**

    ![](/images1/addappilcatiogateway.png)
    
 1. Under **Associate an application gateway** page, enter below instructions:

    - **Application Gateway (WAF v2 SKU)** : Select **Aplication Gateway (1)** from drop-down 
    -  **Check** the box next to **Apply the web Application Firewall policy configuration even it's different from current configuation (2) **
    -  Click on **Add (3)**

    ![](images1/associateappgateway.png)
    
1. Monitor the deployment status by selecting the **Notifications Bell (1)** icon at the top of the portal. In a minute or so, you should see a confirmation of the successful deployment. Select **Go to resource (2)**. This action will redirect you to the page.

    ![](images1/gotoresource.png)
    
 ## Task 2: Publish your application to the internet with the application gateway
 
In this task, you'll publish an application via Azure Firewall and Application Gateway.

1. On the Azure Portal **Home** page, search for **Azure Firewall** and select it.

   ![firewall](https://github.com/CloudLabsAI-Azure/AIW-Azure-Network-Services/blob/main/media/Azurefirewallnew.png?raw=true)
    
1. Click on the firewall **AzureFirewall**.

   ![firewall](/images1/azurefirewall.png)
     
1. Select **Firewall Manager (1)** from **Settings** and click on **Visit Azure Firewall Manager to configure and manage this firewall (2)**

   ![FM](https://github.com/CloudLabsAI-Azure/AIW-Azure-Network-Solutions/blob/main/media/firewallmanager.png?raw=true)
    
1. Select **Azure Firewall Policies (1)** under **Firewall Manager** page and click on Firewall Policy **afw-contoso-prod-firewallpolicy (2)**.

   ![policy](https://github.com/CloudLabsAI-Azure/AIW-Azure-Network-Solutions/blob/main/media/afwp.png?raw=true)
   
1. Select **DNAT Rules (1)** from **Settings** tab under **Firewall Policy** page and select **+ Add a rule collection (2)**

   ![rule](https://github.com/CloudLabsAI-Azure/AIW-Azure-Network-Services/blob/main/media/dnat1.png?raw=true)
    
1. Under **Add a rule collection** page, enter the below details:

    - Name: **afw-contoso-prod-firewall-rulecolection (1)**
    - Rule Collection type: **DNAT (2)**
    - Priority: **100 (3)**
    - Rule collection group: **DefaultDnatRuleCollectionGroup (4)**
    - Under **Rules (5)** mention the below details:
      - Name: **afw-dnat-http**
      - Source type: Select **IP Address** from the drop-down list
      - Source: Enter *
      - Protocol: Select **TCP** from the drop-down list
      - Destination Ports: **80**
      - Destination type: Select **IP Address** from the drop-down list
      - Destination : Enter the IP address of **Firewall** that you copied in the task-1
      - Translated address: Enter the Private IP address of **Application gateway**. 
      - Translated port: **80**
     
     - Click on **Add (6)**

       ![rule](https://github.com/CloudLabsAI-Azure/AIW-Azure-Network-Solutions/blob/main/media/rulec.png?raw=true)
          
1. Now, to test the application copy and paste the Public IP address of **Firewall** in a new browser tab.

   ![ss](https://github.com/CloudLabsAI-Azure/AIW-Azure-Network-Solutions/blob/main/media/CIVMeastus002.png?raw=true)
       
1. This will confirm that you have published the Contoso web application via Azure Firewall & Application Gateway.

  


      
