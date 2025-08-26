# Siemens Desigo CC V6 Expert — Commissioning Checklist

## Purpose
Use this checklist to validate commissioning of a Desigo CC V6.x deployment. Tick ✓ when verified.

---

## 1. Licensing & Version
- [ ] Correct edition installed (Management Station / Extensions licensed)
- [ ] Feature keys imported (OPC, Modbus, BACnet, P2, etc.)
- [ ] Version & hotfix level verified (System Info vs project requirement)

## 2. Server & Services
- [ ] Windows services running (Desigo CC Core, DB, Tomcat)
- [ ] Database connectivity (SQL Server) verified
- [ ] Backup/restore tested

## 3. Network & Security
- [ ] Hostname/DNS resolution correct
- [ ] Required ports open (WSI 8443, Tomcat 18080, OPC UA/DA)
- [ ] Certificates installed & trusted (CN/SAN match, chain complete)
- [ ] RBAC applied (least privilege, operator vs engineer roles)

## 4. Integrations
### WSI / Web Services
- [ ] Swagger UI reachable
- [ ] Auth working (Bearer/Basic)
- [ ] Object read/write tested with Postman (baseline → write → rollback)
- [ ] Trend export verified

### OPC UA Client
- [ ] UA server endpoint reachable
- [ ] Cert trust established
- [ ] Points mapped, values updating

### OPC DA Client/Server
- [ ] DA client reads 3rd‑party points
- [ ] DA server exposes required data

### BACnet / APOGEE / Modbus
- [ ] BACnet devices discovered/imported
- [ ] EDE import tested
- [ ] P2 panels connected, PPCL validated
- [ ] Modbus TCP/RTU devices mapped, values correct

## 5. Graphics & UI
- [ ] Graphics libraries imported (BAS_EN/NA)
- [ ] Custom graphics displayed correctly
- [ ] Symbols linked to live points

## 6. Operator Tasks & Mobile
- [ ] Operator tasks tested (alarms, overrides)
- [ ] Mobile app connects via WSI
- [ ] Push notifications delivered

## 7. Reporting / Tomcat
- [ ] Tomcat service running
- [ ] BIRT viewer opens
- [ ] Sample report runs (<5s load)
- [ ] Scheduled reports configured

## 8. Performance & Logs
- [ ] Historian/trends logging correctly
- [ ] System performance within limits
- [ ] Event/Alarm logs clear, searchable

## 9. Acceptance
- [ ] Commissioning signed off by Engineer
- [ ] Documentation handed over
- [ ] Backup of configuration stored securely

---

**Engineer Name:** ______________________  
**Date:** ______________  
**Signature:** ______________________
