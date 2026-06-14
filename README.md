# QNAP NAS LLD SNMP
Production‑ready SNMP Low‑Level Discovery (LLD) template for QNAP NAS storage devices.  
Designed for Zabbix 7.4+ with full compatibility validation for Zabbix 8.x.

**Version:** 0.2.0  
**Author:** Majid Abdollahi

---

## 📌 Overview
Version **0.2.0** significantly expands the monitoring scope of the template, transforming it from a hardware‑focused baseline into a **full‑stack QNAP observability suite**.  
This release introduces enterprise‑grade hardware coverage, service monitoring, security visibility, and predictive analytics.

The template remains fully aligned with the Zabbix 7.4 YAML schema and is validated for Zabbix 8.x.

---

## 🚀 Features

### 🔍 **Automatic Low‑Level Discovery (LLD)**
- HDD discovery (capacity, temperature, state)
- RAID group discovery (status, rebuild visibility)
- Storage pool discovery (capacity, free %, IOPS, throughput, forecast)
- Volume discovery (capacity, free %, throughput)
- FAN discovery (speed, health)
- PSU discovery (status, redundancy)
- UPS discovery (status, health)
- Temperature sensor discovery (grouped by CPU/System/HDD)
- PCIe expansion card discovery
- System health module discovery

### 🖥️ **Static System Monitoring**
- CPU temperature (legacy + modern OIDs)
- CPU usage
- CPU load averages (1m / 5m / 15m)
- Memory usage (absolute & %)
- System uptime
- Hostname, serial number, firmware version
- Firmware update availability
- SNMP agent availability

### ⚠️ **Alerting & Thresholds**
- HDD temperature warning/critical
- Pool free space below threshold
- Volume free space below threshold
- RAID degraded or failed
- Fan/PSU/UPS/BBU failures
- Temperature sensor high alarm
- System health abnormal
- CPU temperature high
- Memory low
- Unexpected reboot
- Service failures (SMB, AFP, NFS, FTP, SSH)
- Antivirus disabled
- Malware detected
- Failed login burst detection
- SNMP agent unavailable

### 📊 **Valuemap Support**
- RAID Status  
- PSU Status  
- UPS Status  
- Alarm State  
- Health Status  
- Firmware Version Available  
- IF‑MIB Operational Status  

---

## 🧩 Template Architecture
- Fully LLD‑driven hardware, storage, service, and security monitoring
- Clean separation of static system items vs. dynamic LLD items
- Optimized polling intervals for performance‑critical vs. slow‑changing metrics
- Consistent naming, tagging, and key structure for dashboards and filtering
- Predictive analytics for capacity exhaustion (pools & volumes)
- YAML schema validated for Zabbix 7.4 and tested on Zabbix 8.x

---

## 🛠️ Requirements
- QNAP NAS with SNMP enabled (SNMP v2 recommended)
- Zabbix 7.4 or newer
- Network access to UDP/161

---

## 📦 Installation
1. Download the latest release from the **Releases** section.
2. Import the YAML file into Zabbix:
   - *Configuration → Templates → Import*
3. Assign the template to your QNAP NAS host.
4. Ensure SNMP credentials match your NAS configuration.
5. Wait for LLD cycles (5–15 minutes depending on component).

---

## 🧪 Tested On
- QNAP TS‑x53 series  
- QNAP TS‑x73 series  
- QNAP TS‑x83 series  
- QNAP Enterprise ZFS NAS  
- QTS 4.x / 5.x  
- QuTS hero  

---

## 🗺️ Roadmap

### 🔹 v0.3.0 — Security & Health Monitoring
- System event log LLD (if possible)
- Admin password age
- Firmware integrity deep checks
- Advanced intrusion detection
- Malware scan history
- Suspicious activity correlation

### 🔹 v0.4.0 — Enterprise Features
- Dual‑controller QNAP support (ES1640dc, enterprise ZFS)
- Multi‑NAS dashboard (global overview)
- SLA‑oriented KPIs (availability %, performance %, capacity %)
- Prebuilt dashboards (JSON)
- Custom widgets for QNAP metrics

### 🔹 v1.0.0 — Full Enterprise Release
- Complete hardware + storage + service + security coverage
- Predictive analytics for capacity and failure
- Full dashboard suite
- Automated documentation generation
- Model‑specific optimizations (TS‑x53, TS‑x73, TVS‑x72, ZFS NAS, etc.)
- Community contributions integrated

---

## 📄 License
This template is released under the MIT License.

---

## 🤝 Contributing
Pull requests, improvements, and additional QNAP model support are welcome.

---

## 📚 Changelog
See [CHANGELOG.md](./CHANGELOG.md) for full version history.
