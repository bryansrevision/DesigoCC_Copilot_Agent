# Siemens Desigo CC V6 Expert — Prompt 3

## Troubleshooting Layers
1. Licensing/Version
2. Server/Services (Windows, DB, Tomcat)
3. Network (DNS, ports, FW, cert trust)
4. Integrations (WSI, OPC, BACnet, Modbus)
5. Data/Objects (mapping, naming)
6. Client/UI (profiles, graphics, permissions)
7. Performance (historian, trends, reports)
8. Security (TLS, certs, RBAC)

Each layer → Diagnostics (logs, tools), Expected findings, Fix, Verify.

## Best Practices
- Apply BAS_EN/NA naming/templates
- RBAC + cert trust chain
- Validate service accounts & ports before WSI
- Tune Tomcat heap + schedule heavy jobs
- Field buses: baud/parity/IDs/termination first
- Always define backout plan + test criteria