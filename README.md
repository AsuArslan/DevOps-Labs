# Oracle VM & Virtual Machines in DevOps

This branch is dedicated to my exploration and hands-on practice with Virtual Machines (VMs), particularly using Oracle VM/VirtualBox. VMs are essential tools for learning DevOps effectively in a safe, isolated environment.

---

## 🧠 What is a Virtual Machine (VM)?

A **Virtual Machine** is a software-based emulation of a physical computer. It allows you to run a complete operating system (such as Linux or Windows) inside your own machine, without affecting your base system.

VMs have their own:
- CPU
- RAM
- Disk
- Operating System

All running *virtually* within your actual physical computer.

---

## 🔧 Oracle VM / VirtualBox

**Oracle VM** is a virtualization tool developed by Oracle. A more commonly used alternative is **VirtualBox**, also from Oracle, which is beginner-friendly and widely supported in the DevOps learning community.

With VirtualBox, I can:
- Create Linux-based test servers
- Simulate multi-machine environments
- Safely break, fix, and rebuild systems
- Practice installing and configuring DevOps tools (e.g., Docker, Jenkins, Ansible, etc.)

---

## 🛠️ Manual VM vs. Automated VM

### 🖐️ Manual VM
This refers to **manually installing and setting up** a virtual machine using a GUI tool like VirtualBox:
- You create the VM manually
- Select disk size, RAM, CPU, etc.
- Mount an ISO (e.g., Ubuntu or CentOS)
- Install and configure OS by hand

🔹 Best for beginners to understand how systems are built and structured  
🔹 Helps with practicing basic sysadmin tasks

---

### ⚙️ Automated VM (IaC - Infrastructure as Code)

Automated VMs are created and configured using code-based tools like:

- **Vagrant**
- **Terraform**
- **Ansible**

With a few lines of code, you can:
- Spin up multiple VMs
- Define their configuration
- Provision them automatically
- Destroy and recreate them in seconds

🔹 Used in real-world DevOps pipelines  
🔹 Makes setups reproducible and scalable  
🔹 Fits under *Infrastructure as Code (IaC)* in DevOps

---

## 🚀 Why VMs Matter in DevOps

| Use Case | Purpose |
|----------|---------|
| 🧪 Lab Environments | Safe space to try tools and break things |
| 🔄 CI/CD Testing | Run builds, deploy apps inside VM |
| 🔐 Security Practice | Practice firewall, SSH, user config in isolation |
| 🛠️ Tool Installation | Jenkins, Docker, Kubernetes inside VM |
| ☁️ Cloud Simulation | Simulate AWS/GCP/Linux servers locally |

---

📌 **Note**: This branch focuses on the **manual VM approach**, but will gradually include **automated IaC-based VMs** as well.

Happy virtualizing! ☁️💻

---

## ⚠️ Prerequisite: Enable Virtualization in BIOS/UEFI

Before installing Oracle VM (VirtualBox), make sure **virtualization is enabled** on your system:

- For **Intel** CPUs: VT-x  
- For **AMD** CPUs: AMD-V / SVM

You can enable this setting in your system's BIOS or UEFI menu. Without this, VirtualBox may fail to launch virtual machines properly.

Once virtualization is enabled, you're ready to proceed with the setup.





# Oracle VM & Virtual Machines in DevOps

This branch is dedicated to my exploration and hands-on practice with Virtual Machines (VMs), particularly using Oracle VM/VirtualBox. VMs are essential tools for learning DevOps effectively in a safe, isolated environment.

Here, I share what I've learned about the role of VMs in DevOps, their types, and how they help simulate real-world environments during the learning process.

> 📘 *This section serves as an introduction and conceptual overview.  
> For practical setup instructions, please continue below.*  
>  
> ⬇️⬇️⬇️

---

## ⚠️ Prerequisite: Enable Virtualization in BIOS/UEFI

Before installing Oracle VM (VirtualBox), make sure **virtualization is enabled** on your system:

- For **Intel** CPUs: VT-x  
- For **AMD** CPUs: AMD-V / SVM

You can enable this setting in your system's BIOS or UEFI menu. Without this, VirtualBox may fail to launch virtual machines properly.

Once virtualization is enabled, you're ready to proceed with the setup.

