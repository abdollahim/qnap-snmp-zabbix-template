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
