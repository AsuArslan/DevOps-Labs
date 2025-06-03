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

### 🛑 How to Enable Virtualization in BIOS/UEFI

To enable virtualization (VT-x or AMD-V), follow these steps:

1. **Restart your computer.**
2. During the boot process (before Windows starts), press the correct key to enter BIOS/UEFI.  
   Common keys are:
   - `F2`
   - `Delete`
   - `Esc`
   - `F10`
   - `F12`

   > 💡 The correct key depends on your computer’s brand. You’ll usually see something like  
   > “Press [key] to enter Setup” when the computer starts.

3. Once inside BIOS/UEFI:
   - Go to the **Advanced**, **CPU Configuration**, or **Security** tab (depending on the system).
   - Look for an option called:
     - **Intel VT-x** or **Intel Virtualization Technology** (for Intel CPUs)
     - **SVM Mode** or **AMD-V** (for AMD CPUs)
   - Set it to **Enabled**.

4. **Save and exit** the BIOS (usually `F10` key), and allow the system to restart.

Once this is done, VirtualBox will be able to run virtual machines successfully.


