# Azure Honeypot SIEM Setup with Microsoft Sentinel
 This project demonstrates the setup of a basic honeypot in Microsoft Azure, combined with centralized log forwarding, event enrichment, and visualization using Microsoft Sentinel.  


## 🔧 Part 1: Azure Subscription Setup

- [Create a free Azure subscription](https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account)

Log in to the Azure Portal:  
👉 https://portal.azure.com

---

## 🐝 Part 2: Create the Honeypot (Azure VM)

1. Go to **Virtual Machines** in the Azure Portal.
2. Create a **Windows 10 VM**
   - Select a small size (e.g., B1s) to save cost.
   - Remember the VM’s username and password.
3. Go to **Networking** > **Network Security Group (NSG)** for the VM:
   - Create an **Inbound Rule** to **allow all traffic**.
4. Inside the VM:
   - Open `wf.msc`
   - Turn off **Windows Firewall** (Domain, Private, Public profiles).

> ⚠️ This creates a purposely vulnerable machine to simulate attacker behavior.

---

## 🔐 Part 3: Simulate Failed Logins & Log Collection

1. On your honeypot VM:
   - Attempt **3 failed logins** using a fake user (e.g., `employee`)
2. Log in successfully.
3. Open **Event Viewer**:
   - Go to `Windows Logs > Security`
   - Look for **Event ID 4625** (Failed login attempt)

---

## 📈 Part 4: Enable Log Forwarding & KQL Queries

### Create Log Analytics Workspace (LAW)
- Used to collect logs across Azure resources.

### Create Microsoft Sentinel Instance
- Connect it to your LAW.

### Configure Log Ingestion
- Use the **"Windows Security Events via AMA"** connector.
- Create a **Data Collection Rule (DCR)**.

## 🧠 Skills Practiced

 - Azure VM Deployment
 - NSG & Firewall Configuration
 - Windows Event Log Analysis
 - Log Analytics & KQL (Kusto Query Language)
 - Sentinel Setup & Integration
 - Log Enrichment with Watchlists
 - Visual Dashboards using Workbooks


## Steps & Screenshots

### 1. Creating Azure Account
<img width="1700" height="898" alt="image" src="https://github.com/user-attachments/assets/a1760b8b-321e-4c85-9855-ac2118f6c810" />

### 2. Creating Resource group
<img width="1700" height="898" alt="image" src="https://github.com/user-attachments/assets/bb379263-58ae-46e3-8d21-da32afd3ef72" />

### 3. Creating Virtual Network
<img width="1700" height="898" alt="image" src="https://github.com/user-attachments/assets/1bd77398-7fbb-4752-a000-4eb377fe4775" />

### 4. Creating VM
<img width="1700" height="898" alt="image" src="https://github.com/user-attachments/assets/a98755d9-0520-4e78-8720-28c412aa59aa" />

### 5. Creating VM
<img width="1700" height="898" alt="image" src="https://github.com/user-attachments/assets/bfb44d88-806f-4d53-95c1-6b80fdeba059" />

### 6. RDP & Firewall
<img width="1700" height="898" alt="image" src="https://github.com/user-attachments/assets/7ea26ec6-fd86-491b-b6b1-432fcf40bbb4" />
<img width="1909" height="865" alt="image" src="https://github.com/user-attachments/assets/cf1297e1-32a8-48fa-848b-e005c6d4e489" />
<img width="1033" height="705" alt="image" src="https://github.com/user-attachments/assets/f490b461-a789-4532-abf2-22e166cd7224" />

### 7. Failed Logins
<img width="1914" height="915" alt="image" src="https://github.com/user-attachments/assets/a6795a15-acf9-4525-bd8f-e00457a35784" />

### 8. Creating Log Analytics Workspace
<img width="950" height="807" alt="image" src="https://github.com/user-attachments/assets/6b8d2b2b-5e1a-4294-9d84-93fbe7c5f30d" />

### 9. SIEM
<img width="1908" height="886" alt="image" src="https://github.com/user-attachments/assets/2e078ad7-e8d4-4bcd-adb2-8f5df7b63378" />

### 10. Login Attempts
<img width="1908" height="886" alt="image" src="https://github.com/user-attachments/assets/cb103478-469a-4ac4-abda-50b8fcad089c" />

### 11. Log Details + IP Location
<img width="1884" height="850" alt="image" src="https://github.com/user-attachments/assets/0cc43744-3cf2-4b36-9811-6e7a51c48909" />

### 12. VM Attack MAP
<img width="1874" height="853" alt="image" src="https://github.com/user-attachments/assets/f2342447-da9c-4e9c-a06c-473dba092a80" />

### 13. LAB DIAGRAM
<img width="1408" height="736" alt="image" src="https://github.com/user-attachments/assets/4d088c55-1782-4c87-ab40-edafd74debd2" />











