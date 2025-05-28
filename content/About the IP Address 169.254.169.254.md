---
date: 2025-05-28
created: 2025-05-28 20:05
tags:
  - azure
  - networking
link:
---
The IP address `169.254.169.254` is a **special-purpose IP address** used by cloud providers like **Azure, AWS, and Google Cloud** to provide **instance metadata** to virtual machines (VMs).   It's part of a range (169.254.0.0 - 169.254.255.255) reserved for communication within a local network when DHCP is not available or fails. In cloud contexts, it often serves as a metadata endpoint to access information about the instance.

### What is 169.254.169.254 Used For?
- It allows **VMs to access metadata** about themselves **without needing an internet connection**.
- Metadata includes details like **instance ID, networking configuration, IAM roles, and security credentials**.
- Cloud services use this IP to provide **internal communication** between the VM and the cloud provider.

### Is It a Standard IP Address?
- **Yes, but only for cloud environments**.
- It belongs to the **link-local address range** (`169.254.0.0/16`), which is reserved for **internal communication** within a network.
- This means it **cannot be routed externally**—it only works **inside the cloud provider’s infrastructure**.

### How Does It Work?
- When a VM queries `http://169.254.169.254`, it retrieves metadata about itself.
- Example command to fetch metadata:
    ```
    curl -H "Metadata: true" "http://169.254.169.254/metadata/instance?api-version=2021-02-01"
    ```
    
- This is **critical for automation**, security, and configuration management in cloud environments.