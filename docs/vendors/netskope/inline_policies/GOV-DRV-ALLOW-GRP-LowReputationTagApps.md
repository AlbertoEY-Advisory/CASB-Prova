# CASB Policy Documentation

## Policy Name

GOV-DRV-ALLOW-GRP-LowReputationTagApps

---

## Description

- **Purpose**: Allow policy for low reputation Cloud-Storage Apps blocking rules
- **Context**: Have an exception process for the low reputation Cloud-Storage Apps blocking rules
- **Behavior**: Allow
- **Version**: 1.0
- **Owner**: CISO/DCP Team
- **Source**: Stellantis CISO policy

---

## Naming Breakdown

- **Category**: GOV
- **Application**: DRV
- **Action**: ALLOW
- **Scope**: group
- **Tags**: 
- **Title**: LowReputationTagApps

---

## Enforcement Logic

- **Trigger**: Access to an App that have the -DerogLowReputation- netskope tag
- **Condition**: The user has the access service ZSSJ.CASBBlockLowRepEx with the ExceptionLowCloudStorage valorisation
- **Exceptions**: 
- **Primary Action**: ALLOW
- **Secondary Action**: 
- **Logging**: Classic logging by Netskope

---

## Audit & Monitoring

- **Logs**: Default alert logs.
- **Reports**: TODO
- **Review**: CISO/DCP

---

## Related Policies

* GOV-DRV-ALLOW-GRP-LowReputationTagApps
* GOV-DRV-COACHBLOCK-ALL-LowReputationApps
* GOV-DRV-BLOCK-ALL-LowReputationApps

## Use Cases / Links

* UC-CASB-02-BlockLowRepByCateg

## Last JSON export

```json
{
    "ruleName": "GOV-DRV-ALLOW-GRP-LowReputationTagApps",
    "user": "ZSSJ.CASB.ExceptionLowCloudStorage ",
    "sourceIP": "Any",
    "srcCountry": "Any",
    "browser": "Any",
    "accessMethod": "Any",
    "deviceClassification": "Any",
    "application": "FSES-CloudStorage-Category",
    "activity": "Any",
    "ccl": "Poor, Unknown, Low",
    "dstCountry": "Any",
    "profile": "None",
    "action": "Allow",
    "alerts": "0",
    "lastEdit": "Created Dec 15 2025 4:57 PM by stephane.lalmanach@stellantis.com",
    "status": "Enabled (Pending Changes)",
    "sourceIPEgress": "Any",
    "uci": "None",
    "app_tags": "Deroglowreputation",
    "groupOrder": "12",
    "groupName": "CASB - Stellantis",
    "osFamily": "Any"
}

```

## Notes

* 1/3 related_policies 1 to Allow specific people to access few Apps (this one) 1 to Coach the App will be blocked (temporary policy) 1 to Block

## History

_None_