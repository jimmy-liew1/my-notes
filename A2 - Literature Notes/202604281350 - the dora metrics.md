---
up:
date: 2026-04-28
created: 2026-04-28 13:50
title: The DORA metrics
aliases:
  - DORA
  - DevOps Research and Assessment
status: budding
tags:
  - devops
  - type/literature-note
link:
---
**DevOps Research and Assessment (DORA)** metrics are four key performance indicators established by Google’s DevOps Research and Assessment team to measure software development velocity and stability. They distinguish high-performing teams from low-performing ones by tracking deployment frequency, lead time for changes, change failure rate, and time to restore service.

This video explains the four DORA metrics and their significance in DevOps:
<iframe width="560" height="315" src="https://www.youtube.com/embed/lqsENcje41w?si=dvsvsS5uJpj-P-0y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## The Four Key DORA Metrics
- **[Deployment Frequency](https://www.google.com/search?client=firefox-b-d&channel=entpr&q=Deployment+Frequency&mstk=AUtExfCrfvWl9J3nQh-gfxCJj9oh7rNPcIQ6kSOrth_Z1pTKGYE0mQkyc8xhZr63eh1CBysHYLs3h7R90EAPBerYXKVL3x1X_NfJ_MzVjykeCFpSsw96ivxorpMG2BfP6CnuJkY&csui=3&ved=2ahUKEwjGoa_twI-UAxVdyjgGHR9lK1AQgK4QegYIAQgCEAQ) (DF):** How often an organization successfully releases to production (e.g., daily, weekly, on-demand).
- **[Lead Time for Changes](https://www.google.com/search?client=firefox-b-d&channel=entpr&q=Lead+Time+for+Changes&mstk=AUtExfCrfvWl9J3nQh-gfxCJj9oh7rNPcIQ6kSOrth_Z1pTKGYE0mQkyc8xhZr63eh1CBysHYLs3h7R90EAPBerYXKVL3x1X_NfJ_MzVjykeCFpSsw96ivxorpMG2BfP6CnuJkY&csui=3&ved=2ahUKEwjGoa_twI-UAxVdyjgGHR9lK1AQgK4QegYIAQgCEAY) (LTFC):** The time it takes for a commit to move from code committed to code successfully running in production.
- **[Change Failure Rate](https://www.google.com/search?client=firefox-b-d&channel=entpr&q=Change+Failure+Rate&mstk=AUtExfCrfvWl9J3nQh-gfxCJj9oh7rNPcIQ6kSOrth_Z1pTKGYE0mQkyc8xhZr63eh1CBysHYLs3h7R90EAPBerYXKVL3x1X_NfJ_MzVjykeCFpSsw96ivxorpMG2BfP6CnuJkY&csui=3&ved=2ahUKEwjGoa_twI-UAxVdyjgGHR9lK1AQgK4QegYIAQgCEAg) (CFR):** The percentage of deployments that cause a failure in production, requiring immediate remediation such as a rollback or hotfix.
- **[Time to Restore Service](https://www.google.com/search?client=firefox-b-d&channel=entpr&q=Time+to+Restore+Service&mstk=AUtExfCrfvWl9J3nQh-gfxCJj9oh7rNPcIQ6kSOrth_Z1pTKGYE0mQkyc8xhZr63eh1CBysHYLs3h7R90EAPBerYXKVL3x1X_NfJ_MzVjykeCFpSsw96ivxorpMG2BfP6CnuJkY&csui=3&ved=2ahUKEwjGoa_twI-UAxVdyjgGHR9lK1AQgK4QegYIAQgCEAo) (TTRS/MTTR):** The time it takes to recover from a production failure or incident.

![For Key Metrics|732](https://storage.googleapis.com/gweb-cloudblog-publish/images/Calculating_the_metrics_frOhcbp.max-2000x2000.jpg)<br>The table above adopted from [Google Cloud Blog](https://cloud.google.com/blog/products/devops-sre/using-the-four-keys-to-measure-your-devops-performance).

## Performance Benchmarks (2025) 
Teams are typically categorized based on their performance across these metrics: 
- **Elite:** Multiple deployments per day; lead time < 1 day; < 15% change failure rate; < 1 hour time to restore.
- **High:** Daily/weekly deployments; 1 day–1 week lead time; 16–30% failure rate; < 1 day time to restore.
- **Medium:** Weekly/monthly deployments; 1 week–1 month lead time; 16–30% failure rate; 1 day–1 week time to restore.
- **Low:** Monthly/biannual deployments; 1–6 months lead time; 46–60% failure rate; 1 week–1 month time to restore. 

## Benefits and Purpose
- **Balanced Measurement:** They balance speed (DF, LTFC) with stability (CFR, TTRS) to ensure quality isn't sacrificed for velocity.
- **Actionable Insights:** They help identify bottlenecks in the CI/CD pipeline and areas for improvement.
- **Continuous Improvement:** Used as indicators for maturity, they guide organizations toward better DevOps practices and higher efficiency. 

>_**Note:** In 2024, some frameworks began referencing a fifth metric, **Deployment Rework Rate**, to further measure stability, though the original four remain the industry standard._

## References
- [Are you an Elite DevOps performer? Find out with the Four Keys Project](https://cloud.google.com/blog/products/devops-sre/using-the-four-keys-to-measure-your-devops-performance) | Google Cloud Blog