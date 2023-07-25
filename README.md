# Azure-SOC


[![Azure Cloud Image cover](https://raw.githubusercontent.com/corieX/Azure-SOC/main/AzureImage.jpg)](https://raw.githubusercontent.com/corieX/Azure-SOC/main/AzureImage.jpg)

## Purpose and Objectives

The main goal of this project was to build a Security Operations Center (SOC) environment in Azure. I aimed to collect and analyze logs from various sources, consolidating them in a Log Analytics workspace. This was achieved using Microsoft Sentinel, which helped develop attack maps, set alert triggers, and generate incident.

In the first phase, Azure Sentinel measured the metrics of an insecure environment over a 24-hour period. Afterward, I implemented security controls to strengthen the virtual environment's security infrastructure. In the final phase, we conducted another 24-hour measurement to compare the results with the evironment being insure and with security controls in place.

The metrics analyzed encompassed:

- More than 9 security incidents within an 30 day-period.
- Detection of anomalies in user activity.
- Recommendations to enhance the security posture of the environment.

Overall, these efforts allowed us to assess the impact of the implemented security controls and demonstrate the effectiveness of our SOC environment in detecting and responding to potential threats in real-time.

- SecurityEvent (Windows Event Logs)
- Syslog (Linux Event Logs)
- SecurityAlert (Log Analytics Alerts Triggered)
- SecurityIncident (Incidents created by Sentinel)
- AzureNetworkAnalytics_CL

# Azure Components Deployed

- Network Security Group (NSG)
- Virtual Machines (2 Windows, 1 Linux)
- Log Analytics Workspace Using (KQL)
- Azure Key Vault
- Azure Storage Account
- Microsoft Sentinel
- Microsoft Defender
- Visual Studio Code

![Azure Image 2](Azure%20image2.jpg)

# Azure Evironment Before Hardening / Security Controls
![Azure Image 3](3.jpg)

The intial phase of the project consisted of leaving the Azure environment exposed to the internet. The Virtual Machines had both their Network Security Groups and built-in firewalls left wide open, and all other components deployed with public endpoints visible to the Internet. The purpose of this was to attract threat actors and observe their begavioral patterns. I created a Windows virtual machine housed with SQL database, also  a Linux server with both their network security groups set to Allow All settings. This created an unsecured Azure environment with monitoring tool Microsoft Sentinel that used logs aggregated by Logs Analytics workspace.


# Azure Evironment After Hardening / Security Controls
![Azure Image 4](Azure%20image%20%283%29.jpg)

During the Final phase of this project, it consisted of Network Security Groups were hardened by blocking inbound and outbound traffic with the exception of the created public IP addresses that are required access to the virtual machines, and all other resources were protected by their built-in firewalls also Private Endpoint.

# Azure Maps Before Hardening / Security Control

The attack map highlights the criticality of securing your infrastructure. With an open Network Security Group (NSG), malicious traffic flowed freely, emphasizing the need for robust security measures. Implementing restricted NSG rules helps prevent unauthorized access and minimizes potential threats, reinforcing the significance of information security.

![Before NSG Malicious Allowed In](Before-nsg-malicious-allowed-in.PNG)
![Before syslog SSH Auth Fail](Before-syslog-ssh-auth-fail.PNG)
![Before Windows RDP SMB Auth Fail](Before-windows-rdp-smb-auth-fail.PNG)

# Metrics Before Hardening / Security Controls

In the insecure environment, we conducted a comprehensive measurement of key metrics over a 24-hour period, starting on June 19, 2023, at 11:27PM (EST) and ending on June 20, 2023, at 11:27PM (EST). 

| Metric                   | Count
| ------------------------ | -----
| SecurityEvent            | 19217
| Syslog                   | 6917
| SecurityAlert            | 1
| SecurityIncident         | 218
| NSG Inbound Malicious Flows Allowed | 562

# Metrics After Hardening / Security Controls

In our environment, we diligently monitored crucial metrics for a continuous 24-hour period, commencing on July 3, 2023, at 3:47:01 PM (EST) and concluding on July 4, 2023, at 3:47:01 PM (EST). Notably, these measurements were taken after implementing robust security controls. By comparing the data with the previous results, we gain essential insights into the efficacy of our security measures and the overall state of information security. This analysis enables us to identify areas of improvement, validate the impact of security controls, and further fortify our systems against potential threats.

| Metric                   | Count
| ------------------------ | -----
| SecurityEvent            | 437
| Syslog                   | 323
| SecurityAlert            | 0
| SecurityIncident         | 0
| NSG Inbound Malicious Flows Allowed | 0

# Conclusion


This project successfully built an Azure cloud infrastructure and employed Microsoft Sentinel for logging and incident generation based on watch lists. Before implementing security controls, baseline metrics were recorded in the unprotected environment. After fortifying the network with various security measures, a new set of measurements was taken.

Comparing pre- and post-implementation metrics revealed a significant reduction in security events and incidents, validating the effectiveness of the security controls.




