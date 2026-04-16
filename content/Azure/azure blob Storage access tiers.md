---
date: 2026-04-09
created: 2026-04-09 08:04
title: Azure Blob Storage - Three Primary Access Tiers
aliases:
tags:
  - azure
  - storage
  - blobs
  - aigc
link:
---
**Azure Blob Storage** is Microsoft's object storage solution for the cloud. Blob storage is optimized for storing massive amounts of unstructured data.

Azure Blob Storage offers three primary access tiers, designed to accommodate different data access patterns and cost sensitivities:

1.  🔥 **Hot Tier:**
    * **Purpose:** Designed for data that is accessed frequently. This includes data that needs to be readily available for applications, reports, or user requests.
    * **Characteristics:**
        * **Lowest latency:** Data is quickly accessible.
        * **Highest storage cost:** Because of the performance, it's the most expensive per GB to store data.
        * **Lowest access/transaction cost:** Retrieving data is inexpensive.
    * **Use Cases:** Active application data, frequently accessed images or videos, data used in real-time analytics.

2.  ❄️ **Cool Tier:**
    * **Purpose:** Designed for data that is accessed infrequently but needs to be readily available when needed.
    * **Characteristics:**
        * **Slightly higher latency:** There's a small delay when accessing data compared to the Hot tier.
        * **Lower storage cost:** Cheaper per GB to store data than the Hot tier.
        * **Higher access/transaction cost:** Retrieving data costs more than the Hot tier.
        * **Minimum data retention:** Data must be stored for at least 30 days. If you delete data before 30 days, you'll still be charged for the 30 days.
    * **Use Cases:** Less frequently accessed backups, older log files, disaster recovery data that you might need to retrieve quickly but not constantly.

3.  📦 **Archive Tier:**
    * **Purpose:** Designed for data that is rarely accessed and can withstand longer retrieval times. This is ideal for long-term retention and compliance.
    * **Characteristics:**
        * **Highest latency:** Retrieval can take hours, as data needs to be rehydrated from archive storage.
        * **Lowest storage cost:** The cheapest per GB for long-term storage.
        * **Highest access/transaction cost:** Retrieving data is the most expensive, and there are also rehydration costs.
        * **Minimum data retention:** Data must be stored for at least 180 days. Deleting before then incurs a charge for the full 180 days.
        * **Specific retrieval options:** You can choose between standard (hours) or high (minutes) retrieval options, with corresponding cost differences.
    * **Use Cases:** Regulatory compliance archives, long-term data backups for disaster recovery, raw data that you might need to analyze years down the line.

### Important Considerations

* **Tiering within a Storage Account:** You can set a default access tier for your entire storage account (Hot or Cool). You can then explicitly set individual blobs or subdirectories to different tiers. The Archive tier can only be set at the individual blob level.
* **Access Patterns Matter:** The key to choosing the right tier is understanding your data's access patterns.
    * If you're unsure, it's often best to start with the Hot tier and then analyze your access logs (using Azure Monitor or Storage Analytics) to identify data that can be moved to Cool or Archive.
    * Conversely, if you have data that is now rarely accessed but was previously Hot, you can move it to Cool or Archive to save costs.
* **Rehydration:** Moving data *from* Cool or Archive *to* Hot incurs retrieval costs. This is why you need to be mindful of the "minimum data retention" period.
* **Pricing Nuances:** Pricing for blob storage tiers is complex and involves several components:
    * **Storage Cost (per GB per month):** This is the primary cost and varies significantly between tiers.
    * **Transaction Costs (per 10,000 operations):** Costs for read, write, and delete operations. These are higher for Cool and Archive.
    * **Data Retrieval/Rehydration Costs (per GB):** This is a significant cost for Cool and especially Archive when you need to access the data.
    * **Data Transfer Costs:** Ingress (data into Azure) is generally free. Egress (data out of Azure) and data transfer between regions incur costs.

## Pricing Comparison

Let's look at an *illustrative* example for **East US region** for LRS (Locally-redundant storage) on **July 2024**. **Please always refer to the official Azure Blob Storage pricing page for the most up-to-date and region-specific pricing.**

| Feature                  | Hot Tier (per GB/month) | Cool Tier (per GB/month) | Archive Tier (per GB/month) |
| :----------------------- | :---------------------- | :----------------------- | :-------------------------- |
| **Storage Cost**         | ~$0.018                 | ~$0.010                  | ~$0.00099                   |
| **Transaction Cost (All types)** | ~$0.004 per 10,000      | ~$0.01 per 10,000        | ~$0.02 per 10,000           |
| **Data Retrieval**       | N/A                     | ~$0.01 per GB            | ~$0.05 per GB (Standard)    |
| **Data Rehydration**     | N/A                     | N/A                      | ~$0.02 per GB (Standard)    |
| **Min. Retention**       | N/A                     | 30 Days                  | 180 Days                    |

### Summary of Differences

| Aspect             | Hot Tier                                  | Cool Tier                                     | Archive Tier                                      |
| :----------------- | :---------------------------------------- | :-------------------------------------------- | :------------------------------------------------ |
| **Access Frequency** | Frequent                                  | Infrequent                                    | Rare                                              |
| **Access Latency** | Low                                       | Medium (Slightly higher than Hot)             | High (Hours for retrieval)                        |
| **Storage Cost**   | Highest                                   | Medium                                        | Lowest                                            |
| **Transaction Cost**| Lowest                                    | Medium                                        | Highest                                           |
| **Retrieval Cost** | N/A (Included in transactions)            | Moderate                                      | Highest (Includes rehydration)                    |
| **Min. Retention** | None                                      | 30 Days                                       | 180 Days                                          |
| **Best For**       | Active data, high performance needs       | Infrequently accessed, but quickly needed data| Long-term archiving, compliance, disaster recovery|

## How to Choose and Manage Tiers
1. **Analyze Access Patterns:** Use tools like Azure Monitor logs and Storage Analytics to understand how your data is being accessed.
2. **Set Default Tiers:** For a storage account, you can set a default tier (Hot or Cool).
3. **Configure Lifecycle Management:** Azure Storage Lifecycle Management policies are your best friend here! They allow you to automatically transition blobs between tiers based on rules you define (e.g., "move blobs older than 90 days to the Cool tier," or "delete blobs older than 365 days"). This is the most efficient way to manage costs over time.
    * **Example Rule:** If a blob is not accessed for 30 days, move it to the Cool tier. If it's then not accessed for another 180 days, move it to the Archive tier.
4. **Manual Tiering:** You can also manually change the tier of individual blobs via the Azure portal, Azure CLI, or PowerShell. This is useful for specific scenarios or when first migrating data.

## Related
- [[Azure Blob Storage]]

## Reference
* [Access tiers for Blob Data - Azure Storage | Microsoft Learn](https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview)
