# Lab 3: Insider Risk Management

## 🎯 Purpose
This lab demonstrates how to detect and investigate risky user behavior using **Microsoft Purview Insider Risk Management**. It simulates data exfiltration by a departing employee and walks through alert generation, triage, and case resolution within the Purview Compliance Portal.

---

## 🧩 Learning Objectives
By completing this lab, you will:
- Understand how Insider Risk policies detect potential data theft or policy violations.  
- Configure data sources and risk indicators (e.g., file exfiltration, USB activity, data sharing).  
- Simulate a departing employee scenario and validate alert generation.  
- Review the lifecycle of a case from alert → investigation → closure.  
- Connect insights to Microsoft 365 Defender and Sentinel.

---

## 🏗️ Lab Setup Steps

### **Step 1: Enable Insider Risk Management**
1. Sign in to the **Microsoft Purview Compliance Portal** → `https://purview.microsoft.com`.
2. Navigate to **Solutions → Insider Risk Management**.
3. If prompted, enable the solution for your tenant.  
4. Assign yourself the **Insider Risk Management Admin** and **Investigators** roles under **Permissions → Role Groups**.

---

### **Step 2: Connect Data Sources**
1. Go to **Settings → Data Sources** and enable the following:
   - **Microsoft 365 Audit Logs**
   - **Microsoft Defender for Endpoint**
   - **Microsoft Defender for Cloud Apps**
2. Confirm data connectors are active and in sync.

---

### **Step 3: Create a Policy**
1. Select **Policies → Create Policy**.  
2. Choose **Data Theft by Departing Employee** as the template.  
3. Assign your test users (e.g., `UserA`, `UserB`).  
4. Define indicators to monitor:
   - File downloads from SharePoint or OneDrive
   - Emailing files externally
   - Copying to USB devices
5. Set thresholds to **Low** for faster simulation.

---

### **Step 4: Simulate Risky Activity**
Perform the following under your test user account:
1. Upload sensitive files (e.g., “ClientData.xlsx”) to OneDrive.
2. Share the file externally or send via Outlook to a non-organization address.
3. Optionally, simulate USB copy activity (if Defender for Endpoint is enabled).

Wait approximately 15–30 minutes for activity ingestion.

---

### **Step 5: Review Alerts**
1. Return to **Insider Risk Management → Alerts**.
2. Locate the generated alert (e.g., *“Potential data exfiltration by departing employee”*).
3. Click the alert to review evidence:
   - User profile
   - Triggering activity
   - Risk score trend
4. Escalate the alert to a **Case** for further review.

---

### **Step 6: Investigate and Close Case**
1. Open the case in **Cases → Active Cases**.  
2. Review timelines, audit details, and risk score charts.  
3. Document the root cause and corrective actions.  
4. Close the case and export the summary as a PDF.

---

## 🧠 Integration Insight
You can integrate Insider Risk alerts with **Microsoft 365 Defender** and **Sentinel** using the *Microsoft 365 Compliance Connector*.  
Example **KQL Query** in Sentinel:
```kql
SecurityAlert
| where ProductName == "Microsoft 365 Compliance"
| where AlertName contains "Insider Risk"
| project TimeGenerated, AlertName, Severity, CompromisedEntity, Description
