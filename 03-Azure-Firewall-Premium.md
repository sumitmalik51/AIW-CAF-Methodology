# Exercise 3: Azure Firewall Premium

Azure Firewall is a cloud-native and intelligent network firewall security service that provides the best of breed threat protection for your cloud workloads running in Azure. It's a fully stateful, firewall as a service with built-in high availability and unrestricted cloud scalability. It provides both east-west and north-south traffic inspection.

Azure Firewall Premium is a next generation firewall with capabilities that are required for highly sensitive and regulated environments. It includes the following features:

**TLS Inspection** - decrypts outbound traffic, processes the data, then encrypts the data and sends it to the destination.
IDPS - A network intrusion detection and prevention system (IDPS) allows you to monitor network activities for malicious activity, log information about this activity, report it, and optionally attempt to block it.
URL filtering - extends Azure Firewall’s FQDN filtering capability to consider an entire URL. For example, www.contoso.com/a/c instead of www.contoso.com.
Web categories - administrators can allow or deny user access to website categories such as gambling websites, social media websites, and others.

**IDPS** - A network intrusion detection and prevention system (IDPS) allows you to monitor network activities for malicious activity, log information about this activity, report it, and optionally attempt to block it.

**URL filtering** - extends Azure Firewall’s FQDN filtering capability to consider an entire URL. For example, www.contoso.com/a/c instead of www.contoso.com.

**Web categories** - administrators can allow or deny user access to website categories such as gambling websites, social media websites, and others.

For more information, see https://learn.microsoft.com/en-us/azure/firewall/premium-features

## Task 1: Test the firewall

First, create a resource group to contain the resources needed to deploy the firewall. Then create a VNet, subnets, and a test server.

1. You can see a virtual machine desktop 💻 is loaded on the left side in your browser. Use this virtual machine throughout the workshop to perform the lab.
1. In the virtual machine destop, double click on the **Azure portal** shortcut of Microsoft Edge browser which is provided on the desktop.
      
      ![](.././images/select-azureportal.png "Select Azure Portal")
      
1. 
