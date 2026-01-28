# SOC-Project-Lab
A project building a functional SOC using the ELK Stack on Azure with a Fleet Server.

**Platform:** Microsoft Azure | **SIEM:** ELK Stack (Elasticsearch, Kibana, Fleet)

## 📋 Project Overview
This project involves building a functional Security Operations Center (SOC) within a cloud-native environment. I deployed a full-cycle defense system to monitor, detect, and respond to real-world Command and Control (C2) attacks simulated using the Mythic framework.

### 🎯 Key Objectives:
* **Infrastructure:** Deploy a secure Virtual Network (VNet) in Azure for victim and attacker machines.
* **Centralized Logging:** Configure a Fleet Server to manage Elastic Agents across Windows and Linux endpoints.
* **Adversary Emulation:** Simulate a persistent threat using Mythic C2 and Hydra brute-force tools.
* **Detection Engineering:** Author custom KQL (Kusto Query Language) rules to alert on malicious process execution.

---

## 🏗️ Architecture Diagram
![SOC Lab Architecture](link-to-your-diagram-image-here)
*Figure 1: High-level overview of the lab environment, showing data flow from victims to the ELK SIEM.*

---

## 🛠️ Technology Stack
| Category | Tools Used |
| :--- | :--- |
| **Cloud Provider** | Microsoft Azure (Compute, VNet, NSG) |
| **SIEM / Analytics** | ELK Stack (Elasticsearch 8.x, Kibana) |
| **Endpoint Visibility** | Elastic Agent (Fleet), Sysmon |
| **Adversary Emulation** | Kali Linux, Mythic C2 Framework, Hydra |
| **Operating Systems** | Windows Server 2022, Ubuntu 22.04 LTS |

---

## 🚀 Implementation Steps

### 1. Environment Hardening (Azure)
* Configured **Network Security Groups (NSGs)** to strictly control inbound/outbound traffic.
* Disabled **Network Level Authentication (NLA)** and **Account Lockout Policies** on the Windows victim to facilitate realistic brute-force testing.

### 2. SIEM & Fleet Deployment
* Deployed **Elasticsearch** and **Kibana** as the central brain of the SOC.
* Set up a **Fleet Server** to manage endpoint policies, enabling one-click deployment of security integrations.

### 3. Threat Simulation & Detection
* **The Attack:** Executed a Mythic C2 payload (`service-host.exe`) on the Windows target to establish a reverse shell.
* **The Detection:** Created a custom Kibana alert using the following logic to detect malicious network callbacks:
    ```kql
    process.name : "service-host.exe" and event.category : "network"
    ```

---

## 📈 Key Achievements & Learning
* **Cloud Governance:** Managed Azure resources within budget constraints while maintaining high availability.
* **Log Analysis:** Mastered the ingestion of **Sysmon Event ID 1 (Process Creation)** and **Event ID 3 (Network Connection)** for forensic investigation.
* **Incident Response:** Developed a workflow to identify, triage, and document the lifecycle of a C2 breach.

---

## 🔗 Connect with me
* **LinkedIn:** www.linkedin.com/in/utkarsh-pandey-cys


