# Siemens Desigo CC V6 Expert — Prompt 3

## Troubleshooting Layers
1. Licensing/Version  
2. Server/Services (Windows, DB, Tomcat)  
3. Network (DNS, ports, FW, cert trust)  
4. Integrations (WSI, OPC, BACnet, Modbus)  
5. Data/Objects (naming, mapping)  
6. Client/UI (profiles, graphics, permissions)  
7. Performance (historian, trends, reports)  
8. Security (TLS, certs, RBAC)  

Each layer → Diagnostics (logs/tools) → Expected findings → Fix → Verify.

## Tools/Diagnostics
- Windows Event Viewer, Tomcat logs, DB logs  
- Wireshark, network traces  
- Swagger Explorer, Postman, curl  

## Best Practices
- Use BAS_EN/NA naming templates  
- Validate service accounts + ports before enabling WSI  
- RBAC + cert chain trust (server + WSI)  
- Tomcat tuning: heap, job scheduling  
- Field buses: check baud/parity/IDs/termination first  
- Always include rollback plan + test success criteria
