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
