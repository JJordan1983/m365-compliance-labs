# Microsoft 365 Compliance Labs

## 🎯 Purpose
This repository demonstrates real-world implementation and configuration of **Microsoft Purview**, **Microsoft 365 Defender**, and **Sentinel** for compliance and security integration.  
These labs simulate how a Security Operations or Compliance team can detect, investigate, and respond to data protection incidents across Microsoft 365.

---

## 🧩 Lab Index
| Lab | Focus | Key Components |
|-----|--------|----------------|
| [Lab 1: Data Classification](lab1-data-classification/README.md) | Sensitivity labels, auto-classification, audit validation | Purview → Information Protection |
| [Lab 2: DLP Incident Response](lab2-dlp-incident-response/README.md) | Data Loss Prevention policy creation, alert triage, Sentinel integration | Purview → DLP → Defender → Sentinel |
| [Lab 3: Insider Risk Management](lab3-insider-risk/README.md) | Policy creation, alert simulation, case management | Purview Insider Risk |

---

## 🗂️ Policy Artifacts
All JSON exports for example policies can be found under `/policies/`.  
These samples include:
- `sample_dlp_policy.json` – detects credit card and PII data
- `sample_retention_policy.json` – 7-year retention policy
- `sample_label_policy.json` – “Confidential” sensitivity label definition

---

## 🧠 Tools Used
- Microsoft 365 E3 Tenant (Purview Compliance Portal)
- Microsoft Sentinel Workspace (Log Analytics)
- Microsoft Defender Portal
- Visio / Draw.io (diagram visualization)
- KQL Queries for DLP Alert correlation

---

## 🔄 Architecture Overview
![Purview Flow Diagram](diagrams/purview_alert_flow.png)

**Process Flow (Text Summary):**
1. **User Activity:** A user uploads or emails a file with PII data.
2. **Purview:** DLP or Information Protection detects sensitive data and raises an alert.
3. **Defender for Cloud Apps / Defender for Office:** Ingests the alert and correlates user context (device, location, risk level).
4. **Sentinel:** Collects compliance alerts via connectors and correlates across logs.
5. **SOC Analyst:** Investigates incident and responds via Sentinel or Purview.

---

- **Lab 2:** Confirmed DLP alert triggered and correlated in Sentinel
- **Lab 3:** Simulated insider risk alert with complete investigation lifecycle
