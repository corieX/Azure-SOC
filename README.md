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

In the first phase of the project, I deliberately exposed the Azure environment to the internet. The Virtual Machines, along with their Network Security Groups and built-in firewalls, were intentionally left wide open, and all other components had public endpoints visible to the Internet. The goal was to attract potential threat actors and observe their actions and behavior.

To achieve this, I set up a Windows virtual machine with a SQL database and a Linux server, both configured with Network Security Groups set to "Allow All" settings. This created an unsecured Azure environment that served as a honeypot for monitoring and analysis.

To monitor the activities and gather insights, I utilized Microsoft Sentinel, a powerful tool that collected and analyzed logs from various sources, aggregated within a Logs Analytics workspace. This allowed for real-time observation of potential threats and helped gain valuable information about the tactics used by threat actors.

By simulating an exposed environment and using advanced monitoring techniques, this gave me valuable insights into potential vulnerabilities and risks, which gave me experience on how to to enhance the security measures effectively and proactively protect the Azure infrastructure.


# Azure Evironment After Hardening / Security Controls
![Azure Image 4](Azure%20image%20%283%29.jpg)

In the Final phase of this project, I focused on enhancing the security of the Azure environment, specifically the Network Security Groups (NSGs) and built-in firewalls.

To bolster the security of the environment, I hardened the NSGs by implementing strict rules. By blocking both inbound and outbound traffic, except for specific public IP addresses that were necessary to access the virtual machines. This approach allowed more security to the resources more effectively, ensuring that only authorized entities could interact with them.

Additionally, I made sure that all other resources within the environment were protected by their respective built-in firewalls, providing an added layer of defense. Private Endpoints were also utilized to further secure the resources, enabling private connections to specific Azure services without exposing them to the public internet.

By implementing these security measures, this reduced the level of risk and enhanced the overall security of the Azure environment, making it more resilient against potential threats and unauthorized access.

# Azure Maps Before Hardening / Security Control

In my experience, the attack map demonstrated the utmost importance of securing our infrastructure. Witnessing how malicious traffic flowed freely due to an open Network Security Group (NSG) emphasized the necessity for robust security measures. Taking the initiative to implement restricted NSG rules, I learned firsthand how this action can prevent unauthorized access and greatly minimize potential threats. This experience reinforced my understanding of the significance of information security in protecting our valuable assets.

![Before NSG Malicious Allowed In](Before-nsg-malicious-allowed-in.PNG)
![Before syslog SSH Auth Fail](Before-syslog-ssh-auth-fail.PNG)
![Before Windows RDP SMB Auth Fail](Before-windows-rdp-smb-auth-fail.PNG)

# Metrics Before Hardening / Security Controls

In the insecure environment, I thoroughly measured essential metrics over a continuous 24-hour period. The measurement started on June 19, 2023, at 11:27 PM (EST) and concluded on June 20, 2023, at 11:27 PM (EST). By gathering and analyzing these metrics during this time frame, I gained valuable insights into potential vulnerabilities and risks concerning our information security. This analysis allowed me to identify areas of concern and develop targeted strategies to enhance the security of our environment effectively.

| Metric                   | Count
| ------------------------ | -----
| SecurityEvent            | 19217
| Syslog                   | 6917
| SecurityAlert            | 1
| SecurityIncident         | 218
| NSG Inbound Malicious Flows Allowed | 562

# Metrics After Hardening / Security Controls

In the environment, I personally took the responsibility of diligently monitoring crucial metrics for a continuous 24-hour period. The monitoring commenced on July 3, 2023, at 3:47:01 PM (EST) and concluded on July 4, 2023, at 3:47:01 PM (EST). It's essential to note that these measurements were taken after I implemented robust security controls.

By comparing this data with the previous results, I gained valuable insights into the effectiveness of our security measures and the overall state of our information security. This analysis enabled me to identify areas for improvement, validate the impact of the security controls, and further fortify our systems against potential threats. Taking these proactive steps, I continue to strengthen our ability to protect our environment and safeguard our valuable assets.

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




