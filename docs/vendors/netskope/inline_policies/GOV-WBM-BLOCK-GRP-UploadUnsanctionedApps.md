# CASB Policy Documentation

## Policy Name

GOV-WBM-BLOCK-GRP-UploadUnsanctionedApps

---

## Description

- **Purpose**: Coaching policy for upload on unsanctioned Webmail Apps blocking rules
- **Context**: Temporary policy, coach the users on what will happen soon
- **Behavior**: Coach
- **Version**: 1.0
- **Owner**: CISO/DCP Team
- **Source**: Stellantis CISO policy

---

## Naming Breakdown

- **Category**: GOV
- **Application**: WBM
- **Action**: COACHBLOCK
- **Scope**: GRP
- **Tags**: 
- **Title**: UploadUnsanctionedApps

---

## Enforcement Logic

- **Trigger**: Upload on unsanctioned Webmail Networking App
- **Condition**: The user is part of a group for wich the access will be blocked soon
- **Exceptions**: managed trough a dedicated policy, see -related policies-
- **Primary Action**: Coach
- **Secondary Action**: Block or Allow
- **Logging**: Classic logging by Netskope

---

## Audit & Monitoring

- **Logs**: Default alert logs.
- **Reports**: TODO
- **Review**: CISO/DCP

---

## Related Policies

* GOV-WBM-ALLOW-GRP-UploadUnsanctionedApps
* GOV-WBM-COACHBLOCK-GRP-UploadUnsanctionedApps
* GOV-WBM-BLOCK-ALL-UploadUnsanctionedApps

## Use Cases / Links

* UC-CASB-03-BlockLUploadByCateg

## Last JSON export

```json
{
  "ruleName": "GOV-WBM-COACHBLOCK-GRP-UploadUnsanctionedApps",
  "user": "O365-DYN-Users-ICT User Exclusions: ZSSI.InternetAccessUnrestricted, ZSSJ.CASBDLPFullException, ZSSJ.CASBBankTests",
  "sourceIP": "Any",
  "srcCountry": "Any",
  "browser": "Any",
  "accessMethod": "Any",
  "deviceClassification": "Any",
  "application": "Webmail",
  "activity": "Upload",
  "ccl": "Any",
  "dstCountry": "Any",
  "profile": "None",
  "action": "User Alert: Stellantis - BlockUploadUnsanctionedUserCoach",
  "alerts": "46",
  "lastEdit": "Edited Apr 01 2026 1:49 PM by stephane.lalmanach@stellantis.com",
  "status": "Enabled ",
  "sourceIPEgress": "Any",
  "uci": "None",
  "app_tags": "Unsanctioned",
  "groupOrder": "12",
  "groupName": "CASB - Stellantis",
  "osFamily": "Any"
}

```

## Notes

* 1/3 related_policies 1 to Allow specific people to access few Apps 1 to Coach the App will be blocked (temporary policy) (this one) 1 to Block
The target group will change over time, following perimeter of the application of the policy, from one group to another.
Following groups are excluded from the coaching policy - ZSSJ.CASBBankTests because this group has already a Social policy - ZSSI.InternetAccessUnrestricted because this groupe has unrestricted access...
- ZSSJ.CASBDLPFullException

## History

* 01/04/2026, psasm CHGT25721570, digitalme SCTASK0043550 - Coaching ICT
* 13/03/2026, CHGT25667214,CHGT25667247, big update to share exceptions betwin access to the app and just upload