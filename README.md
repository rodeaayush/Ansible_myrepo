
# 🤖 What is Ansible?

**Ansible** is an open-source automation tool used for **configuration management**, **application deployment**, **task automation**, and **orchestration**. It helps DevOps teams automate repetitive tasks across multiple servers using **simple YAML-based scripts** called **Playbooks**.

It is agentless — meaning it doesn’t require any software to be installed on the target systems. It uses **SSH (Secure Shell)** to communicate with remote hosts.

---

## 🚀 Why Use Ansible?

- ✅ Simple, human-readable YAML syntax
- ✅ Agentless (no need to install anything on target nodes)
- ✅ Works well with cloud platforms (AWS, GCP, Azure)
- ✅ Supports configuration, provisioning, and orchestration
- ✅ Free and open source

---

## ⚙️ How Ansible Works

Ansible follows a **push-based** model where it runs commands from a **control node** (your local or management machine) and connects to **target nodes** (managed servers) via SSH.

### 🔄 Ansible Workflow



📖 Reference & Resources
Read this tutorial on [GeeksforGeeks](https://www.geeksforgeeks.org/devops/create-user-using-ansible-playbook/)


🧠 Ansible Cheat Sheet Image:
![image](https://media.geeksforgeeks.org/wp-content/uploads/20240417114541/Ansible-cheat-sheet.gif)


- **Inventory file**: List of servers (hosts)
- **Modules**: Built-in commands (e.g., user, yum, service)
- **Playbooks**: YAML files that define tasks and roles
- **Tasks**: Steps to run (install packages, copy files, etc.)

---

## 📂 Basic Components

| Component     | Description                                 |
|---------------|---------------------------------------------|
| `Inventory`   | List of servers to manage (`/etc/ansible/hosts`) |
| `Playbook`    | YAML file describing automation tasks       |
| `Module`      | A unit of work (e.g., install, copy, start) |
| `Task`        | A single action within a Playbook           |
| `Handler`     | Triggered tasks run on condition            |
| `Role`        | Structured collection of tasks and variables|

---

## 🧪 Example Playbook

```yaml
---
- name: Install Nginx Web Server
  hosts: webservers
  become: true
  tasks:
    - name: Install nginx
      apt:
        name: nginx
        state: present

    - name: Ensure nginx is running
      service:
        name: nginx
        state: started

