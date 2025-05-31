# VMs-monitor-and-remote-access
Create virtaul machine, monitor and remote access


Sure! Here's a clean, professional, and informative `README.md` file for your **Azure Virtual Machine with Remote Access & Monitoring** project—perfect for GitHub and resume showcasing:

---

````markdown
# 🖥️ Azure Virtual Machine with Remote Access & Monitoring

This project demonstrates the deployment, configuration, and monitoring of a secure Virtual Machine (VM) on **Microsoft Azure** using **free-tier resources**. It includes remote access setup (SSH or RDP), network security rules, system monitoring, and alerting via **Azure Monitor** and **Log Analytics**.

---

## 📌 Project Objectives

- Provision a Linux or Windows VM on Azure
- Configure secure remote access (SSH or RDP)
- Set up Network Security Groups (NSG) for inbound rules
- Enable monitoring with Azure Monitor and Log Analytics
- Visualize resource usage (CPU, RAM, disk, etc.)
- (Optional) Configure alerts for performance thresholds

---

## 🛠️ Technologies Used

| Tool                | Purpose                              |
|---------------------|--------------------------------------|
| Azure Virtual Machines | Hosting compute resources         |
| NSG (Network Security Group) | Securing inbound/outbound traffic |
| Azure Monitor       | Real-time system metrics             |
| Log Analytics       | Log collection & custom dashboards   |
| SSH / RDP           | Remote VM access                     |
| Azure CLI / Azure Portal | Deployment and configuration    |

---

## 🚀 Deployment Steps

### 1. Create a Resource Group
```bash
az group create --name vm-monitoring-rg --location westeurope
````

### 2. Create the Virtual Machine (Linux example)

```bash
az vm create \
  --resource-group vm-monitoring-rg \
  --name my-monitoring-vm \
  --image UbuntuLTS \
  --admin-username azureuser \
  --generate-ssh-keys \
  --size Standard_B1s \
  --output json
```

>  For Windows VM: Choose `--image Win2019Datacenter` and enable RDP port (3389)

---

### 3. Open Required Ports

* For Linux (SSH):

```bash
az vm open-port --port 22 --resource-group vm-monitoring-rg --name my-monitoring-vm
```

* For Windows (RDP):

```bash
az vm open-port --port 3389 --resource-group vm-monitoring-rg --name my-monitoring-vm
```

---

### 4. Connect to the VM

* **SSH (Linux)**:

```bash
ssh azureuser@<PUBLIC-IP>
```

* **RDP (Windows)**: Use Remote Desktop to connect to `PUBLIC-IP:3389`.

---

### 5. Enable Monitoring

* Go to **Virtual Machine → Monitoring → Insights**
* Click **Enable** and attach or create a **Log Analytics Workspace**
* View metrics: CPU usage, memory, disk, network

---

### 6. (Optional) Create Alerts

* Go to **Azure Monitor → Alerts → New Alert Rule**
* Set condition: e.g., *CPU % > 80*
* Create Action Group: e.g., *send email*

---

## 📸 Screenshots

| Metric Dashboard             | Log Analytics Query           | VM Overview             |
| ---------------------------- | ----------------------------- | ----------------------- |
| ![](screenshots/metrics.png) | ![](screenshots/logquery.png) | ![](screenshots/vm.png) |

---

## 🧠 Learning Outcomes

* Gained practical experience in Azure IaaS
* Set up and secured remote access to a cloud VM
* Enabled telemetry with Azure Monitor & Logs
* Visualized and interpreted performance data

---

## 📄 Resume Bullet (Use this!)

> Deployed and monitored a secure virtual machine on Microsoft Azure using Linux OS, enabled Azure Monitor and Log Analytics for real-time system tracking, and configured SSH access and NSG firewall rules to ensure secure remote connectivity.

---

## 📂 Project Structure

```
azure-vm-monitoring/
├── azure-vm-setup.sh         # (Optional Azure CLI script)
├── README.md
├── screenshots/
│   ├── metrics.png
│   ├── logquery.png
│   └── vm.png
```

---

## 🆓 Cost Info

* VM Size: **B1s** (Free tier eligible)
* Azure Monitor: Free for basic metrics/logs (within limits)
* NSG and SSH/RDP access: No extra cost

---

## 🧑‍💻 Author

**Md Emdadul Gani**
Cloud & Database Engineer
[LinkedIn](#) | [GitHub](#) | [Email](#)

---

```

Would you like me to generate a GitHub repo structure with placeholder files and screenshots folder? I can also provide a Bash deployment script (`azure-vm-setup.sh`) if you want a one-click setup option.
```
