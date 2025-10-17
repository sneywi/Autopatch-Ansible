# Autopatch-Ansible 🔁

**Automated security patch compliance system for AWS EC2 instances**

Autopatch-Ansible scans AWS EC2 instances, identifies pending updates, applies critical patches, and generates HTML compliance reports - all without manual intervention.

---

## The Problem

Managing patches manually across multiple servers is:
- ⏱️ **Time-consuming** - Hours spent SSH-ing into servers
- ❌ **Error-prone** - Easy to miss critical updates
- 📊 **Poor visibility** - No centralized compliance view
- 📝 **Inconsistent** - Manual documentation becomes outdated
- ⚠️ **High risk** - One forgotten server = security breach

---

## The Solution

Autopatch-Ansible transforms patch management into an automated, reliable workflow.

### What It Does

1. **Discovers** - Finds all running EC2 instances using dynamic AWS inventory
2. **Assesses** - Checks each server for available updates
3. **Prioritizes** - Identifies critical security updates vs routine patches
4. **Patches** - Applies approved updates safely with serial execution
5. **Reports** - Emails HTML compliance dashboard with audit trails

### Key Benefits

✅ **Save 95% of time** - From hours to minutes  
✅ **Zero human errors** - Consistent, repeatable process  
✅ **Complete visibility** - Real-time compliance metrics  
✅ **Automatic documentation** - Every run is logged  
✅ **Risk reduction** - Serial execution prevents mass outages  
✅ **Scalable** - Works for 10 or 1,000 servers  

---

## Features

- **Dynamic AWS Inventory** - Automatic EC2 instance discovery
- **Conditional Logic** - Filters critical updates only
- **Ansible Vault** - Secure secrets management
- **Jinja2 Templates** - Professional HTML reports
- **Email Automation** - Compliance summaries (0% → 100%)

---

## Prerequisites

- AWS CLI
- Python3 & pip
- Python venv
- Ansible
- boto3
- AWS Ansible collection

---

## How to Use This Repo

1. Clone the repository
```bash
git clone https://github.com/sneywi/Autopatch-Ansible.git
cd Autopatch-Ansible
```
2. Configure AWS credentials
```bash
aws configure
```
3. Edit your .pem file
```bash
vi ansible-key.pem
```
4. Edit your ansible-vault credentials
```bash
ansible-vault edit group_vars/all/pass.yml
```
5. Create a new SSH keypair
```bash
ssh-keygen -t rsa -b 4096
```
After creating 'n' number of manage/target nodes:
6. Name them sequentially
```bash
./tagging.sh
```
7. Setup Passwordless SSH to All Managed Nodes
```bash
./copy-public-key.sh
```
8. Execute your playbook!
```bash
ansible-playbook playbooks/execute_playbook.yaml
```
---

## Email Reports

The system sends two automated emails:

📧 **Pre-Patch Report** - Shows what needs patching (0% compliance)  

<img width="1919" height="1079" alt="1" src="https://github.com/user-attachments/assets/de4681f0-b79f-44e5-b249-c42e6ee5abfd" />
<img width="1919" height="1079" alt="2" src="https://github.com/user-attachments/assets/a3ad9d8c-fe06-40ba-820f-4c81b271b61d" />
<img width="1919" height="1079" alt="3" src="https://github.com/user-attachments/assets/6ae311c7-0db5-48d3-896a-c39435eefffd" />

---

📧 **Post-Patch Report** - Shows what got fixed (100% compliance)

<img width="1919" height="1079" alt="4" src="https://github.com/user-attachments/assets/5ae6565f-4a0f-4dd7-ac46-e36d1004b866" />
<img width="1919" height="1079" alt="5" src="https://github.com/user-attachments/assets/74fc70cb-cfa9-4a22-8f5c-28187d70d0a3" />
<img width="1919" height="1079" alt="6" src="https://github.com/user-attachments/assets/e235997d-a574-4894-a5fc-5fec18001545" />

---

## Documentation

Full technical breakdown: [Hashnode Article](https://iacverse.hashnode.dev/autopatch-ansible-building-an-automated-security-patch-compliance-system-with-ansible-and-aws)

---

## Author

Built by [@sneywi](https://github.com/sneywi)
