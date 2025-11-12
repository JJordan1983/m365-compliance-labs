# Lab 1: Data Classification & Sensitivity Labels

## Purpose
This lab demonstrates how to classify and protect sensitive data using Microsoft Purview Information Protection.  

## Setup Steps
1. Navigate to **Purview Compliance Portal → Information Protection**.  
2. Create three labels:
   - Public
   - Confidential
   - Highly Confidential (encrypt content)
3. Configure auto-labeling for financial or PII keywords.
4. Publish the labels to a test user group.
5. Upload documents containing dummy data (e.g., “Name, SSN, Credit Card”).
6. Wait for labels to auto-apply.

## Results
- Auto-labeling correctly applied “Highly Confidential” to PII documents.
- Validation via **Activity Explorer** confirmed label usage.
- Generated audit log entries visible in the **Unified Audit Log**.
