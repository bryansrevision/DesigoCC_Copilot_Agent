# Siemens Desigo CC V6 Expert Copilot — Agent Instructions

## Purpose
This document explains how to configure, deploy, and maintain the Siemens Desigo CC V6 Expert Copilot in Microsoft Copilot Studio.

## Steps to Build the Agent

### 1. Create Copilot
- Go to **Copilot Studio → Create Copilot**
- Name: `Desigo CC V6 Engineering Expert`
- Open **Settings → Instructions** and paste the prepared multi‑prompt agent builder text.

### 2. Upload Knowledge Sources
- Upload **DesigoCC_V6_Documentation_Index_FullLinks_Notes.pdf**
- Upload core A6V manuals: System Description, Engineering Manual, User Guide, Graphics, Web Client Certs, Install Insert, Online Help Hub
- Upload **WSI v6.0 PDF**, **Entry ID 109765039**, Swagger export (JSON/YAML)
- Upload module PDFs (APOGEE, Modbus, OPC, BAS_EN/NA, Scripts, etc.)
- Upload PPCL manuals (AEM/PXC) + BAS standards

### 3. Configure Actions
- **WSI_Swagger_Call**: Custom Connector from Desigo CC Swagger
- **Tomcat_Report_Job**: Connector to BIRT viewer/report endpoints
- **Knowledge_Passage_Search**: if available, to surface PDF passages

### 4. Secrets / Environment
- Store `baseUrl`, `reportBase`, `username`, `password`, `token`, `forceBasic`
- Use environment variables or connection secrets

### 5. Test the Copilot
- Ask: “Create an OPC UA client checklist”
- Ask: “WSI read AHU1.SAT with curl example”
- Ask: “RCA for web client certificate warning”

### 6. Publish & Monitor
- Publish to Teams or Web
- Enable transcripts/logs
- Refresh documentation quarterly or on hotfix releases

## Maintenance
- Keep repo updated with new manuals
- Update Postman collection if endpoints change
- Review user feedback and improve prompts
