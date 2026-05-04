# CASB Policy Documentation

## Policy Name

GOV-GEN-ALLOW-GRP-AllowSpecificApps

## Optional Tags

---

## Description
- **Purpose**: Allow small group of users to access short list of GenAI apps managed by a tag "GenAIDerog01"  
- **Context**: This group of policies is needed to reduce data exfiltration risk by using unapproved AI solutions. This policy can be used for some kinds of derogations.  
- **Behavior**: Allow 
- **Version**: 1.0  
- **Owner**: CISO/SBD Team  
- **Source**: Stellantis AI policy 

---

## Naming Breakdown
- **Category**: GOV  
- **Application**: GEN  
- **Action**: ALLOW
- **Scope**: GRP  
- **Tags**:   
- **Title**: AllowSpecificApps  

 ## Enforcement Logic
 
- **Trigger**: Access to a genAI Apps tagged "GenAIDerog01" by a specific group of users 
- **Condition**: The user is part of ZSSJ.CASBDerogationAppsGenAI and try to access to a GenAI App tagged "GenAIDerog01"
- **Exceptions**: - , this policy is a way to set exceptions to the global GenAI Apps access policy. 
- **Primary Action**: ALLOW  
- **Secondary Action**: 
- **Logging**: Classic logging by Netskope

## Audit & Monitoring

**Logs**: TODO: What is captured in CASB logs.

**Reports**: TODO: Frequency of reporting (daily, weekly, monthly).

**Review**: CISO/CASB

## Related Policies

GOV-GEN-RESTRICT-ALL-ACT-GenAIReadOnly  → Few apps must be accessible in read only - this policy to restrict access on activities.
GOV-GEN-RESTRICT-ALL-POST-GenAIReadOnly → Few apps must be accessible in read only - this policy to restrict access on HTTP POST requests.
GOV-GEN-BLOCK-ALL-GenAIUnsanctioned     → Block all unsanctioned, poor GenIA Apps
GOV-GEN-COACH-ALL-Unsanctioned          → Optionnal additional policy to coach users without blocking because unauthorized but not blocked. 

## Last JSON export of the policy

    {
        "ruleName": "GOV-GEN-ALLOW-GRP-AllowSpecificApps",
        "user": "ZSSJ.CASBDerogationAppsGenAI ",
        "sourceIP": "Any",
        "srcCountry": "Any",
        "os": "Any",
        "browser": "Any",
        "accessMethod": "Any",
        "deviceClassification": "Any",
        "application": "Generative AI",
        "activity": "Any",
        "ccl": "Any",
        "dstCountry": "Any",
        "profile": "None",
        "action": "Allow",
        "alerts": "0",
        "lastEdit": "Created Sep 26 2025 9:13 AM by stephane.lalmanach@stellantis.com",
        "status": "Enabled ",
        "sourceIPEgress": "Any",
        "uci": "None",
        "app_tags": "Genaiderog01",
        "groupOrder": "12",
        "groupName": "CASB - Stellantis"
    }




## Notes

- user group is managed in Reunis, Apps list is manage through tags


## History