# Desigo CC V6 Copilot Kit

This repository contains the full project package for deploying a **Siemens Desigo CC V6 Engineering Expert** agent in **Microsoft Copilot Studio**.

---

## 🚀 Quick Start

### 1. Clone Repo
```bash
git clone https://github.com/your-org/desigocc-v6-copilot-kit.git
cd desigocc-v6-copilot-kit
```

### 2. Upload Knowledge Base
Upload the following documents into **Copilot Studio** under *Knowledge*:
- Core A6V Manuals (System Description, Engineering, User Guide, Graphics, etc.)
- Module PDFs (BACnet, P2, OPC UA/DA, Modbus, etc.)
- WSI v6.0 Guide (Entry ID 109765039)
- Swagger export (wsi-openapi.yaml)
- Tomcat/Reporting Online Help

### 3. Import Prompts
Load prompts from `/prompts` into **Instructions**:
- Prompt 1: Role, Scope & References
- Prompt 2: Policy, Styles & Interaction
- Prompt 3: Troubleshooting & Best Practices
- Prompt 4: Actions, APIs, Scripting & Safety

### 4. Configure Connectors
- Import `connectors/wsi-openapi.yaml` into Copilot Studio.  
- Add `connectors/wsi-typed-actions.json` for user-friendly endpoints.  
- Configure Tomcat connector (`tomcat-http-connector.json`).  
- Store **baseUrl**, tokens, and credentials in **secrets vault**.

### 5. Run CI/CD Pipeline
- GitHub Actions workflows included:
  - `ci-cd.yml` → Newman API smoke tests
  - `swagger-lint.yml` → Validate Swagger
  - `secrets-scan.yml` → Secret scanning

Check pipeline status after each commit/PR.

### 6. Test Agent
- Example queries:
  - “Read AHU1.SAT via WSI; show curl.”
  - “Generate PPCL snippet for schedule override.”
  - “Run BIRT report for energy summary.”

### 7. Deploy
- Publish the agent to **Teams or Web**.  
- Ensure **RBAC and DLP policies** are enforced.

---

## 📂 Repo Layout
```txt
desigocc-v6-copilot-kit/
├─ .github/workflows/   # CI/CD pipelines
├─ connectors/          # Swagger + connectors
├─ automation/          # Postman collections, Newman tests, scripts
├─ prompts/             # Agent instruction prompts
├─ docs/                # Documentation + Project Final Draft
├─ samples/             # Commissioning checklist, RCA templates
└─ README.md            # This file
```

---

## ✅ Acceptance Checklist
- Prompts 1–4 loaded in Copilot Studio
- Knowledge docs uploaded
- Swagger imported + 10 typed actions validated
- Tomcat connector tested
- Secrets vaulted + RBAC mapped
- CI/CD pipelines passing
- Commissioning workflows validated

---

## 👨‍💻 Authors
Generated with AI-assisted development.  
Maintained by your **Desigo CC Copilot Engineering Team**.
