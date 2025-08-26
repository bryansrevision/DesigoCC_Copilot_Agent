# Siemens Desigo CC V6 Expert Copilot — Testing Playbook

## Purpose
Ensure that the Copilot and Postman toolkits are functioning correctly before rollout.

## Test Areas

### 1. Knowledge / Citations
- Ask for a system description (expect citation A6V10415500)
- Ask for OPC UA client steps (expect A6V10415473 reference)
- Ask for PPCL example (expect PPCL manual citation)

### 2. WSI API (Postman)
- **Health Check:** Run `WSI: Service Info` and `Swagger UI`
- **Read Value:** Read `AHU1.SAT` (expect value and <2s response)
- **Write + Rollback:** Safe Write Flow — confirm baseline saved, new value written, verified, and restored
- **Events:** Fetch events and acknowledge one

### 3. Tomcat Reporting
- Open `Tomcat: BIRT Viewer`
- Run `Tomcat: Run Report (GET)` with sample param
- Validate report load time < 5s

### 4. Security
- Test login with Basic vs Bearer (ensure fallback works)
- Verify cert trust in browser for Web Client

### 5. Copilot QA
- Ask a How‑To, an RCA, a Checklist, and an API example
- Confirm citations are included
- Confirm outputs are stepwise and professional

## Logs / Evidence
- Save Postman run results as JSON
- Save Copilot transcripts as PDF
- Archive in `logs/` folder of GitHub repo
