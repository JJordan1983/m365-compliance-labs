# Compliance Manager Lab

## 🎯 Purpose
This lab demonstrates how to use Microsoft Purview **Compliance Manager** to create, configure, and evaluate compliance assessments based on three industry-standard frameworks:

1. **NIST 800-53 Rev. 5 (Moderate Baseline)**
2. **ISO/IEC 27001:2022**
3. **CMMC 2.0 Level 2**

These assessments provide a hands-on way to understand control mapping, improvement actions, implementation status, and how Microsoft 365 capabilities align to major regulatory frameworks.

---

## 📚 Learning Objectives
By completing this lab, you will learn how to:

- Create and configure new assessments in Compliance Manager.  
- Interpret Microsoft-managed controls vs. customer-managed controls.  
- Map M365 features (DLP, IRM, Sensitivity Labels, Defender, Sentinel, CA policies) to control requirements.  
- Track remediation progress through improvement actions.  
- Export assessment results for documentation or audits.

---

## 🏗️ Setup Steps

### **Step 1: Create an Assessment**
1. Navigate to **Microsoft Purview → Compliance Manager**  
2. Select **Assessments → Create Assessment**  
3. Choose one of the recommended frameworks:
   - *NIST 800-53 Rev. 5*
   - *ISO/IEC 27001:2022*
   - *CMMC 2.0 Level 2*
4. Assign:
   - **Assessment Name**
   - **Group** (e.g., “M365-Lab”)
   - **Services**: Microsoft 365, Exchange, SharePoint, OneDrive

---

### **Step 2: Review Improvement Actions**
1. Open the assessment.  
2. Select **Improvement actions**.  
3. Review:
   - Required implementation steps  
   - Related Purview, Entra, or Defender features  
   - Microsoft-managed vs customer-managed controls  
4. Assign each action to yourself for remediation tracking.

---

### **Step 3: Map Technical Controls**
Use the "Control Mapping Examples" section below to interpret how M365 features satisfy compliance requirements.

---

### **Step 4: Export or Document Results**
1. Navigate to **Actions → Export Assessment**  
2. Export as:
   - **JSON** (raw metadata)
   - **CSV** (for Excel documentation)
   - **PDF** (optional — for audit-ready reports)
3. Store exports in:  
   `m365-compliance-labs/compliance-manager/exports/`

---

## 🧠 Control Mapping Examples

### **NIST 800-53 Rev. 5 → Microsoft 365 Controls**
| NIST Control | Requirement | M365 Feature Mapping |
|--------------|-------------|-----------------------|
| AC-2 | Account management | Entra ID user lifecycle, Access Reviews |
| AC-17 | Remote access | Conditional Access MFA |
| AU-2 | Audit logging | Unified Audit Log, Purview Audit Premium |
| IR-4 | Incident handling | Defender XDR & Sentinel automation |
| MP-5 | Media protection | DLP Endpoint + USB device control |
| SC-28 | Data-at-rest protection | Encryption at rest, Sensitivity labels |

---

### **ISO/IEC 27001:2022 → Microsoft 365 Controls**
| ISO Control | Requirement | M365 Mapping |
|-------------|-------------|--------------|
| A.5.10 | Acceptable use | M365 Usage policy & written SOP |
| A.8.10 | Data deletion | Retention + Purge policies |
| A.8.12 | Data leakage prevention | Purview DLP policies |
| A.8.16 | Monitoring activities | Defender + Sentinel analytics |
| A.9.1 | Access control | Entra ID RBAC + PIM |

---

### **CMMC 2.0 Level 2 → Microsoft 365 Controls**
| CMMC Practice | Requirement | M365 Mapping |
|---------------|-------------|--------------|
| AC.L2-3.1.2 | Access enforcement | CA, Segmentation via Entra groups |
| AU.L2-3.3.5 | Audit log review | Purview Audit + Sentinel queries |
| IR.L2-3.6.1 |
