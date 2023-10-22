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
![Architecture Diagram](https://i.imgur.com/aBDwnKb.jpg
