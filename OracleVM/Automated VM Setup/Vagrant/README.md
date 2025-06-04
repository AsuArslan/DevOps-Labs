## ═══ Vagrant for Virtual Machines ═══

> A minimal, declarative way to launch reproducible virtual environments — with zero OS setup friction.

---

### ▸ OS-Free Provisioning

Vagrant uses pre-built virtual machine images called **Boxes**.  
No ISO files, no installers, no surprises.  
Boxes can be pulled directly from [Vagrant Cloud](https://app.vagrantup.com/).

---

### ▸ The Vagrantfile

At the heart of each Vagrant project lies a **Vagrantfile** — a single file that defines how the VM should behave.

- Resource allocation (CPU, memory)
- Port forwarding and synced folders
- Provisioning scripts (e.g., shell, Ansible)

You write it once, and reuse it across teams and systems.  
Perfect for source control and automation pipelines.

---

### ▸ Common Workflow

```bash
vagrant init <boxname>   # Initialize project with a box
vagrant up               # Start and provision the VM
vagrant ssh              # Access the VM
vagrant halt             # Gracefully shut down
vagrant destroy          # Remove everything
