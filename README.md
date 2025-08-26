# DesigoCC_Copilot_Agent

A comprehensive Microsoft Copilot Studio agent for Siemens Desigo CC V6.x Building Automation Systems. This repository contains optimized prompts and Swagger action definitions for creating an expert-level BAS integration assistant.

## 🎯 Overview

This agent provides expert guidance for Siemens Desigo CC V6.x systems, including:
- System architecture, installation, and configuration
- Integration with APOGEE, BACnet, Modbus, OPC UA/DA
- PPCL & JavaScript/Macro scripting
- Web Service Interface (WSI) and Swagger API usage
- Tomcat reporting and performance optimization
- Troubleshooting and best practices

## 📁 Repository Structure

```
├── prompts/                          # Optimized Copilot Studio prompts
│   ├── prompt1-role-scope.md         # Agent role and scope definition
│   ├── prompt2-answering-policy-styles.md  # Response policies and styles
│   ├── prompt3-troubleshooting-best-practices.md  # Troubleshooting framework
│   └── prompt4-actions-swagger-safety.md  # Actions and safety guidelines
├── swagger-actions/                  # Typed Swagger action definitions
│   ├── get-object-value.json         # Retrieve object values
│   ├── set-object-value.json         # Set object values
│   ├── get-trend-data.json           # Historical trend data
│   ├── get-alarms.json               # Active alarm retrieval
│   ├── get-events.json               # System event logs
│   ├── get-schedules.json            # Schedule information
│   ├── create-object.json            # Create new objects
│   ├── update-object.json            # Update object properties
│   ├── delete-object.json            # Delete objects (with safeguards)
│   └── browse-objects.json           # Browse object hierarchy
└── README.md                         # This documentation
```

## 🚀 Quick Start

### 1. Import Prompts to Copilot Studio

Copy the content from each prompt file into your Copilot Studio agent configuration:

1. **System Prompt**: Use `prompt1-role-scope.md`
2. **Conversation Starters**: Use content from `prompt2-answering-policy-styles.md`
3. **Instructions**: Combine `prompt3-troubleshooting-best-practices.md` and `prompt4-actions-swagger-safety.md`

### 2. Configure Swagger Actions

Import the JSON action definitions from the `swagger-actions/` directory:

1. In Copilot Studio, go to **Actions** → **Add an action** → **Custom connector**
2. Import each JSON file as a separate action
3. Configure authentication (Bearer token or Basic Auth)
4. Test endpoints against your Desigo CC system

## 📊 Prompt Specifications

All prompts are optimized for Copilot Studio's ~2000 character limit:

| Prompt | Characters | Purpose |
|--------|------------|---------|
| Prompt 1 | 683 chars | Role definition and scope |
| Prompt 2 | 836 chars | Response policies and interaction styles |
| Prompt 3 | 707 chars | Troubleshooting methodology |
| Prompt 4 | 751 chars | Actions, Swagger usage, and safety |

## 🔧 Swagger Actions

### Core Object Operations
- **GetObjectValue**: Retrieve current values from BAS objects
- **SetObjectValue**: Set values with priority handling
- **BrowseObjects**: Navigate object hierarchy
- **CreateObject**: Create new system objects
- **UpdateObject**: Modify object properties
- **DeleteObject**: Remove objects (with safety checks)

### Data & Analytics
- **GetTrendData**: Historical trend data with time ranges
- **GetAlarms**: Active alarm monitoring and filtering
- **GetEvents**: System event log retrieval
- **GetSchedules**: Schedule management and status

## 🛡️ Security & Safety

The agent is designed with safety-first principles:

- **Authentication**: All actions require proper Bearer token authentication
- **Authorization**: RBAC-aware with permission checking
- **Non-destructive defaults**: Read operations preferred
- **Validation steps**: Built-in verification for critical operations
- **Error handling**: Comprehensive error mapping and guidance
- **Credential protection**: Never expose tokens or sensitive data

## 🔗 Integration Requirements

### Prerequisites
- Siemens Desigo CC V6.x system with WSI enabled
- Valid user credentials with appropriate RBAC permissions
- Network access to Desigo CC server (typically port 443 for HTTPS)
- SSL/TLS certificates properly configured

### Authentication
Configure one of these authentication methods:
- **Bearer Token**: Recommended for API access
- **Basic Authentication**: Username/password for legacy systems

## 📋 Usage Examples

### Check AHU Status
```
"What's the current status of AHU1 supply air temperature?"
```

### Troubleshoot Alarm
```
"I have a high priority alarm on Building.Floor2.VAV15. Can you help me troubleshoot?"
```

### Get Trend Data
```
"Show me the last 24 hours of trend data for all FCUs on Floor 3"
```

## 📚 Documentation References

The agent is trained to reference official Siemens documentation:
- **DesigoCC_V6_Documentation_Index_FullLinks_Notes.pdf**
- Core A6V manuals and module PDFs
- Web Service Interface v6.0.pdf
- WSI Swagger documentation

## 🤝 Contributing

When contributing to this repository:
1. Ensure prompts stay under 2000 characters
2. Test Swagger actions against actual Desigo CC systems
3. Follow safety-first principles for all operations
4. Include proper error handling and validation
5. Document all changes with citations

## 📄 License

This project is provided as-is for educational and professional use with Siemens Desigo CC systems. Please ensure compliance with your organization's policies and Siemens licensing terms.

---

**Note**: This agent provides guidance based on Siemens Desigo CC V6.x documentation and best practices. Always validate recommendations in your specific environment and follow your organization's change management procedures.