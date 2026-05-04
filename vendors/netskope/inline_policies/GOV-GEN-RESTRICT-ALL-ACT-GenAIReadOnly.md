# CASB Policy Documentation

## Policy Name

GOV-GEN-RESTRICT-ALL-ACT-GenAIReadOnly


## Optional Tags

---

## Description
- **Purpose**: Set read-only a small list of GenAI apps managed by a tag "GenAIROAct"  
- **Context**: This group of policies is needed to reduce data exfiltration risk by using unapproved AI solutions. This policy is used to let access to the documentation of some blocked apps.  
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
- **Tags**: ACT - filtering done based on Activities for compatible applications. 
- **Title**: GenAIReadOnly  

 ## Enforcement Logic
 
- **Trigger**: Access to a genAI Apps tagged "GenAIROAct" by a user. 
- **Condition**: Activities like "Add", "Ai Post", "Attach", "Upload"...
- **Exceptions**: Unrestricted users and GenAI full derogation group
- **Primary Action**: BLOCK  
- **Secondary Action**: user notification
- **Logging**: Classic logging by Netskope

## Audit & Monitoring

**Logs**: TODO: What is captured in CASB logs.

**Reports**: TODO: Frequency of reporting (daily, weekly, monthly).

**Review**: CISO/CASB

## Related Policies

GOV-GEN-ALLOW-GRP-AllowSpecificApps     → Exception management : small group to access small list of apps.
GOV-GEN-RESTRICT-ALL-POST-GenAIReadOnly → Few apps must be accessible in read only - this policy to restrict access on HTTP POST requests.
GOV-GEN-BLOCK-ALL-GenAIUnsanctioned     → Block all unsanctioned, poor GenIA Apps
GOV-GEN-COACH-ALL-Unsanctioned          → Optionnal additional policy to coach users without blocking because unauthorized but not blocked. 

## Last JSON export of the policy

{
        "ruleName": "GOV-GEN-RESTRICT-ALL-ACT-GenAIReadOnly",
        "user": "ZSSJ.CASBCoachGenAI User Exclusions: ZSSI.InternetAccessUnrestricted, ZSSJ.CASBDerogationAppsGenAIFull",
        "sourceIP": "Any",
        "srcCountry": "Any",
        "os": "Any",
        "browser": "Any",
        "accessMethod": "Any",
        "deviceClassification": "Any",
        "application": "STLA-Generative-AI-BlockingScope",
        "activity": "Add, AI Post, AI Response, API Post, Attach, Connect, Copy, Create, Delete, Edit, Invite, Post, Response, Send, Share, Upload",
        "ccl": "Any",
        "dstCountry": "Any",
        "profile": "None",
        "action": "Block: CASB-GenAI Blocking",
        "alerts": "274",
        "lastEdit": "Edited Oct 10 2025 2:22 PM by stephane.lalmanach@stellantis.com",
        "status": "Enabled ",
        "sourceIPEgress": "Any",
        "uci": "None",
        "app_tags": "Genairoact",
        "groupOrder": "12",
        "groupName": "CASB - Stellantis"
    },




## Notes

- This policy can be applied only on Apps where Netskope is able to detect Post activities


## History