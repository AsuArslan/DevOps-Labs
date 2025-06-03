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


---

## 🧩 Step-by-Step: Install VirtualBox and Set Up a Virtual Machine

Now that virtualization is enabled on your system, let's move on to installing Oracle VirtualBox and creating your first virtual machine.

---

### ✅ Step 1: Download and Install Oracle VirtualBox

1. Visit the official website: [https://www.virtualbox.org](https://www.virtualbox.org)
2. Click on `Downloads` and select **Windows hosts**.
3. Download the `.exe` file and run the installer.
4. Proceed with the default installation steps (Next → Next → Install).

> 📷 Google image search:  
> `virtualbox installation windows screenshot`

---

### 💾 Step 2: Download a Linux ISO (Ubuntu)

You need an operating system to install inside your VM. For starters, **Ubuntu Desktop** is beginner-friendly and widely supported.

1. Visit: [https://ubuntu.com/download/desktop](https://ubuntu.com/download/desktop)
2. Download the latest **Ubuntu LTS ISO** file (e.g., `ubuntu-22.04.4-desktop-amd64.iso`).

> 📷 Google image search:  
> `ubuntu iso download page`

---

### 🛠️ Step 3: Create a New Virtual Machine in VirtualBox

1. Open VirtualBox and click **"New"**.
2. Give your VM a name (e.g., `Ubuntu-DevOps`).
3. Set Type = `Linux`, Version = `Ubuntu (64-bit)`
4. Assign memory (RAM) — 2048 MB or more is recommended.
5. Create a virtual hard disk → Use default `VDI`, dynamically allocated → 20 GB+

> 📷 Google image search:  
> `virtualbox new vm settings ubuntu`

---

### 📂 Step 4: Mount the ISO and Start the VM

1. Select your VM and click **"Start"**.
2. VirtualBox will ask you to select a start-up disk → browse and select the **Ubuntu ISO** you downloaded.
3. The VM will boot using the ISO — just like installing an OS on a real PC.

> 📷 Google image search:  
> `virtualbox mount iso ubuntu`

---

### 💡 Step 5: Install Ubuntu (Inside the VM)

1. Choose language and click `Install Ubuntu`.
2. Select:
   - Keyboard layout
   - Normal installation
   - Use entire virtual disk
3. Choose a username and password.
4. Wait for installation to complete and click `Restart Now`.

> 📷 Google image search:  
> `ubuntu installation steps virtualbox`

---

### 🧪 Step 6: Your Virtual DevOps Lab Is Ready!

Once Ubuntu is installed, your VM will boot into the OS like a real computer.

From here, you can:
- Open the terminal
- Install tools like Git, Docker, or Jenkins
- Simulate real server environments
- Practice DevOps setups safely

---

## 🎉 Summary

By following these steps, you now have:
- ✅ Oracle VirtualBox installed
- ✅ A virtual Linux machine running Ubuntu
- ✅ A ready-to-use DevOps lab environment

Up next: We'll explore what you can do **inside** the VM — such as Docker installation, network configs, and CI/CD experiments.



