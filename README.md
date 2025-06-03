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

---

## 🧩 Step-by-Step: Install VirtualBox and Set Up a CentOS Virtual Machine (with Explanations)

---

### ✅ Step 1: Install Oracle VirtualBox

We use **Oracle VirtualBox** as the hypervisor — a tool that lets us create and manage virtual machines on top of our physical operating system.

- **Why VirtualBox?**  
  It's free, open-source, cross-platform, and beginner-friendly — perfect for DevOps learners who need safe and disposable environments.

Download from: [https://www.virtualbox.org](https://www.virtualbox.org)

![image](https://github.com/user-attachments/assets/59603495-ad0b-4a3c-ae34-67852246a09c)

---

### 💾 Step 2: Download CentOS ISO

We need an operating system (OS) to install inside our virtual machine. In this case, we choose **CentOS**:

- **Why CentOS (or RHEL-based systems)?**  
  It mirrors real-world enterprise environments. Many DevOps tools are tested and deployed on Red Hat-based systems in production.  
  CentOS (or successors like AlmaLinux/Rocky) offers:
  - Stability
  - Predictable package management with `yum`/`dnf`
  - Systemd-based architecture common in servers

## 📦 Choosing the Right CentOS ISO: `boot.iso` vs `dvd.iso`

When downloading CentOS, you may notice there are two common ISO types: `boot.iso` and `dvd1.iso`. Here's the difference:

### 🔹 `boot.iso`
- A small installer (~1.2 GB)
- **Requires internet** during installation
- Downloads the rest of the system from CentOS repositories

✅ Use if:
- You have a fast and stable internet connection  
- You want to do a minimal or custom install

🔗 Download: [CentOS 9 Stream boot.iso (x86_64)](https://mirror.stream.centos.org/9-stream/BaseOS/x86_64/iso/)

---

### 🔸 `dvd1.iso`
- Full offline installer (~7–9 GB)
- Includes everything you need to install CentOS
- No internet required during setup

✅ Use if:
- You prefer a full GUI-based or offline install  
- You're installing on a virtual machine and want fewer installation errors

🔗 Download: [CentOS 9 Stream DVD ISO Mirrors](https://www.centos.org/download/)

---

📌 **Recommendation**: For virtual machine installation (like in VirtualBox), `dvd1.iso` is usually easier and more reliable.


---

### 🛠️ Step 3: Create a New VM in VirtualBox

1. Click `New` in VirtualBox.

2. Fill in:
   - **Name**: e.g., `CentOS-Lab`
   - **Type**: `Linux`  
     > This tells VirtualBox to optimize settings for Linux-based systems.
   - **Version**: `Red Hat (64-bit)`  
     > CentOS is built from Red Hat sources, so this is the most compatible choice.

3. **Memory (RAM)**: Allocate at least `2048 MB` (2 GB)  
   > This ensures the VM can run basic tools and GUI if needed. Lower memory might freeze or slow down installation.

4. **Hard Disk**:
   - Create a virtual hard disk now.
   - Choose **VDI (VirtualBox Disk Image)** → default, works best with VirtualBox.
   - **Dynamically allocated**: Uses disk space as needed, not all at once.
   - Set **Size** to at least `20 GB`  
     > Allows you to install packages and tools without worrying about space.

---

---

## 🖱️ Optional: Set Pointing Device to "USB Tablet"

Before starting the VM, it's recommended to change the pointing device to **USB Tablet**.

### 🔹 Why?

By default, VirtualBox uses a "PS/2 Mouse" device for input, which can sometimes cause issues like:
- Mouse pointer **not aligning correctly** with the host system
- Cursor **lagging or jumping** inside the VM
- Difficulty in **seamlessly moving the cursor** between host and VM

The **USB Tablet** option provides:
- Better integration with the host system
- More accurate and responsive mouse control
- Especially helpful if you're using a graphical (GUI) installation

### 🔧 How to Set It:
1. Go to **VirtualBox Manager**
2. Select your VM → Click **Settings**
3. Navigate to **System > Motherboard** tab
4. Set **Pointing Device** to `USB Tablet`

![image](https://github.com/user-attachments/assets/01f6c08a-428a-4cc1-ad5f-06ef82ca8a19)



> It’s a small change that can make your graphical installation and VM usage much smoother.





### 📂 Step 4: Mount the ISO and Boot

- Select the VM and click `Start`.
- When prompted, select the **CentOS ISO** you downloaded earlier.

> This simulates booting from a CD — it lets the VM "install" CentOS as if it were a real computer.

![image](https://github.com/user-attachments/assets/e29dfcdd-cefb-49c0-a3a8-bcd05f174304)
![image](https://github.com/user-attachments/assets/249d89eb-fe22-49d7-a7b1-ebf904a385a6)
![image](https://github.com/user-attachments/assets/a6190c25-89fc-4560-90f3-f22094b12688)


---

### 🧱 Step 5: CentOS Installation (Explained Choices)

1. Choose **Language & Keyboard Layout**: English / your local settings.

   ![image](https://github.com/user-attachments/assets/1357e0db-938d-4e1f-add8-4f37c00d936d)


3. **Installation Destination**:
   - Select the available virtual hard disk.
   - Click "Done" — CentOS will automatically partition the disk.
   > For beginners, automatic partitioning is fine.

4. **Software Selection**:
   - You can choose:
     - **Minimal Install** → for lightweight CLI-only system.
     - **Server with GUI** → for desktop-like experience.
   - **Why choose GUI or not?**
     - CLI (command line) is closer to real-world DevOps environments.
     - GUI is helpful if you're new to Linux and prefer visual navigation.
     - In DevOps learning labs, CLI is often preferred for Docker, Ansible, etc.

5. **Network & Hostname** (optional):
   - Enable network connection if you plan to install packages.
   - Set a hostname like `centos-lab.local`.

6. **User Settings**:
   - Set root password.
   - Create a regular user with admin rights (recommended).
   - If you create a strong password, clicking the Done button once will be enough.
However, if the password is weak, you'll need to click the Done button twice to confirm.

     
   ![image](https://github.com/user-attachments/assets/96977608-b7fa-4a1b-9d7b-5aa8368259c5)
   ![image](https://github.com/user-attachments/assets/1fe9b239-2fcd-4818-bee9-077594b6d5c7)

We’ve set a password for the root user, configured the network, and selected the operating system — now we’re ready to click "Begin Installation".
Click `Begin Installation`, then wait for the process to complete and reboot.

![image](https://github.com/user-attachments/assets/38ae2906-4e22-4163-b1a3-83673f2f9759)


The installation may take approximately 10 to 15 minutes to complete.

![image](https://github.com/user-attachments/assets/ad396c51-1a6e-429d-9020-14d5a619e651)

Once the installation is complete, do not click the Reboot button immediately. Instead, return to the main VirtualBox window and shut down the virtual machine first.
Then, remove the ISO file from the virtual optical drive —
otherwise, the VM will boot from the ISO again and restart the installation process.

![image](https://github.com/user-attachments/assets/c5abfe00-6c4a-4b78-9893-965682e32e0d)

![image](https://github.com/user-attachments/assets/3510963e-47fd-49dc-b525-ec793b2ba40b)

![image](https://github.com/user-attachments/assets/47bae81f-b40e-40ff-abc9-99701e7434bd)

When you see the powered-off word in there, you can start the process for iso.

![image](https://github.com/user-attachments/assets/0f974dd6-f7ff-42a1-8edd-ac28449e3c84)

Go to the settings.

![image](https://github.com/user-attachments/assets/9245f747-3c73-4371-aead-013a19a88ff0)

And remove the iso folder from the machine.

![image](https://github.com/user-attachments/assets/2bd2f9c3-b56b-4bfe-a05e-c0b410b6b83c)

---

### 🧪 Step 6: First Boot — You're In!

After rebooting, log in with your created user.

Now you're ready to:
- Run `sudo dnf update`
- Install Git, Docker, Ansible, etc.
- Practice SSH, firewalls, and service configuration

---

## 🧠 Summary of Key Decisions & Why

| Step | Choice | Why |
|------|--------|-----|
| OS | CentOS / Alma / Rocky | Mirrors enterprise production servers |
| RAM | ≥ 2048 MB | Ensures smooth performance |
| Disk | VDI, 20 GB+, dynamically allocated | Flexible and space-efficient |
| Install type | Minimal vs. Server GUI | CLI = realistic for DevOps; GUI = visual support for beginners |
| VM type | Red Hat (64-bit) | Matches CentOS compatibility |
| User setup | Create regular user + root | Follows best practice and security |

---

✅ You now have a CentOS-based virtual lab ready for DevOps experimentation.  
Next, we'll install core tools like Docker, NGINX, or Jenkins.

