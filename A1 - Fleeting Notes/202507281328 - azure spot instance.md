---
date: 2025-07-28
created: 2025-07-28 13:07
aliases:
  - Spot Instances
tags:
  - type/fleeting-note
  - azure
link:
---
**Azure Spot instances** allow you to provision virtual machines at a reduced cost, but these virtual machines can be stopped by Azure when Azure needs the capacity for other pay-as-you-go workloads, or when the price of the spot instance exceeds the maximum price that you have set. These virtual machines are good for dev, testing, or for workloads that do not require any specific SLA.

**Azure Spot Virtual Machines** (also called Spot Instances) are ==a cost-effective way to run stateless and interruptible workloads on Azure by leveraging unused capacity at a significant discount== (up to 90% off pay-as-you-go prices). These instances can be evicted with short notice (30 seconds) when Azure needs the capacity back. They are suitable for workloads that can tolerate interruptions, like [batch processing](https://www.google.com/search?rlz=1C1GCEA_enUS1114MY1114&cs=0&sca_esv=2dcb3ec73b8f4595&q=batch+processing&sa=X&ved=2ahUKEwi_6oeHnOmOAxUz-DgGHSmfAhsQxccNegQIBRAB&mstk=AUtExfDTorkHvX-FjLVx0PDnaEYvVRDn7UgydLmJWYBmQFfrmQ31SCj0BX0CoO5Z62ITIQeYFWkRwidMEPaxpfOmvFWLyh5Xk4KHgpeWRGpaCHy3dIWs0WcE-5jJAvNYavDmUwU&csui=3), [testing](https://www.google.com/search?rlz=1C1GCEA_enUS1114MY1114&cs=0&sca_esv=2dcb3ec73b8f4595&q=testing&sa=X&ved=2ahUKEwi_6oeHnOmOAxUz-DgGHSmfAhsQxccNegQIBRAC&mstk=AUtExfDTorkHvX-FjLVx0PDnaEYvVRDn7UgydLmJWYBmQFfrmQ31SCj0BX0CoO5Z62ITIQeYFWkRwidMEPaxpfOmvFWLyh5Xk4KHgpeWRGpaCHy3dIWs0WcE-5jJAvNYavDmUwU&csui=3), and [development environments](https://www.google.com/search?rlz=1C1GCEA_enUS1114MY1114&cs=0&sca_esv=2dcb3ec73b8f4595&q=development+environments&sa=X&ved=2ahUKEwi_6oeHnOmOAxUz-DgGHSmfAhsQxccNegQIBRAD&mstk=AUtExfDTorkHvX-FjLVx0PDnaEYvVRDn7UgydLmJWYBmQFfrmQ31SCj0BX0CoO5Z62ITIQeYFWkRwidMEPaxpfOmvFWLyh5Xk4KHgpeWRGpaCHy3dIWs0WcE-5jJAvNYavDmUwU&csui=3).

### Related Concept
* [Use Azure Spot Virtual Machines - Azure Virtual Machines | Microsoft Learn](https://learn.microsoft.com/azure/virtual-machines/spot-vms)
* [Configure virtual machine availability - Training | Microsoft Learn](https://learn.microsoft.com/training/modules/configure-virtual-machine-availability/)
* [Reserved Instances vs. Spot Instances: Maximize Your Savings Today](https://www.alphaus.cloud/en/blog/reserved-instances-vs-spot-instances-maximize-your-savings-today)
* [[reserved instances|Reserved Instance]]