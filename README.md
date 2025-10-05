# ⚙️ Ansible Automation — Infrastructure Configuration & Orchestration

## 📘 Overview

This repository demonstrates my **Ansible expertise** through a complete, hands-on progression — from foundational concepts to cloud-based automation.  
It showcases how I design, configure, and manage infrastructure declaratively using **Ansible Playbooks**, **roles**, and **modules**, following **real-world DevOps practices**.

The goal of this repository is to help recruiters and technical reviewers quickly assess:

- 🧠 Understanding of **Ansible architecture**, configuration management, and orchestration
- 🧩 Ability to automate **infrastructure provisioning** and **application deployment**
- ☁️ Experience working with **AWS**, **Linux**, and **multi-node environments**

---

## 🧩 Exercises Overview

### 1️⃣ Introduction to Ansible

- What is Ansible, why it’s agentless, and how it differs from Chef/Puppet.
- SSH-based control mechanism and ad-hoc commands.
- **Focus:** Setup and basic understanding of infrastructure automation.

---

### 2️⃣ Setup & Infrastructure

- Installed Ansible on a control node.
- Created inventory files with host groups (web, db).
- Verified node connectivity with the **ping module**.
- **Focus:** Inventory management and connectivity testing.

---

### 3️⃣ YAML & JSON

- Learned **YAML syntax** (key-value pairs, lists, dictionaries).
- Compared YAML vs JSON for configuration.
- **Focus:** Writing clean, human-readable automation files.

---

### 4️⃣ Ad Hoc Commands

- Used ad hoc commands for one-time tasks.
- **Examples:**
  ```bash
  ansible all -m ping
  ansible web -a "df -h"
  ```
- **Focus:** Quick automation without playbooks.

---

### 5️⃣ Playbooks & Modules

- Created **playbooks** for repeatable tasks.
- Explored built-in modules: `copy`, `service`, `yum`, `file`, `template`.
- Learned to troubleshoot and find module documentation.
- **Focus:** Declarative automation using playbooks.

---

### 6️⃣ Variables & Facts

- Defined variables in inventory, playbooks, and separate var files.
- Used `debug` module to print variables.
- Explored facts using `ansible_facts`.
- **Focus:** Parameterization and dynamic data handling.

---

### 7️⃣ Decision Making & Loops

- Conditional execution using **when statements**.
- Iterative tasks using `loop` and `with_items`.
- **Example:** Installing multiple packages dynamically.
- **Focus:** Logical automation and reusability.

---

### 8️⃣ File, Copy, Template & Handlers

- Managed files, templates, and handlers for notifications.
- Used **Jinja2 templates** for dynamic file generation.
- **Focus:** Event-driven automation and configuration templating.

---

### 9️⃣ Roles & AWS Automation

- Structured automation using **roles** (tasks, vars, handlers, templates).
- Implemented automation for **AWS EC2 provisioning** via Ansible.
- **Focus:** Enterprise-grade modular automation.

---

## 🧰 Tools & Technologies

| **Category**                 | **Tools / Services**                                       |
| ---------------------------- | ---------------------------------------------------------- |
| **Automation Tool**          | Ansible                                                    |
| **Cloud Provider**           | AWS                                                        |
| **Scripting Languages**      | YAML, Jinja2                                               |
| **OS / Platform**            | Linux (Ubuntu, CentOS)                                     |
| **Modules Used**             | `ping`, `copy`, `template`, `yum`, `service`, `user`, etc. |
| **Version Control**          | Git & GitHub                                               |
| **Configuration Management** | ansible.cfg, inventory files                               |
| **Orchestration**            | Playbooks, Roles, Handlers                                 |

---

## 🏗️ Architecture & Connection Flow

### **Ansible Connections**

![Ansible Architecture](ansible_architecture.png)

---

## 🧩 Key Skills Demonstrated

- **Configuration Management:** Manage OS, users, packages, and services.
- **Infrastructure as Code (IaC):** Automate provisioning using Ansible & AWS modules.
- **Orchestration:** Multi-host automation using Playbooks & Roles.
- **Templating & Variables:** Dynamic and reusable configurations with Jinja2.
- **Error Handling:** Conditionals, loops, and notifications for efficient playbooks.
- **Version Control:** Git-based workflow for modular automation scripts.

---

### 🧩 Prerequisites

To replicate this setup, ensure the following AWS infrastructure:

| **Node**     | **Purpose**                    | **AMI**          | **Instance Type** | **Security Group Rules**     |
| ------------ | ------------------------------ | ---------------- | ----------------- | ---------------------------- |
| Control Node | Ansible Master                 | Ubuntu 22.04 LTS | t2.micro          | Port 22 open from My IP      |
| Web01        | Managed Node (Web Server)      | CentOS 9 Stream  | t2.micro          | Port 22 open from Control SG |
| Web02        | Managed Node (Web Server)      | CentOS 9 Stream  | t2.micro          | Port 22 open from Control SG |
| DB01         | Managed Node (Database Server) | CentOS 9 Stream  | t2.micro          | Port 22 open from Control SG |

**Additional Setup:**

- Create and attach **key pairs** (`control.pem`, `client-key.pem`).
- Configure SSH access between control and target nodes.
- Install Ansible only on the control node.
- Export AWS credentials (`AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`) if automating AWS resources via Ansible modules.

---

### 🚀 How to Run

```bash
# Run ad-hoc command
ansible all -m ping

# Run a playbook
ansible-playbook site.yml

# Run with custom inventory
ansible-playbook -i inventory/aws_hosts.yml webserver.yml
```

## 🧠 Key Learnings

- Difference between **Configuration Management** and **Orchestration**.
- **Idempotency** — how Ansible ensures consistency across executions.
- The importance of **modular design** using Roles & Variables.
- Using **Ansible as a bridge** between on-prem & cloud automation.

---
