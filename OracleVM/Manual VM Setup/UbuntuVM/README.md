### ⚠️ Prerequisite: Enable Virtualization in BIOS/UEFI

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

###  Step 1: Install Oracle VirtualBox

We use **Oracle VirtualBox** as the hypervisor — a tool that lets us create and manage virtual machines on top of our physical operating system.

- **Why VirtualBox?**  
  It's free, open-source, cross-platform, and beginner-friendly — perfect for DevOps learners who need safe and disposable environments.

Download from: [https://www.virtualbox.org](https://www.virtualbox.org)

![image](https://github.com/user-attachments/assets/59603495-ad0b-4a3c-ae34-67852246a09c)

---

### Step 2: Download Ubuntu Server ISO
Next, we will set up the Ubuntu virtual machine — the Linux preparation phase is now complete.

To download the ISO file, simply search in Google using the following keywords:

ubuntu 22 server iso

Alternatively, you can visit the official release page directly:
https://releases.ubuntu.com/jammy/

Make sure to download the server install image, not the desktop version. The server version is more suitable for VM environments and comes without a graphical interface, which is ideal for DevOps and terminal-based workflows.

![image](https://github.com/user-attachments/assets/2fd224e4-5e97-4241-9e3e-254517355f8c)

---
### Step 3: Mount the Ubuntu ISO to the Virtual Machine
Now repeat the same steps for Ubuntu as you did for CentOS.

Go back to the Ubuntu VM settings.

In the Storage section, click on the Empty optical drive under "Controller: IDE".

On the right, click the disk icon and select “Choose a disk file…”.

Locate and select the Ubuntu Server ISO file you downloaded earlier.

Once added, click OK to save the settings.

This will allow your virtual machine to boot from the Ubuntu ISO during the next startup, so you can begin the installation.

![image](https://github.com/user-attachments/assets/b2d8e8d2-034e-48c5-8525-aae4b87a1103)


---

Step 4: Start the VM and Begin Installation
Click Start to launch the virtual machine and begin the Ubuntu installation process.

From this point on, most of the setup will be straightforward — you can continue by clicking "Done" where applicable.

Each step is illustrated with screenshots to guide you through the process smoothly.


![image](https://github.com/user-attachments/assets/0c16049b-bf7b-4031-b9d2-67f2e1e0365f)

![image](https://github.com/user-attachments/assets/d8b110db-fba0-412c-a7a7-c9aece97ed8b)

![image](https://github.com/user-attachments/assets/6d6d7450-1d5e-4eaa-bf24-968bbe36607c)

Continue without updating

![image](https://github.com/user-attachments/assets/d73042e4-2dd0-4f1d-acbd-8198db9f84e7)

![image](https://github.com/user-attachments/assets/777a5b8d-9fa4-45d0-8b94-0e3452d0bc68)

You need to see the both network, which is good.
![image](https://github.com/user-attachments/assets/36970c8c-aa8d-43ed-90f6-27246d42620c)

![image](https://github.com/user-attachments/assets/6a995267-f7e5-44e3-a7c7-c5955caaa86d)

Choose the entire disk option and continue with done

![image](https://github.com/user-attachments/assets/ef2e701d-fbdf-4a2a-a3ec-f75ddeac89ce)

![image](https://github.com/user-attachments/assets/6acb7f26-2c50-48ff-82e3-3d8b31951005)

Fill out the entries

![image](https://github.com/user-attachments/assets/d083c720-ce06-40b6-9811-a6e80ca9ba13)

Choose "OpenSSH Server" option and continue with done

![image](https://github.com/user-attachments/assets/fd7f7013-ecb9-4ae3-a1a5-2417d02691ac)

![image](https://github.com/user-attachments/assets/d9b03ebc-c9a8-4dad-b202-7a84f2f65772)

![image](https://github.com/user-attachments/assets/3b061a64-7bb8-4ac2-9f7b-319336ed1082)


