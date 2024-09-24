---
up: "[[Server Infrastructure MOC]]"
tags:
  - infrastructure/HCI
  - infrastructure/hyper-converged
  - hypervisor
  - vmware
---
The server infrastructure has changed from physical to software-defined architecture, or [[Software-Defined Infrastructure|software defined infrastructure]] - in short, it call "[[Hyper-converged Infrastructure|hyper-converge]]".

### Hyper-converged Infrastructure (HCI) vs. Hypervisor
A hypervisor, also known as a virtual machine monitor or VMM, is software that creates and runs virtual machines (VMs). A hypervisor allows one host computer to support multiple guest VMs by virtually sharing its resources, such as memory and processing. 

#### Type of Hypervisors
There are two main hypervisor types, referred to as “Type 1” (or “bare metal”) and “Type 2” (or “hosted”). A **type 1 hypervisor** acts like a lightweight operating system and runs directly on the host’s hardware, while a **type 2 hypervisor** runs as a software layer on an operating system, like other computer programs. 

>*Read more: [VMware: Hypervisor](https://www.vmware.com/topics/glossary/c*ontent/hypervisor.html?resource=cat-1243073610#cat-1243073610)

### How Does Hyper-converged Infrastructure Work?
Four tightly integrated software components make up a hyper-converged platform: 
-   Storage virtualization
-   Compute virtualization
-   Networking virtualization
-   Advanced management capabilities including automation 

The virtualization software abstracts and pools underlying resources, then dynamically allocates them to applications running in VMs or containers. Configuration is based on policies aligned with the applications, eliminating the need for complicated constructs like LUNs and volumes.

### What Can You Do with HCI?
- **Build a private cloud***: Deploy cloud-like infrastructure on-premises with lower costs, more control, and improved security. Choose from multiple hardware possibilities from our certified partners.
- **Extend to [public cloud](https://www.vmware.com/topics/glossary/content/public-cloud)**: Choose an as-a-service option from the largest HCI cloud ecosystem for faster speed of deployment and less time spent managing infrastructure.
- **Achieve true [hybrid cloud](https://www.vmware.com/topics/glossary/content/hybrid-cloud)**: Manage a mix of VM- and container-based applications, deployed across a mix of data center, public cloud and edge environments with VMware hybrid cloud.

The virtualization software abstracts and pools underlying resources, then dynamically allocates them to applications running in VMs or containers. Configuration is based on policies aligned with the applications, eliminating the need for complicated constructs like LUNs and volumes.

### Other References:
- [Hyper-converged Infrastructure | VMware](https://www.vmware.com/asean/products/hyper-converged-infrastructure.html)
- [Hypervisor | VMware - Glossary](https://www.vmware.com/topics/glossary/content/hypervisor.html)
- [Hyper-converged Infrastructure | Nutanix](https://www.nutanix.com/sg/hyperconverged-infrastructure)
- [Converged vs. Hyper-converged Infrastructure | Nutanix](https://www.nutanix.com/sg/info/converged-vs-hyperconverged-infrastructure)
- [Converged Infrastructure vs. Hyper-converged Infrastructure | BMC](https://www.bmc.com/blogs/converged-infrastructure-vs-hyper-converged-infrastructure/)