# Lab 2: DLP Incident Response Integration

## Purpose
Simulate a DLP policy detecting sensitive data and triggering alerts correlated with Sentinel.

## Setup Steps
1. In **Purview → Data Loss Prevention**, create a policy using the JSON from `/policies/sample_dlp_policy.json`.
2. Enable for Exchange and OneDrive.
3. Send an email with a fake credit card number (e.g., 4111-1111-1111-1111).
4. Verify the DLP alert triggers in **Alerts**.
5. Connect **Microsoft 365 Compliance** data connector in **Sentinel**.
6. Run the following KQL query:
   ```kql
   SecurityAlert
   | where ProductName == "Microsoft 365 Compliance"
   | where AlertName contains "Credit Card"
   | project TimeGenerated, AlertName, Severity, CompromisedEntity
