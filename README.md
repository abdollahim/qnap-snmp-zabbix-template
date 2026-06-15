# QNAP NAS SNMP LLD Template  
### Version 1.0.0 — Stable Release  
Author: **Majid Abdollahi**

This repository contains the **production‑ready SNMP Low‑Level Discovery (LLD) template** for
monitoring QNAP NAS devices using Zabbix. Version **1.0.0** represents the first **stable**
release of the SNMP‑based template, incorporating all features developed across versions
0.1.0 through 0.9.0.

> **Important:**  
> Modern QNAP models running **QTS 5.x / QuTS hero** (including TS‑873AeU‑RP) expose only
> basic system metrics via SNMP. Storage‑level OIDs (disks, RAID, pools, volumes, SMART,
> NVMe, fans, PSU) are no longer available through SNMP.  
>  
> This template remains fully functional for **legacy QNAP models** that still support the
> full QNAP private MIB.

---

## 📦 Features

### ✔ Core Monitoring
- CPU utilization  
- Memory usage  
- System uptime  
- Firmware version  
- SNMP agent availability  
- System identity and model information  

### ✔ Storage & Hardware (Legacy QNAP Models Only)
- Automatic discovery of:
  - HDDs  
  - RAID groups  
  - Storage pools  
  - Volumes  
  - Fans  
  - Temperature sensors  
  - PSUs  
  - UPS units  
  - PCIe devices  
  - BBU modules  
  - NVMe devices  
  - SMART attributes  

- Metrics include:
  - Capacity, free space, utilization  
  - IOPS and throughput  
  - Disk temperature, wear‑leveling, remaining life  
  - RAID rebuild progress and ETA  
  - Pool fragmentation  
  - Volume latency and queue depth  

### ✔ Predictive Analytics (Legacy Models)
- SMART anomaly detection  
- SMART volatility index  
- Disk lifetime forecasting  
- Disk degradation velocity  
- Disk failure‑probability scoring  
- Thermal stress index  
- Thermal fatigue index  
- RAID rebuild curve‑fit ETA  
- Volume performance anomaly detection  
- Volume stability index  

### ✔ Security & System Health
- Failed login bursts  
- Intrusion detection  
- Unexpected reboot detection  
- Antivirus status and last scan  
- Service‑level monitoring (SMB, AFP, NFS, FTP, SSH)  

---

## 🧩 Template Architecture

- Fully SNMP‑based  
- LLD‑driven discovery for all storage and hardware components (where supported)  
- Clean separation of static and dynamic items  
- Optimized polling intervals  
- Extensive use of valuemaps  
- Predictive analytics built on dependent items and trend functions  
- SLA‑oriented metrics for availability, performance, and capacity  

---

## ⚠️ SNMP Support Notes

### Modern QNAP Models (QTS 5.x / QuTS hero)
- Only basic system metrics are available via SNMP  
- Storage‑level OIDs are removed by QNAP  
- LLD rules for disks, RAID, pools, volumes, SMART, NVMe, fans, PSU will return **no data**  
- This is expected behavior and not a template issue  

### Legacy QNAP Models
- Full SNMP storage telemetry is available  
- All LLD rules and predictive analytics work as designed  

---

## 📘 Compatibility

- Fully compatible with **Zabbix 7.4**  
- Validated for import and runtime behavior on **Zabbix 8.x**  
- Works with:
  - QTS 4.x (full SNMP support)  
  - QTS 5.x (limited SNMP support)  
  - QuTS hero (limited SNMP support)  

---

## 🏁 Version 1.0.0 Status

This release finalizes the **SNMP branch** of the QNAP monitoring template.

All future development (Version 2.x and beyond) will focus on **REST‑API‑based monitoring**,
which provides full storage and hardware visibility on modern QNAP systems.

---

## 📄 License
MIT License

---

## 🙌 Author
**Majid Abdollahi**  
Storage Monitoring & Predictive Analytics Architect
