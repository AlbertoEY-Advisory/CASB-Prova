# CASB Policy Naming Standard

**Version:** 1.1
**Owner:** TBD
**Scope:** Cloud Access Security Broker (CASB) policies across Netskope, Microsoft, and additional platforms as required.

This document defines the naming convention to be used for all CASB policies created, updated, or deprecated.
The goal is to ensure **consistency**, **readability**, **automation-readiness**, and **traceability** across the organization.

---

## Purpose

This standard ensures **consistent, parsable, and automation-friendly naming** for CASB policies. It supports:

* **Traceability**: History of change
* **Clarity**: Explicit understanding of policy purpose
* **Governance**: Complete lifecycle management

---

## Naming Syntax

Below it is outlined the structure of naming convention established for CASB policies

---

## Core Structure (mandatory)

```
<CATEGORY>-<APP>-<ACTION>-<SCOPE><TAGS>-<TITLE>
```

Where:

* TAGS is optional and should be used only if required for policy clarity
* TITLE is mandatory and always in PascalCase

---

## 1. POLICY CATEGORY

Defines the primary purpose of the policy:

* **SEC** → Security (access control, threat protection)
* **GOV** → Governance / Compliance
* **MON** → Monitoring / Detection
* **NET** → Network (IP restrictions, routing, segmentation)
* **DLP** → Data Protection (DLP, PII, PCI, PHI, etc.)

---

## 2. APPLICATION or APP CATEGORY

Standardized short name (3 characters) of the targeted cloud service or app:

Common examples:

* **O365** → Microsoft 365
* **GWS** → Google Workspace
* **SLK** → Slack
* **BOX** → Box
* **ZOM** → Zoom
* **DRV** → Cloud Drives (OneDrive, GDrive, Box Drive…)
* **SOC** → Social Apps
* **GEN** → Generative AI
* **WBM** → Webmails
* **MLT** → Multi-application / Generic
* **TRT** → Translation tools

---

## 3. ACTION

Type of control or enforcement:

* **BLOCK** → Fully block
* **RESTRICT** → Block specific actions
* **ALLOW** → Permit actions
* **MONITOR** → Observe / audit
* **ALERT** → Trigger alerts
* **COACH** → User coaching

---

## 4. SCOPE

Identifies the population targeted by the policy:

* **ALL** → All users
* **HR** → Human Resources
* **FIN** → Finance
* **RND** → Research & Development
* **EXT** → External / Guest
* **GRP** → Specific group
* **VIP** → Executives
* **INT** → Internal users
* **SVC** → Service accounts

---

## 5. OPTIONAL TAGS

Tags are optional and are treated as other policy name fields

Example:

```ATT&CKT1234```

Available tags:

| Tag type | Description                                      | Possible options (with examples)                                                                                                      |
| -------- | ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| ATT&CK   | Maps the control to a MITRE ATT&CK technique     | T1059 (Command and Scripting Interpreter), T1566 (Phishing), T1027 (Obfuscated Files or Information)                                  |
| GEO      | Defines the geographical scope of applicability  | GLB (Global), EMEA (Europe, Middle East and Africa), NA (North America), APAC (Asia–Pacific)                                          |
| STAT     | Represents the operational status of the control | Draft (In draft phase), Test (Under testing), Enabled (Active in production), Disabled (Inactive), Deprecated (No longer recommended) |
| DATA     | Indicates the data classification level          | PUB (Public), INT (Internal), C2 (Confidential – medium), C3 (Confidential – high), C4 (Highly sensitive)                             |
| METHOD   | Defines how the control is implemented           | CLT (Client-side control), EB (Event-based), RP (Rule/Policy-based), API (API-based control)                                          |

**Tags are optional** and should only be added when they clearly add value.

---

## 6. TITLE

A short descriptive title of the policy, written in **PascalCase**, without spaces, underscores, or special characters.

Examples:

* `SensitiveDataUpload`
* `ExternalFileSharing`
* `FinanceAccessControl`
* `CoachUnsanctionedGenAI`

---

## Regex Validation Rule

To ensure compliance with the naming convention, the following regex must be used:

```regex
^(SEC|GOV|MON|NET|DLP)-[A-Z0-9]{3}-(BLOCK|RESTRICT|ALLOW|MONITOR|ALERT|COACH)-[A-Z]{2,4}(?:-[A-Z&]+)?-[A-Z][A-Za-z0-9]+$
```

---

## Versioning

Policy versioning is **tracked separately**, e.g. in:

* GitHub commit history
* Policy change logs
* CASB metadata

Version is **not part of the policy core name**.

---

## Contribution Guidelines

1. Fork the repository and create a feature or fix branch.
2. Add or update rules following this naming standard.
3. Validate names using the provided regex or linter script.
4. Submit a pull request with a descriptive explanation of the changes.

---

## Governance & Lifecycle

* **Ownership**: Each policy has a documented owner.
* **Versioning**: Track via commit logs.
* **MITRE Mapping**: Include ATT&CK IDs when applicable.
* **CI/CD**: Enforce naming with automated linters.
* **Knowledge Base**: Maintain examples, best practices, and rule definitions.

---

## Examples

Original                               Updated Naming                              

CASB-Block-LowReputationApps           --> GOV-MLT-BLOCK-ALL-LowReputationApps         
CASB-BlockUploadUnsanctionedApps       --> GOV-MLT-RESTRICT-ALL-UploadUnsanctionedApps 
CASB-Allow-FSES-SocialMediaRead        --> SEC-SOC-RESTRICT-FIN-SocialMediaReadOnly    
CASB-Allow-Any-M365-Netskope-Instances --> SEC-MLT-ALLOW-ALL-Instances                 
CASB-Block-GenAI-AllOthers             --> GOV-GEN-COACH-ALL-CoachUnsanctionedGenAI
