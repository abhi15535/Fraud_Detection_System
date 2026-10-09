# 🛡️ AI-Powered Fraud Detection & Monitoring System (Low-Code / No-Code)

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Power Automate](https://img.shields.io/badge/Power_Automate-0066FF?style=for-the-badge&logo=powerautomate&logoColor=white)](https://powerautomate.microsoft.com/)
[![AI Builder](https://img.shields.io/badge/AI_Builder-00A4EF?style=for-the-badge&logo=microsoft&logoColor=white)](https://learn.microsoft.com/en-us/ai-builder/)
[![SharePoint](https://img.shields.io/badge/SharePoint-038387?style=for-the-badge&logo=microsoftsharepoint&logoColor=white)](https://www.microsoft.com/en-us/microsoft-365/sharepoint)
[![Microsoft Forms](https://img.shields.io/badge/Microsoft_Forms-008272?style=for-the-badge&logo=microsoft&logoColor=white)](https://forms.microsoft.com/)
[![Platform](https://img.shields.io/badge/Architecture-Low--Code%20%2F%20No--Code-blueviolet?style=for-the-badge)](#tech-stack)

An enterprise-grade, **End-to-End Low-Code / No-Code Fraud Detection & Threat Intelligence System**. This solution automatically captures, validates, analyzes, and visualizes potentially fraudulent communications (SMS and Email phishing scams) in real time using **Microsoft Power Platform, AI Builder, SharePoint, and Power BI**.

---

## 📑 Table of Contents
- [📌 Project Overview](#-project-overview)
- [✨ Key Features](#-key-features)
- [🧩 Tech Stack & Ecosystem](#-tech-stack--ecosystem)
- [🔄 System Architecture & Data Flow](#-system-architecture--data-flow)
- [⚙️ Fraud Detection & AI Logic](#️-fraud-detection--ai-logic)
- [📸 System Walkthrough & Screenshots](#-system-walkthrough--screenshots)
  - [1. User Incident Reporting (Microsoft Forms)](#1-user-incident-reporting-microsoft-forms)
  - [2. Centralized Incident Store (SharePoint & Excel)](#2-centralized-incident-store-sharepoint--excel)
  - [3. Automated Orchestration & AI Builder Classification](#3-automated-orchestration--ai-builder-classification)
  - [4. Interactive Threat Intelligence Dashboard (Power BI)](#4-interactive-threat-intelligence-dashboard-power-bi)
- [📊 Dashboard Visual Analytics & KPIs](#-dashboard-visual-analytics--kpis)
- [📂 Repository Structure](#-repository-structure)
- [🚀 Setup & Deployment Guide](#-setup--deployment-guide)
- [🔮 Roadmap & Future Enhancements](#-roadmap--future-enhancements)
- [🤝 Contributing & Contact](#-contributing--contact)

---

## 📌 Project Overview

Modern cyber fraud targeting users via SMS (Smishing) and Email (Phishing) causes significant financial and identity losses. Traditional fraud prevention systems often require complex coding, dedicated server infrastructure, and high maintenance costs.

This project delivers a **scalable, fully automated, low-code/no-code alternative** that enables security operations and organizations to:
1. **Instantly Intake Reports:** Provide users with an intuitive incident submission interface.
2. **Automate Triage:** Trigger immediate automated acknowledgments, safety guidelines, and validation workflows.
3. **AI-Driven Threat Scoring:** Leverage AI Builder and configurable rule sets to analyze text patterns, urgency triggers, suspicious sender domains, and message codes.
4. **Drive Executive Visibility:** Provide security analysts and stakeholders with high-impact Power BI analytics dashboards tracking geographic trends, repeat offenders, and channel-wise threats.

---

## ✨ Key Features

- **⚡ Zero-Code End-to-End Automation:** Seamless orchestration across Microsoft Forms, SharePoint, Power Automate, and Power BI.
- **🤖 Generative AI / AI Builder Integration:** Context-aware classification of suspicious message text, body content, and sender details.
- **🚨 Instant Security Advisory Emails:** Automated notification engine that alerts reporters on safe handling practices (avoid clicking links, never disclose OTPs/credentials).
- **📈 Dynamic Real-Time Dashboards:** Multi-dimensional Power BI visualizations with interactive cross-filtering, maps, drill-downs, and trend metrics.
- **📍 Geographic Threat Mapping:** Pinpoint fraud incident density by region and location to identify targeted geographic campaigns.
- **🔍 Repeat Offender Tracking:** Identification and ranking of top suspicious email addresses and recurring malicious message codes.

---

## 🧩 Tech Stack & Ecosystem

| Component | Technology | Role & Functionality |
| :--- | :--- | :--- |
| **Intake Layer** | **Microsoft Forms** | Secure, mobile-responsive portal for collecting reported suspicious SMS & Email communications. |
| **Data Lake & Store** | **SharePoint Online / Excel** | Centralized, secure cloud tabular repository for incident tracking, auditing, and state storage. |
| **Logic & Automation** | **Power Automate** | Event-driven workflow engine executing data transformations, conditions, AI calls, and email alerts. |
| **Intelligence Layer** | **AI Builder / Rule Engine** | NLP prompt evaluation and heuristic logic to categorize items as *Fraudulent* or *Safe*. |
| **Analytics & BI** | **Microsoft Power BI** | Executive dashboards, threat intelligence monitoring, spatial maps, and KPI metric tracking. |

---

## 🔄 System Architecture & Data Flow

```mermaid
flowchart TD
    A["👤 End User / Reporter"] -->|"Submits Suspicious Message"| B["📝 Microsoft Forms"]
    B -->|"Creates Incident Entry"| C["🗄️ SharePoint List / Excel"]
    C -->|"Trigger: On Item Created"| D["⚡ Power Automate Workflow"]
    
    subgraph Automation_Pipeline ["Automated Triage & Analysis"]
        D --> E["📧 Send Safety Advisory Email (V2)"]
        D --> F["🔀 Variable Parser (SMS vs Email Body)"]
        F --> G["🤖 AI Builder NLP Prompt & Rule Classifier"]
        G --> H{"Risk Evaluation"}
        H -->|"Score > Threshold (Fraud)"| I["🚩 Flag as Fraudulent & Escalate"]
        H -->|"Safe Content"| J["✅ Flag as Safe / Benign"]
    end
    
    I --> K["🔄 Update SharePoint Record State"]
    J --> K
    K -->|"Scheduled Refresh / Direct Data Link"| L["📊 Power BI Fraud Intelligence Dashboard"]
    L --> M["🛡️ Security Operations & Leadership Insights"]
```

---

## ⚙️ Fraud Detection & AI Logic

The detection engine combines heuristic risk patterns with AI prompt evaluation:

1. **Channel Normalization:** Evaluates whether the submission is an **SMS** or **Email** and extracts the corresponding message payload (`Message_Description` vs `Message`).
2. **Immediate Warning Broadcast:** Dispatches an automated safety response advising the reporter:
   - Not to click any links or download attachments.
   - Never to disclose personal identification, banking details, or OTPs.
3. **AI Builder NLP Analysis:** Submits the extracted payload to an AI Builder prompt model designed to identify:
   - High-risk urgency indicators (*"Account suspended immediately"*, *"Action required in 24h"*).
   - Impersonation patterns (banks, parcel delivery, tax authorities).
   - Malicious URL structures and suspicious call-to-action triggers.
4. **Heuristic Rule Sets:**
   - High-risk sender email domain validation.
   - Suspicious message code tracking.
   - Anomaly detection based on repeated submissions from identical senders.
   - User confidence & feedback rating correlations.

---

## 📸 System Walkthrough & Screenshots

### 1. User Incident Reporting (Microsoft Forms)
Users can report suspicious communications through a responsive form capturing message type, sender details, message body, and location.

<p align="center">
  <img width="1153" height="653" alt="Microsoft Forms Submission Interface" src="https://github.com/user-attachments/assets/62e0a9b0-9b97-4ced-a5cf-f7e8b83a244f" />
</p>

---

### 2. Centralized Incident Store (SharePoint & Excel)
All incoming reports are automatically logged with timestamped fields, risk classifications, feedback scores, and metadata.

<p align="center">
  <img width="2142" height="631" alt="SharePoint Centralized Repository" src="https://github.com/user-attachments/assets/580d27ed-edb8-488a-a168-cdd95164a106" />
</p>

---

### 3. Automated Orchestration & AI Builder Classification
The Power Automate pipeline triggers instantly on new list entries, parses content conditionally, executes AI Builder threat evaluation, and issues user safety guidance.

<p align="center">
  <img width="1531" height="1275" alt="Power Automate Flow Architecture" src="https://github.com/user-attachments/assets/fbf3c944-1482-4b48-84ae-c9a704c0ee86" />
</p>

<p align="center">
  <img width="1595" height="1170" alt="Power Automate Logic & AI Builder Execution" src="https://github.com/user-attachments/assets/e008b318-c681-49fb-afb1-5958673a3a5f" />
</p>

<p align="center">
  <img width="2550" height="1254" alt="Flow Execution Runs and Status Monitoring" src="https://github.com/user-attachments/assets/e1ad2f02-3cd9-44ed-86d1-04295ecf3f17" />
</p>

---

### 4. Interactive Threat Intelligence Dashboard (Power BI)
Comprehensive Power BI dashboard providing deep visibility into threat metrics, geographic distributions, channel breakdown, and top threat vectors.

<p align="center">
  <img width="1363" height="766" alt="FDS Power BI Executive Dashboard" src="https://github.com/user-attachments/assets/89818c76-4c5f-4ba3-9766-8114817b8beb" />
</p>

<p align="center">
  <img width="1488" height="1382" alt="Power BI Analytical Deep-Dive" src="https://github.com/user-attachments/assets/fdfc323b-24d8-48be-a02b-940c7e372444" />
</p>

---

## 📊 Dashboard Visual Analytics & KPIs

The interactive Power BI dashboard delivers operational and executive metrics:

- **📊 SMS vs. Email Risk Breakdown:** Comparative visual of fraud prevalence across communication channels.
- **⚖️ Fraud vs. Safe Classification:** Real-time ratio of identified malicious attacks versus benign submissions.
- **🔢 Total Submission Volume:** Aggregate operational workload metric and platform engagement.
- **⭐ User Feedback & Confidence Scoring:** Reporter accuracy feedback to calibrate detection precision.
- **🗺️ Geographic Threat Map:** Spatial mapping of incidents by reported locations and regions.
- **🎯 Top 10 Malicious Senders:** Ranked list of high-frequency sender email IDs for blocklisting.
- **🏷️ Top 10 Message Codes & Indicators:** Identified scam templates, malicious patterns, and attack vectors.

---

## 📂 Repository Structure

```plaintext
Fraud-Detection-System/
├── 📊 FDS_DASHBOARD.pbix                     # Complete interactive Power BI report & data model
├── ⚡ Fraud Detection Flow.txt               # Step-by-step workflow logic & AI prompt definition
├── 📦 FraudDetectionFlow_20250829055341.zip # Exported Power Automate package ready for import
└── 📖 README.md                              # Comprehensive project documentation & visual guide
```

---

## 🚀 Setup & Deployment Guide

### Prerequisites
- Microsoft 365 Account with access to **Power Automate**, **SharePoint Online**, and **Forms**.
- **Power BI Desktop** (latest version) for opening and customizing `.pbix`.
- Microsoft **AI Builder** capacity/credits enabled in your Power Platform environment.

### Deployment Steps
1. **Create SharePoint List:**
   - Create a list with columns matching the form inputs (`Email_ID`, `How_the_message`, `Message_Description`, `Message`, `Status`, `Location`, `Feedback`).
2. **Import Power Automate Flow:**
   - Navigate to [Power Automate Portal](https://make.powerautomate.com/).
   - Import the package: `FraudDetectionFlow_20250829055341 (1).zip`.
   - Reconnect connections (SharePoint, Office 365 Outlook, AI Builder).
3. **Configure AI Builder Prompt:**
   - Verify prompt instructions and set output classification thresholds.
4. **Deploy Power BI Dashboard:**
   - Open [FDS_DASHBOARD.pbix](file:///c:/Users/DELL/Downloads/Fraud-Detection-System/FDS_DASHBOARD.pbix) in Power BI Desktop.
   - Update the SharePoint List URL in **Power Query Data Source Settings** to point to your live list.
   - Click **Refresh** and publish to Power BI Service.

---

## 🔮 Roadmap & Future Enhancements

- [ ] **Automated Firewall/Gateway Blocklisting:** Integrate Power Automate with Microsoft Defender / Exchange Online to auto-quarantine repeat offenders.
- [ ] **Multi-Language AI Support:** Expand AI Builder prompts to detect multi-lingual and localized phishing scams.
- [ ] **Teams/Slack SecOps Alerts:** Real-time push notifications into security team channels for critical-severity fraud reports.
- [ ] **Automated OCR for Screenshots:** Integrate Computer Vision to extract text directly from user-submitted scam screenshots.

---

<!-- ## 🤝 Contributing & Contact

Contributions, ideas, and suggestions are welcome! Feel free to open an issue or submit a pull request.
 -->

