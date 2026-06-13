# QNAP NAS LLD SNMP
Production‑ready SNMP Low‑Level Discovery (LLD) template for QNAP NAS storage devices.  
Designed for Zabbix 7.4+ with full compatibility validation for Zabbix 8.x.

**Version:** 0.0.1
**Author:** Majid Abdollahi

---

## 📌 Overview
This template provides complete, automated monitoring coverage for QNAP NAS systems using
native SNMP OIDs. It includes full hardware discovery, storage analytics, system health
monitoring, and performance metrics — all aligned with the Zabbix 7.4 YAML schema.

The template is optimized for production environments, large deployments, and NOC‑level
observability requirements.

---

## 🚀 Features

### 🔍 **Automatic Low‑Level Discovery**
- HDD discovery (capacity, temperature, state)
- RAID group discovery (status, capacity, free space)
- Storage pool discovery (capacity, free %, thresholds)
- Volume discovery (capacity, free %, thresholds)
- FAN discovery (speed, health)
- PSU discovery (status)
- UPS discovery (status)
- Temperature sensor discovery (per‑sensor alarms)
- System health module discovery

### 🖥️ **Static System Monitoring**
- CPU temperature
- CPU usage
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
- Fan/PSU/UPS failures
- System health abnormal
- CPU temperature high
- Memory low
- SNMP agent unavailable

### 📊 **Valuemap Support**
- RAID Status  
- PSU Status  
- UPS Status  
- Alarm State  
- Health Status  
- Firmware Version Available  

---

## 🧩 Template Architecture
- Fully LLD‑driven hardware and storage monitoring
- Clean separation of static system items vs. dynamic LLD items
- Optimized polling intervals for performance‑critical vs. slow‑changing metrics
- Consistent naming, tagging, and key structure for dashboards and filtering
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

The following roadmap outlines planned enhancements and future development goals for the
**QNAP NAS LLD SNMP** template. Features are grouped by milestone versions to provide a clear,
predictable evolution path toward a full enterprise‑grade monitoring suite.

---

### 🔹 v0.0.2 — Storage & Hardware Enhancements
- [ ] SMART attribute monitoring (if OIDs available)
- [ ] Disk IOPS & latency metrics
- [ ] Network interface LLD (IF‑MIB)
- [ ] Fan RPM threshold alerts (warning/critical)
- [ ] PSU redundancy state monitoring
- [ ] Temperature sensor grouping (CPU / System / HDD / Ambient)
- [ ] Improved tag normalization across all LLD prototypes

---

### 🔹 v0.1.0 — Performance & Capacity Analytics
- [ ] Pool & volume performance metrics (IOPS, throughput)
- [ ] RAID rebuild progress monitoring
- [ ] Disk wear‑level / lifespan indicators
- [ ] CPU load averages (1m / 5m / 15m)
- [ ] Memory buffer/cache breakdown
- [ ] Predictive capacity analytics (pool/volume full date)
- [ ] Predictive disk failure risk (SMART + temperature)
- [ ] Graph prototypes for temperature, capacity, and performance trends

---

### 🔹 v0.2.0 — QNAP Services & Apps Monitoring
- [ ] QNAP service status (SMB, NFS, AFP, FTP, SSH, WebDAV)
- [ ] QNAP app status (Container Station, HBS, etc.)
- [ ] Antivirus status monitoring
- [ ] Snapshot space usage
- [ ] Backup/replication job status (RTRR / Rsync)
- [ ] Alerts for service failures, backup job errors, and snapshot issues

---

### 🔹 v0.3.0 — Security & Health Monitoring
- [ ] Failed login attempt monitoring
- [ ] Admin password age
- [ ] Firmware integrity status
- [ ] Malware scan results (if exposed)
- [ ] System event log LLD (if possible)
- [ ] Alerts for suspicious activity, unexpected reboots, and firmware mismatch

---

### 🔹 v0.4.0 — Enterprise Features
- [ ] Dual‑controller QNAP support (ES1640dc, enterprise ZFS models)
- [ ] Multi‑NAS dashboard (global overview)
- [ ] SLA‑oriented KPIs (availability %, performance %, capacity %)
- [ ] Custom Zabbix dashboard widgets
- [ ] Prebuilt dashboards (JSON)
- [ ] Prebuilt screens and host groups

---

### 🔹 v1.0.0 — Full Enterprise Release
- [ ] Complete hardware + storage + service + security coverage
- [ ] Predictive analytics for capacity and failure
- [ ] Full dashboard suite
- [ ] Automated documentation generation
- [ ] Model‑specific optimizations (TS‑x53, TS‑x73, TVS‑x72, ZFS NAS, etc.)
- [ ] Community contributions integrated

## 📄 License
This template is released under the MIT License.

---

## 🤝 Contributing
Pull requests, improvements, and additional QNAP model support are welcome.

---

## 📚 Changelog
See [CHANGELOG.md](./CHANGELOG.md) for full version history.
