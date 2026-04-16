# 🔐 SIEM Lab using ELK Stack (Multi-VM Architecture)

## 📌 Overview
This project demonstrates the design and implementation of a Security Information and Event Management (SIEM) system using the ELK Stack (Elasticsearch, Kibana) with Filebeat for log collection.  

The setup is built in a multi-VM environment with proper network segmentation (Public DMZ, Private DMZ, Internal Subnet) to simulate a real-world enterprise security architecture.

---

## 🧠 Objective
- To understand how SIEM systems work in real environments  
- To build a centralized logging and monitoring pipeline  
- To simulate secure communication between isolated network segments  
- To visualize and analyze logs for security monitoring  

---

## 🏗️ Architecture

          Internet (NAT)
               │
        ┌──────────────┐
        │  Gateway VM  │
        │ (Routing/NAT)│
        └──────┬───────┘
               │ (Private DMZ - 192.168.10.0/24)
     ┌─────────┴─────────┐
     │                   │
┌────────────┐     ┌──────────────┐
│ Kali VM    │     │ ELK Server   │
│ (Filebeat) │ --> │ Elasticsearch│
│            │     │ + Kibana     │
└────────────┘     └──────────────┘

---

## 🌐 Network Design
- Public DMZ (NAT Network): Provides internet access for updates and package installation  
- Private DMZ (Internal Network): Secure communication between VMs  
- Internal Subnet: Static IP allocation (192.168.10.x) for reliable connectivity  

---

## ⚙️ Components

### Gateway VM
- Dual network interfaces (NAT + Internal)
- Performs IP forwarding and NAT
- Acts as a bridge between internal network and internet

### ELK Server VM
- Hosts Elasticsearch (log storage & indexing)
- Hosts Kibana (visualization & dashboards)
- Central analysis point of the SIEM system

### Kali Linux (Filebeat VM)
- Runs Filebeat to collect system logs
- Sends logs securely to Elasticsearch
- Simulates an endpoint being monitored

---

## 🔄 Data Flow
Kali (Logs) → Filebeat → Elasticsearch → Kibana Dashboard

---

## 📊 Features
- Centralized log collection and storage  
- Real-time log ingestion and visualization  
- Multi-VM segmented network architecture  
- Secure communication via private subnet  
- Kibana dashboards for monitoring system activity  

---

## 🛠️ Technologies Used
- SIEM Tools: ELK Stack (Elasticsearch, Kibana), Filebeat  
- OS: Kali Linux, Ubuntu  
- Virtualization: VirtualBox  
- Networking: NAT, Internal Network, Subnetting  
- Concepts: SIEM, Log Management, Network Segmentation, DMZ  

---

## 🧪 Testing & Validation
- Verified connectivity between all VMs using ping  
- Tested Elasticsearch connection via curl  
- Validated Filebeat → Elasticsearch pipeline  
- Confirmed logs appearing in Kibana dashboards  

---

## 📚 Key Learnings
- Understood how SIEM systems collect, process, and visualize logs  
- Gained hands-on experience with network segmentation (DMZ architecture)  
- Learned to troubleshoot networking, routing, and log ingestion issues  
- Built a practical understanding of SOC monitoring workflows  

---

## 🚀 Future Improvements
- Add Logstash for advanced log processing  
- Implement alerting (email/SMS/Telegram)  
- Integrate threat detection rules  
- Deploy on cloud infrastructure (AWS/Azure)  

---

## 👨‍💻 Author
Chitransh Mathur  
Cybersecurity Enthusiast | SIEM | VAPT | Malware Analysis  

---

## ⭐ Note
This project is built for learning and simulation purposes to understand real-world SIEM architecture and workflows.
