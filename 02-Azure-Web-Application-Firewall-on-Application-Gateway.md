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

    
 # Task 2: Publish your application to the internet with the application gateway
 

  


      
