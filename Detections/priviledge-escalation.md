
# Privilege Escalation Detection

## Description
Detects changes to Active Directory groups, such as adding or removing users from privileged groups.  
Event Codes: 4728, 4729

## Screenshot

![Privilege Escalation Splunk Screenshot](../Screenshots/privilege-escalation.png)

## Splunk Detection Query

```spl
index=winevents EventCode=4728 OR EventCode=4729 | table _time, EventCode, Account_Name, host
