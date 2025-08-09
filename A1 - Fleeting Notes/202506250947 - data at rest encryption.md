---
date: 2025-06-25
created: 2025-06-25 09:06
aliases: 
tags:
  - type/fleeting-note
  - encryption
  - nutanix
link:
---
## Data At Rest Encryption (DARE)
**Data At Rest Encryption (DARE)** is the encryption of the data that is stored in the databases and is not moving through networks. With DARE, data at rest including offline backups are protected.

Data encryption is done by using [[Transparent Data Encryption]] (TDE) where no changes are made to the application logic or schema. DARE is done for Oracle, DB2, and MySQL databases.

DARE does not require any additional tools. A built-in and secure key management is used for the data encryption. Any user who has the permission to view the data can access and view the data.

----
## What is DARE?
"Data at rest encryption" (DARE) is a security measure that protects stored data—whether on disk, SSD, or backup media—from unauthorized access. It ensures that even if someone gains physical access to the storage, they can't read the data without the proper encryption keys.

On **Nutanix**, DARE is built into the platform and offers flexible options:
- **Software-Based Encryption**: Nutanix AOS supports native AES-256 encryption using a FIPS 140-2 Level 1 compliant module. This method doesn’t require self-encrypting drives (SEDs) or external key management systems (KMS), making it simple and cost-effective to deploy.
- **Hardware-Based Encryption**: Nutanix also supports SEDs for environments that require hardware-level protection. These drives encrypt data automatically and lock themselves if removed or tampered with.
- **Key Management**: You can use Nutanix’s built-in key manager or integrate with an external KMS, depending on your compliance needs. If the Controller VM can’t retrieve the correct key, it won’t be able to access the data.
- **Dual Encryption Support**: For added security, Nutanix allows layering software encryption over hardware encryption.

This setup is especially useful in regulated industries like finance, healthcare, and government, where data confidentiality is non-negotiable. If you're working on compliance or security hardening, Nutanix's DARE features are worth exploring further in their [official documentation](https://next.nutanix.com/installation-configuration-23/data-at-rest-encryption-configuring-and-verification-33934).

----
## Verify and/or automate DARE configuration on Nutanix clusters
To verify and automate **Data-at-Rest Encryption (DARE)** on Nutanix clusters, you’ve got a few solid options depending on your environment and tooling preferences. Here’s a breakdown tailored to your scripting and automation strengths:

---

### 🔍 **Verification Methods**

1. **Prism UI**  
   - Navigate to **Settings (gear icon) > Data-at-Rest Encryption**.  
   - This shows the current encryption status, whether SED or software-based, and the key management setup.

2. **nCLI (Nutanix Command Line Interface)**  
   Ideal for quick checks or scripting in environments using SEDs:
   ```bash
   ncli data-at-rest-encryption get-status
   ```

3. **REST API (v2)**  
   Great for automation or integration with external systems:
   ```bash
   curl -sk -X GET --header 'Accept: application/json' \
   'https://<PE_IP>:9440/PrismGateway/services/rest/v2.0/data_at_rest_encryption/' \
   --user 'admin:<password>' | python -m json.tool
   ```

4. **PowerShell Cmdlets**  
   If you're managing via Windows or integrating into Azure Pipelines, PowerShell can query the REST API or use Nutanix Cmdlets (if available).

---

### 🤖 **Automation Tips**

- **Scheduled Checks**: Use cron jobs or Azure DevOps Pipelines to run REST API queries and log results.
- **Compliance Audits**: Parse API responses to confirm encryption is enabled and all disks are protected.
- **Alerting**: Integrate with monitoring tools (like Prometheus or Splunk) to raise alerts if encryption is disabled or misconfigured.

---

For a deeper dive, Nutanix provides a [detailed guide on configuring and verifying DARE](https://next.nutanix.com/installation-configuration-23/data-at-rest-encryption-configuring-and-verification-33934) and a [KB article with command examples](https://portal.nutanix.com/page/documents/kbs/details?targetId=kA00e000000CqIaCAK) that you can adapt into scripts or playbooks.
