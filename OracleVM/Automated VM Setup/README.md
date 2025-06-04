<img src="https://github.com/user-attachments/assets/55c20704-c8f7-4907-ad42-06dc80e17945" alt="Automated VM Setup" width="500"/>

### What is Automated VM Setup?
Automated VM setup is the smarter, faster way to spin up virtual machines — without clicking through every. single. prompt.

Instead of manually choosing your keyboard layout, time zone, disk partitioning, and praying you didn’t miss an SSH option (again), you define everything once in a config file or automation script. Then the VM builds itself. Magic? Not quite. Just DevOps.

🛠️ Popular tools used for automated VM provisioning:

Kickstart (for RHEL-based systems like CentOS/Rocky)

Preseed (for older Debian/Ubuntu systems)

Cloud-init (for Ubuntu and cloud VMs)

Packer (to create reusable VM images)

Vagrant (for lightweight, reproducible dev environments)

Terraform (for infrastructure as code — not just VMs!)

Ansible (for post-provisioning config & automation)

It’s like meal-prepping, but for your infrastructure. Set it up once, reuse it forever. Perfect for consistency, speed, and avoiding "Wait, why is this VM missing Python again?" nightmares.


🔧 ***Kickstart***  
*For RHEL-based systems like CentOS and Rocky Linux*  
_Used for automated installations via kickstart config files._

---

📦 ***Preseed***  
*For older Debian/Ubuntu systems*  
_Answers all installer prompts automatically using preseed files._

---

☁️ ***Cloud-init***  
*Commonly used in Ubuntu and cloud VMs*  
_Handles initial configuration in cloud environments (e.g., SSH, users)._

---

🛠️ ***Packer***  
*To create reusable and automated VM images*  
_Build consistent machine images for multiple platforms from a single source._

---

📦 ***Vagrant***  
*For lightweight, reproducible dev environments*  
_Quickly spin up disposable VMs for development/testing._

---

🌍 ***Terraform***  
*For infrastructure as code — not just VMs!*  
_Manage cloud infrastructure declaratively across providers._


