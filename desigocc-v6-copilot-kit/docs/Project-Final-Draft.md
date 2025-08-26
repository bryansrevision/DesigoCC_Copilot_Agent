# Siemens Desigo CC V6 Engineering Expert — Copilot Studio Agent

---

## 📖 Summary
This project delivers a **Microsoft Copilot Studio Agent** specialized for **Siemens Desigo CC V6.x**.  
The agent functions as a **virtual engineering & integration expert**, supporting:

- Document-based guidance with citations.  
- System configuration, troubleshooting, and performance optimization.  
- Live **API calls** via **WSI Swagger connector**.  
- **Typed, user-friendly actions** for common Desigo CC operations.  
- Safe scripting and code generation (PPCL, JavaScript, macros).  
- Integration with **Tomcat/BIRT reporting**.  
- Governance via **GitHub repo**, CI/CD pipelines, and automation tests.  

---

## 🎯 Purpose
The agent provides:  
- **Stepwise instructions** for installation, configuration, commissioning.  
- **Troubleshooting assistance** with layered diagnostics.  
- **Debugging support** for integrations, networking, and scripting.  
- **Code generation** for PPCL, macros, and automation scripts.  
- **Live system interaction** via Swagger-based WSI calls.  
- **Governed deployment** through GitHub pipelines with automated validation.  

---

## 🗂️ Repo Structure
```txt
desigocc-v6-copilot-kit/
├─ .github/
│  └─ workflows/
│     ├─ ci-cd.yml              # CI/CD pipeline
│     ├─ swagger-lint.yml       # Swagger validation
│     └─ secrets-scan.yml       # Secret scanning
├─ connectors/
│  ├─ wsi-openapi.yaml          # Swagger export from Desigo CC WSI
│  ├─ wsi-typed-actions.json    # Typed endpoints (10 key actions)
│  └─ tomcat-http-connector.json
├─ automation/
│  ├─ postman/
│  │  ├─ DesigoCC_WSI.postman_collection.json
│  │  └─ DesigoCC.postman_environment.json
│  ├─ newman-smoke-tests.json   # Core endpoint smoke tests
│  └─ run-newman.ps1            # Script to run Newman tests
├─ prompts/
│  ├─ prompt1-role-scope.md
│  ├─ prompt2-policy-styles.md
│  ├─ prompt3-troubleshooting.md
│  └─ prompt4-actions-safety.md
├─ docs/
│  ├─ Agent-Setup-Guide.md
│  ├─ Security-RBAC.md
│  └─ User-Workflows.md
│  └─ Project-Final-Draft.md
└─ samples/
   ├─ commissioning-checklist.pdf
   └─ alarm-rca-template.md
```

---

## 📚 References Library

### Core Platform (V6.0)
- System Description → A6V10415500  
- Engineering Manual → A6V10415473 (EU), A6V10376170 (US)  
- User Guide → A6V10415471  
- Graphics Tools Manual → A6V10415487  
- Web Client Certificate Install → A6V10415479  
- Installation Insert → A6V11637612_enUS_c  
- Online Help Hub → A6V14054665  

### Web Services / APIs / Tomcat
- WSI Guide → Entry ID 109765039  
- Energy Manager Integration via WSI → Siemens Energy Manager Guide  
- Advanced Reporting (BIRT/Tomcat) → Online Help  

### Extension Modules (V6.0)
- APOGEE BACnet V6.0 → BACnet EDE 5.1 [Help]  
- APOGEE P2 V6.0 → AEM integration, PPCL [Help]  
- APOGEE System V6.0 → Driver overview [Help]  
- Application Host Base V6.0 [Help]  
- BAS_EN / BAS_NA V6.0 → Libraries, naming rules [Help]  
- Modbus 5.1 / V6.0 [Help]  
- Engineering Console V6.0 [Help]  
- Graphics Tools V6.0 [Help]  
- Mobile App / Push Notif V6.0 [Help]  
- Multimedia V6.0 [Help]  
- Network Setup Wizard V6.0 [Help]  
- OPC DA Client/Server V6.0 [Help]  
- OPC UA Client V6.0 [Help]  
- Operator Tasks V6.0 [Help]  
- Scripts V6.0 [Help]  

### Standards & Programming
- PPCL → APOGEE field panel manuals (AEM, PXC, 125-xxxx)  
- Swagger/OpenAPI → via WSI (`/swagger/`)  
- Tomcat → Apache Tomcat 9.0 (default port 18080)  

---

## 💬 Final Prompts

### Prompt 1 — Role, Scope & References
Defines **expert role, system scope, and references index**.

### Prompt 2 — Policy, Styles & Interaction
Enforces **citations, safe instructions, structured styles (How-To, RCA, API, Scripting, Change/Risk)**.

### Prompt 3 — Troubleshooting & Best Practices
Provides **layered troubleshooting** framework with diagnostic tools and best practices.

### Prompt 4 — Actions, APIs, Scripting & Safety
Defines **typed Swagger actions, API safety rules, scripting policies, and rollback requirements**.

---

## ⚡ Typed Swagger Actions
**File:** `connectors/wsi-typed-actions.json`  

Includes 10 operations:  
- GetObjectValue  
- SetObjectValue  
- BrowseHierarchy  
- GetTrendData  
- SubscribeEvents  
- AcknowledgeAlarm  
- GetSystemInfo  
- SearchObjects  
- GetSchedules  
- RunCommand  

Each action is strongly typed, friendly-named, and mapped to WSI endpoints.

---

## 🛠️ CI/CD Pipelines

### 1. CI/CD Workflow (`.github/workflows/ci-cd.yml`)
Runs **Newman API smoke tests** on push/PR.  

### 2. Swagger Lint (`.github/workflows/swagger-lint.yml`)
Validates `wsi-openapi.yaml` using **Spectral**.  

### 3. Secrets Scan (`.github/workflows/secrets-scan.yml`)
Uses **GitGuardian** to detect leaked secrets.  

---

## 🧩 Automation Scripts

### Newman Smoke Test (`automation/run-newman.ps1`)
```powershell
param (
    [string]$Collection = "automation/postman/DesigoCC_WSI.postman_collection.json",
    [string]$Environment = "automation/postman/DesigoCC.postman_environment.json"
)

Write-Host "Running Newman API smoke tests..."
newman run $Collection -e $Environment -r cli,json --reporter-json-export results.json

if ($LASTEXITCODE -ne 0) {
    Write-Error "Newman tests failed. Check results.json."
    exit 1
}
```

---

## ✅ Acceptance Checklist
- [ ] Prompts 1–4 loaded into Copilot Studio.  
- [ ] Knowledge docs uploaded (Core, Modules, APIs).  
- [ ] WSI Swagger imported.  
- [ ] 10 typed actions validated.  
- [ ] Tomcat connector tested.  
- [ ] Auth secrets vaulted + RBAC mapped.  
- [ ] CI/CD pipelines passing.  
- [ ] Commissioning & troubleshooting workflows tested.  

---

# 🚀 Export-Ready Package
This file consolidates:  
- **Summary & Purpose**  
- **Repo Structure**  
- **References Index**  
- **Prompts (1–4)**  
- **Typed Swagger Actions**  
- **CI/CD Pipelines**  
- **Automation Scripts**  
- **Acceptance Checklist**  

> Place this file under `docs/Project-Final-Draft.md` in your GitHub repo for documentation and export.  
