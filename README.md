# Azure-Soc-Honeypot
Cloud Honeynet / SOC (![Untitled drawing](https://github.com/RugbyMan15/Azure-Soc-Honeypot/assets/121908604/8b8eb492-4865-448c-8b04-bdf18002f4fc)


## Introduction

In this project, I will build a mini honeynet in Azure and ingest log sources from various resources into a Log Analytics workspace, which is then used by Microsoft Sentinel to build attack maps, trigger alerts, and create incidents. I measured security metrics in the insecure environment for 24 hours, apply security controls to harden the environment, measure metrics for another 24 hours, then show the results below. The metrics we will show are:

- SecurityEvent (Windows Event Logs)
- Syslog (Linux Event Logs)
- SecurityAlert (Log Analytics Alerts Triggered)
- SecurityIncident (Incidents created by Sentinel)
- AzureNetworkAnalytics_CL (Malicious Flows allowed into our honeynet)

## Architecture Before Hardening / Security Controls
![aBDwnKbpublic](https://github.com/RugbyMan15/Azure-Soc-Honeypot/assets/121908604/48dc8436-d46b-4d22-919b-246546f671bf)

## Architecture After Hardening / Security Controls
![harden](https://github.com/RugbyMan15/Azure-Soc-Honeypot/assets/121908604/1ecfd53f-e1b6-4da0-8ddb-a90c2dd01993)


The architecture of the mini honeynet in Azure consists of the following components:

- Virtual Network (VNet)
- Network Security Group (NSG)
- Virtual Machines (2 windows, 1 linux)
- Log Analytics Workspace
- Azure Key Vault
- Azure Storage Account
- Microsoft Sentinel

For the "BEFORE" metrics, all resources were originally deployed, exposed to the internet. The Virtual Machines had both their Network Security Groups and built-in firewalls wide open, and all other resources are deployed with public endpoints visible to the Internet; aka, no use for Private Endpoints.

For the "AFTER" metrics, Network Security Groups were hardened by blocking ALL traffic with the exception of my admin workstation, and all other resources were protected by their built-in firewalls as well as Private Endpoint

## Attack Maps Before Hardening / Security Controls
Windows-rdp-smb-auth-fail ![Screenshot 2023-10-06 134549](https://github.com/RugbyMan15/Azure-Soc-Honeypot/assets/121908604/d5600fb8-47b9-45a2-b40f-7c3becbc6557)
syslog-ssh-auth-fail 
