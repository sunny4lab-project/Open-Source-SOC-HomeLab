# 🧠Open-Source SOC HomeLab

A full-scale, AI-enhanced Security Operations Center built entirely from open-source technologies.

#

🔍 **Project Overview**

This project walks you through building a real-world Security Operations Center (SOC) environment from the ground up — using open-source tools, automation, and AI enrichment.

The lab simulates the end-to-end SOC workflow:

From network traffic capture → intrusion detection → SIEM correlation → identity telemetry → AI-powered incident enrichment and automated response.

You’ll gain hands-on experience with every critical SOC layer — including network defense, identity monitoring, SOAR automation, and MITRE ATT&CK mapping.

🧩 **Key Objectives**

- ✅Build and configure an enterprise-grade SOC lab using free and open tools
- ✅Learn detection, correlation, and response workflows
- ✅Automate threat enrichment using OpenAI and VirusTotal APIs
- ✅Collect identity telemetry from Okta and Microsoft Entra ID
- ✅Map detections to MITRE ATT&CK and the Cyber Kill Chain
- ✅Document your process for a GitHub portfolio project
#
## ⚙️ Core Stack Overview

| Layer | Tool / Service | Function |
| :-------------------------- | :------------------------------ | :------------------------------------- |
| 🌐 **Perimeter Security**   | pfSense                         | Firewall, routing, log forwarding      |
| 🕵️ **Intrusion Detection** | Suricata                        | Real-time packet inspection & alerting |
| 📊 **SIEM**                 | Splunk Enterprise (no Docker)   | Log aggregation & correlation          |
| ⚙️ **SOAR Automation**      | n8n + PostgreSQL                | Automated enrichment and response      |
| 🧠 **AI Enrichment**        | OpenAI API                      | Alert summarization, MITRE mapping     |
| 🧬 **Threat Intel**         | VirusTotal API                  | IP/domain/file reputation lookups      |
| 👤 **Identity Layer**       | Okta + Microsoft Entra ID       | Sign-in & risk event telemetry         |
| 🧾 **Frameworks**           | MITRE ATT&CK / Cyber Kill Chain | Detection alignment & threat modeling  |


##
## 🧩 Data Flow Architecture

```mermaid
flowchart TD
  A[Internet] --> B(pfSense Firewall)
  B --> C(Suricata IDS)
  C --> D[(Splunk Enterprise)]
  E1[Okta] --> D
  E2[Microsoft Entra ID] --> D
  D --> F[n8n SOAR + PostgreSQL]
  F -->|Reputation| G(VirusTotal)
  F -->|AI Summary / MITRE Mapping| H(OpenAI)
  F -->|Notify| I(Slack / Email / TheHive)

