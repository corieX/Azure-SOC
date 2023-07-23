# Azure-SOC


[![Azure Cloud Image cover](https://raw.githubusercontent.com/corieX/Azure-SOC/main/AzureImage.jpg)](https://raw.githubusercontent.com/corieX/Azure-SOC/main/AzureImage.jpg)

## Purpose and Objectives

the purpose of this project was to construct a SOC environment within Azure. The objective was to capture and analyze logs from several sources, subsequently consolidated within a Log Analytics workspace. Microsoft Sentinel was impleented to analyze these logs by developing attack maps, creating alert triggers, and incident generation. Azure Sentinel measured the metrics of an insecure environment over a 24-hour period. Following this phase, security controls were implemented to fortify the virtual environment. Lastly, another 24-hour metric measurement phase was conducted and the results obtained from these endeavors are presented below. The metrics analyzed were:

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

The intial phase of the project consisted of leaving the Azure encironment exposed to the internet. The Virtual Machines had both their Network Security Groups and built-in firewalls left wide open, and all other components deployed with public endpoints visible to the Internet.


