# CASB Policy Documentation

## Policy Name

GOV-GEN-BLOCK-ALL-GenAIUnsanctioned

## Optional Tags

---

## Description
- **Purpose**: Block Poor unsanctioned Generative AI apps access  
- **Context**: This group of policies is needed to reduce data exfiltration risk by using unapproved AI solutions  
- **Behavior**: Block 
- **Version**: 1.0  
- **Owner**: CISO/SBD Team  
- **Source**: Stellantis AI policy 

---

## Naming Breakdown
- **Category**: GOV  
- **Application**: GEN  
- **Action**: BLOCK
- **Scope**: ALL  
- **Tags**:   
- **Title**: GenAIUnsanctioned  

 ## Enforcement Logic
 
- **Trigger**: Access to an App that have a "poor" or "Unknown" reputation and is "unsanctioned. 
- **Condition**: Target is full Stellantis perimeter
- **Exceptions**: Unrestricted users and full AI exception group 
- **Primary Action**: BLOCK  
- **Secondary Action**: Notification display to the user with a link to AI Team recommandations
- **Logging**: Classic logging by Netskope

## Audit & Monitoring

**Logs**: TODO: What is captured in CASB logs.

**Reports**: TODO: Frequency of reporting (daily, weekly, monthly).

**Review**: CISO/CASB

## Related Policies

GOV-GEN-ALLOW-GRP-AllowSpecificApps     → Exception management : small group to access small list of apps.
GOV-GEN-RESTRICT-ALL-ACT-GenAIReadOnly  → Few apps must be accessible in read only - this policy to restrict access on activities.
GOV-GEN-RESTRICT-ALL-POST-GenAIReadOnly → Few apps must be accessible in read only - this policy to restrict access on HTTP POST requests.
GOV-GEN-COACH-ALL-Unsanctioned          → Optionnal additional policy to coach users without blocking because unauthorized but not blocked. 

## Last JSON export of the policy

{
        "ruleName": "GOV-GEN-BLOCK-ALL-GenAIUnsanctioned",
        "user": "All User Exclusions: ZSSI.InternetAccessUnrestricted, ZSSJ.CASBDerogationAppsGenAIFull",
        "sourceIP": "Any",
        "srcCountry": "Any",
        "os": "Any",
        "browser": "Any",
        "accessMethod": "Any",
        "deviceClassification": "Any",
        "application": "STLA-Generative-AI-BlockingScope",
        "activity": "Any",
        "ccl": "Poor, Unknown",
        "dstCountry": "Any",
        "profile": "None",
        "action": "Alert",
        "alerts": "474",
        "lastEdit": "Edited Oct 13 2025 2:25 PM by stephane.lalmanach@stellantis.com",
        "status": "Enabled ",
        "sourceIPEgress": "Any",
        "uci": "None",
        "app_tags": "Unsanctioned",
        "groupOrder": "12",
        "groupName": "CASB - Stellantis",
        "custom_ad_attributes": {
            "OU_LVL123": [
                "HR/ICT/CISO"
            ]
        }
    }




## Notes

- started by few one, the target will be extended progressively

## History

