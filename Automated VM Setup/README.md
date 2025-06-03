## 🤖 What Is Automated VM Provisioning?

Instead of manually creating a virtual machine and installing an operating system step-by-step, **automated VM provisioning** allows you to set up the entire environment using code or scripts.

This includes:
- Automatically creating the VM
- Installing the OS (e.g., CentOS, Ubuntu)
- Pre-configuring software and services

Popular tools used for automation:
- **Vagrant** – for local VM setup with VirtualBox
- **Terraform** – for cloud-based infrastructure (e.g., AWS EC2)
- **Ansible / cloud-init** – for post-install configuration

> 🔄 This approach ensures consistency, saves time, and eliminates manual errors — a key practice in DevOps workflows.

---

## 📦 What is Vagrant?

**Vagrant** is a tool that allows you to create and manage virtual machines using simple configuration files.

- Works with VirtualBox, VMware, etc.
- Automates OS setup, networking, and provisioning
- Ideal for local development and DevOps labs

> 💡 With one command (`vagrant up`), you can spin up a ready-to-use VM — no manual clicks required.
