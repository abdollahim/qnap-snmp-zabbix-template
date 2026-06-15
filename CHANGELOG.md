# Changelog — QNAP NAS LLD SNMP

All notable changes to this project will be documented in this file.

---

## [0.0.1] — Initial Release
### Added
- Full SNMP‑based monitoring template for QNAP NAS devices
- CPU monitoring (temperature, usage)
- Memory monitoring (absolute & percentage)
- System identity (hostname, serial, firmware version)
- Firmware update availability detection
- SNMP agent availability monitoring

### Added — Low‑Level Discovery (LLD)
- HDD discovery (capacity, temperature, state)
- RAID group discovery (status, capacity, free space)
- Storage pool discovery (capacity, free %, thresholds)
- Volume discovery (capacity, free %, thresholds)
- FAN discovery (speed, health)
- PSU discovery (status)
- UPS discovery (status)
- Temperature sensor discovery
- System health module discovery

### Added — Alerting
- HDD temperature warning & critical triggers
- Pool free space threshold trigger
- Volume free space threshold trigger
- RAID degraded/failed trigger
- Fan/PSU/UPS failure triggers
- Temperature sensor high alarm trigger
- System health abnormal trigger
- CPU temperature high trigger
- Memory low trigger
- SNMP agent unavailable trigger

### Added — Valuemaps
- Firmware Version Available
- Alarm State
- RAID Status
- PSU Status
- UPS Status
- Health Status

---

## [0.0.2] — Storage & Hardware Enhancements

### Added
- IF‑MIB network interface LLD (RX/TX, speed, status)
- Fan RPM threshold alerting
- PSU redundancy state monitoring
- Temperature sensor grouping macros
- New valuemap: IF-MIB Operational Status

### Improved
- Normalized tags across LLD prototypes
- Improved temperature‑based triggers
- Optimized polling intervals for hardware metrics

### Notes
This version expands hardware visibility and prepares the template for performance analytics
in v0.1.0.

---

## [0.0.3] — System Services & Reliability Layer

### Added
- Monitoring for QNAP core services:
  - SMB
  - AFP
  - NFS
  - FTP
  - SSH
- Triggers for service failures
- System event log error counter
- Trigger for new system error events

### Improved
- Expanded service‑level visibility
- Foundation for QNAP app and backup job monitoring in v0.2.0

### Notes
This version focuses on operational reliability and service availability, extending the
template beyond hardware into QNAP’s internal service stack.

---

## [0.0.4] — Security & Health Monitoring Layer

### Added
- Failed login attempt counter
- Trigger for excessive failed logins
- Unexpected reboot detection
- Firmware integrity monitoring
- Malware scan result monitoring (if supported by model)
- Security‑focused triggers (intrusion, integrity, malware)

### Improved
- Strengthened system reliability and security visibility
- Foundation for advanced security analytics in v0.3.0

### Notes
This version expands the template into the security domain, enabling early detection of
intrusion attempts, firmware tampering, and malware activity.

---

## [0.0.5] — Enterprise Hardware Extensions

### Added
- NVMe cache health monitoring
- SSD cache wear‑level tracking
- BBU (battery‑backed write cache) status monitoring
- PCIe expansion card discovery and status
- Triggers for NVMe, SSD, BBU, and PCIe failures

### Improved
- Extended enterprise hardware visibility
- Prepared the template for performance analytics in v0.1.0

### Notes
This version targets enterprise and high‑end QNAP models, adding deeper hardware intelligence
and redundancy awareness.

---

## [0.1.0] — Performance & Capacity Analytics

### Added
- Pool IOPS (read/write)
- Pool throughput (read/write)
- RAID rebuild progress monitoring
- Predictive capacity analytics (pool & volume full date)
- CPU load averages (1m/5m/15m)
- Trend‑based triggers for capacity forecasting

### Improved
- Template now includes performance and analytics capabilities
- Foundation for advanced anomaly detection in v0.2.0

### Notes
This version transforms the template into a performance‑aware monitoring system capable of
forecasting capacity exhaustion and tracking real‑time storage performance.

---

## [0.2.0] — Full Hardware, Service & Analytics Integration

### Added — Major New Monitoring Modules
- UPS discovery (LLD) with per‑unit status and health mapping
- BBU (battery‑backed write cache) monitoring
- NVMe cache health monitoring
- SSD cache wear‑level tracking
- PCIe expansion card discovery and status
- Antivirus engine monitoring (enabled/disabled)
- Malware scan result monitoring
- Replication job status monitoring
- Snapshot usage monitoring
- Event log error counter
- Failed login attempt counter with intrusion detection trigger

### Added — LLD Enhancements
- Complete rebuild of Pool Discovery:
  - Capacity
  - Free space
  - Free %
  - Read/Write IOPS
  - Read/Write throughput
  - Days‑until‑full forecasting
- Improved Volume Discovery (capacity, free %, throughput)
- Improved Disk Discovery (capacity, temperature, state)
- Improved RAID Discovery (status, rebuild visibility)
- Improved FAN Discovery (speed, health)
- Improved PSU Discovery (status, redundancy)
- Improved Temperature Sensor Discovery with grouping macros
- Improved System Health module discovery

### Added — Service Layer Monitoring
- SMB service status
- AFP service status
- NFS service status
- FTP service status
- SSH service status
- Triggers for service outages

### Improved — Performance & Analytics
- CPU load averages (1m/5m/15m)
- Trend‑based capacity forecasting for pools and volumes
- Optimized polling intervals for performance‑critical metrics
- Normalized tags across all LLD prototypes
- Unified naming conventions for keys and items

### Improved — Security & Reliability
- Firmware integrity monitoring
- Unexpected reboot detection
- Enhanced intrusion detection (failed login bursts)
- Malware detection triggers
- Strengthened system health visibility

### Internal Improvements
- Complete UUIDv4 regeneration across:
  - All discovery rules
  - All item prototypes
  - All trigger prototypes
  - All static items
- Removed all legacy invalid UUIDs
- Removed all duplicate UUIDs
- Ensured full RFC‑4122 UUIDv4 compliance
- Ensured Zabbix 7.4 schema compatibility
- Validated import on Zabbix 8.x
- Cleaned valuemap references
- Normalized tag structure

### Notes
This release completes the transition from a basic hardware template to a full‑stack QNAP monitoring suite, covering hardware, storage, services, security, performance, and predictive analytics. Version 0.2.0 is the first production‑grade, fully comprehensive release.

---

## [0.3.0] — Security, Integrity & System Health Expansion

### Added — Security Monitoring Layer
- Failed login attempt LLD (per‑source aggregation where possible)
- Trigger for excessive failed login bursts (intrusion detection)
- Admin password age monitoring (if OID supported)
- Malware scan result monitoring (extended states)
- Antivirus engine status (enabled/disabled, last scan time)
- Firmware integrity deep‑check (extended OIDs)
- System event log LLD (experimental; model‑dependent)
- Alerts for suspicious activity:
  - Unexpected reboots
  - Firmware mismatch
  - Repeated authentication failures
  - Security module health degradation

### Added — System Health Enhancements
- System health module LLD improvements
- Temperature sensor grouping (CPU / System / HDD / Ambient)
- Health state correlation triggers (multi‑sensor abnormality detection)
- SNMP agent stability tracking (flapping detection)

### Improved — Reliability & Observability
- Normalized security‑related tags across all prototypes
- Improved trigger severity mapping for security events
- Enhanced firmware update detection logic
- Better separation of security vs. hardware alerts
- Optimized polling intervals for security‑sensitive metrics

### Internal Improvements
- UUIDv4 regeneration for all new LLD components
- Cleanup of legacy security OIDs
- Improved YAML schema alignment for Zabbix 7.4+
- Verified compatibility with Zabbix 8.x security modules

### Notes
This release elevates the template into a **security‑aware monitoring suite**, enabling early detection of intrusion attempts, firmware tampering, malware activity, and system instability.  
Version 0.3.0 lays the foundation for enterprise‑grade security analytics and prepares the template for the dashboard‑focused enhancements in v0.4.0.

---

## [0.4.0] — Enterprise Features, SLA Metrics & Dashboard Layer

### Added — Enterprise Hardware Support
- Dual‑controller QNAP support (ES1640dc, enterprise ZFS models)
- Redundant controller health monitoring (A/B)
- Controller failover detection and alerting
- PCIe expansion card extended metrics (bandwidth, link state)
- Enhanced PSU redundancy logic for multi‑PSU chassis

### Added — SLA & Availability Metrics
- Host‑level SLA calculation items:
  - Availability %
  - Performance %
  - Capacity %
- SLA‑oriented triggers for:
  - Monthly uptime violations
  - Performance degradation
  - Capacity SLA breach (pool/volume)
- New valuemap: **SLA State**

### Added — Dashboard & Visualization Layer
- Prebuilt Zabbix dashboards (JSON) for:
  - Hardware overview
  - Storage overview
  - Security overview
  - Performance analytics
  - Multi‑NAS fleet monitoring
- Custom widget definitions for:
  - Temperature groups
  - RAID/Pool/Volume health
  - UPS/PSU/BBU status
  - Security events timeline

### Added — Multi‑NAS Aggregation
- Global discovery for:
  - Total NAS count
  - Total storage capacity across all NAS units
  - Total free space across all NAS units
  - Global RAID health summary
- Multi‑NAS fleet‑level triggers:
  - “Multiple NAS units reporting degraded RAID”
  - “Fleet‑wide capacity threshold exceeded”
  - “Multiple NAS units reporting security incidents”

### Improved — Performance & Analytics
- Enhanced pool/volume forecasting accuracy
- Added trend‑based anomaly detection for:
  - Temperature
  - IOPS
  - Throughput
  - CPU load
- Improved RAID rebuild progress visibility
- Optimized polling intervals for enterprise chassis

### Improved — Security & Event Intelligence
- Event log correlation engine (experimental)
- Security incident grouping (failed logins + reboot + integrity)
- Improved firmware integrity logic for dual‑controller systems

### Internal Improvements
- UUIDv4 regeneration for all new items, triggers, and dashboards
- Cleanup of deprecated OIDs for older QTS versions
- Improved tag normalization for SLA and dashboard widgets
- Verified compatibility with Zabbix 7.4 and 8.x dashboard engine

### Notes
This release elevates the template into a **full enterprise‑grade monitoring suite**, adding
SLA metrics, dashboards, multi‑NAS aggregation, and dual‑controller support.  
Version 0.4.0 prepares the foundation for the final v1.0.0 release, which will focus on
predictive analytics, automated documentation, and model‑specific optimizations.

---

## [0.6.0] — Predictive Analytics, NVMe Endurance, RAID ETA, Thermal Drift
**Release date:** 2026‑06‑14  
**Author:** Majid Abdollahi

### Added
- **Predictive Disk Failure Score** (per‑disk DEPENDENT item)
  - Combines temperature, wear‑leveling count, and remaining‑life percentage
  - New trigger prototypes for *high risk* and *degraded predictive health*
- **Disk Wear‑Leveling Count** and **Remaining Life (%)** item prototypes
- **NVMe Endurance Monitoring**
  - TBW (Total Bytes Written)
  - Remaining endurance percentage
  - Critical endurance trigger (<10%)
- **RAID Rebuild ETA Calculation**
  - New item prototype for rebuild progress
  - DEPENDENT item for ETA (minutes)
  - Trigger for rebuild ETA exceeding 24 hours
- **Temperature Trend (1h)** per sensor
  - DEPENDENT item using Trend.avg()
  - Trigger for thermal drift >10°C in 1 hour

### Improved
- Unified disk discovery macros (`{#HDDINDEX}`, `{#HDDSLOT}`) across all disk‑related items
- Updated all dependent items to correctly reference master items inside the same LLD rule
- Enhanced temperature sensor grouping with consistent tagging (`temp_group`)
- Improved NVMe/SSD cache monitoring tags for dashboard filtering
- Cleaned up inconsistent item naming for HDD/NVMe/SSD components

### Fixed
- Resolved `master_itemid not found` errors caused by mismatched LLD macros
- Corrected SNMP OIDs for wear‑leveling and remaining‑life metrics
- Removed invalid CALCULATED SLA item using unsupported wildcard aggregation
- Fixed trigger expressions referencing incorrect macros (`{#DISKINDEX}` → `{#HDDINDEX}`)
- Eliminated leftover trendavg() CALCULATED items from earlier versions

### Removed
- Deprecated CALCULATED SLA predictive score (replaced with trigger‑based SLA logic)
- Removed unused disk state mappings from legacy QNAP OID branches

---

## Summary
Version **0.6.0** introduces the first generation of **predictive analytics** for QNAP NAS monitoring, including disk health scoring, NVMe endurance tracking, RAID rebuild forecasting, and temperature drift detection. This release significantly enhances reliability, early‑warning capabilities, and long‑term storage health visibility across all QNAP NAS models.

---

## [0.7.0] — SMART LLD, RAID Consistency, Pool Fragmentation, I/O Latency
**Release date:** 2026‑06‑15  
**Author:** Majid Abdollahi

### Added
- **SMART Attribute Discovery (new LLD rule)**
  - Automatic discovery of SMART attributes per disk
  - New item prototypes for SMART attribute values
  - Trigger prototype for critical SMART attributes
- **RAID Consistency Check Monitoring**
  - New item prototype for RAID scrub/consistency status
  - Trigger for failed or incomplete consistency checks
- **Pool Fragmentation Monitoring**
  - New item prototype for pool fragmentation percentage
  - Trigger for high fragmentation (>40%)
- **Volume I/O Latency & Queue Depth**
  - Read latency (ms)
  - Write latency (ms)
  - Trigger for high write latency (>20 ms)
- **Disk Error‑Rate Analytics**
  - New dependent item combining reallocated, pending, and uncorrectable sectors
  - Trigger for high disk error score
- **NVMe SMART Expansion**
  - NVMe temperature monitoring
  - Trigger for high NVMe temperature (>70°C)

### Improved
- Unified macro usage across all disk‑related items (`{#HDDINDEX}`, `{#HDDSLOT}`)
- Enhanced disk health analytics with SMART‑based error scoring
- Improved RAID monitoring with consistency/scrub visibility
- Expanded NVMe monitoring to include SMART‑level temperature
- Added latency‑focused metrics for volume performance diagnostics
- Strengthened pool monitoring with fragmentation metrics

### Fixed
- Corrected SNMP OIDs for SMART and RAID scrub attributes
- Resolved missing master_item references in dependent items
- Fixed inconsistent macro usage in disk‑related triggers
- Eliminated legacy SMART OID references from older QNAP branches
- Corrected volume latency item keys for compatibility with Zabbix 7.4+

### Removed
- Deprecated legacy SMART items from pre‑55062 OID branches
- Removed unused RAID scrub counters from older firmware versions

---

## Summary
Version **0.7.0** introduces full SMART attribute discovery, RAID consistency monitoring, pool fragmentation analytics, and volume latency metrics. This release significantly enhances predictive diagnostics, performance visibility, and long‑term storage reliability across all QNAP NAS platforms.
