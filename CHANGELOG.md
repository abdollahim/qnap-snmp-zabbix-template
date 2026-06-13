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

## Planned for Next Release
- SMART attribute monitoring (if SNMP OIDs available)
- Network interface LLD (if QNAP exposes IF‑MIB fully)
- Dashboard widgets for QNAP overview
- Performance graphs for pools/volumes
