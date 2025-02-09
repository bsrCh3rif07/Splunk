Identify Windows account password changes:
```
index=wineventlog source="*:Security" (EventCode=4723 OR EventCode=4724) | table host,source,action,dvc,name,user,user_group
```

Identify Windows security-related logon session events:
```
index=wineventlog source="*:Security" (EventCode=4624 OR EventCode=4647) | search user!="SYSTEM" | table _time,host,source,action,name,user,user_group
```

Identify Windows account disabled events:
```
index=wineventlog source="*:Security" (EventCode=4725 OR EventCode=4726) | table _time,host,source,action,name,user,user_group
```

Identify Windows account logon events:
```
index=wineventlog source="*:Security" EventCode=4624 Logon_Type!=3 | search  user!="SYSTEM" | table host,source,action,dvc,name,user,user_group
```

Detect Windows account logoff events:
```
index=wineventlog source="*:Security" EventCode=4634 | table host,source,action,dvc,name,user,user_group
```

Monitor Windows account creations:
```
index=wineventlog source="*:Security" (EventCode=4720 OR EventCode=4722) | table host,source,action,dvc,name,user,user_group
```

Monitor successful logins on Windows:
```
index=wineventlog source="*:Security" EventCode=4624 | table host,source,action,app,dvc,name,user,user_group
```

Identify Windows security-related policy changes:
```
index=wineventlog source="*:Security" (EventCode=4719 OR EventCode=4904 OR EventCode=4905) | table _time,host,source,action,subject,user,object_attrs
```

Identify failed login attempts on Windows:
```
index=wineventlog source="*:Security" EventCode=4625
```

Detect account lockouts on Windows:
```
index=wineventlog source="*:Security" EventCode=4740
```

Identify Windows security group modifications:
```
index=wineventlog source="*:Security" (EventCode=4727 OR EventCode=4728 OR EventCode=4731)
```

Detect changes to Windows security policy settings:
```
index=wineventlog source="*:Security" EventCode=4704
```

Identify Windows process creations:
```
index=wineventlog source="*:Security" EventCode=4688
```

Monitor Windows firewall rule modifications:
```
index=wineventlog source="*:Security" EventCode=2004
```

Detect Windows system shutdown or restart events:
```
index=wineventlog source="*:Security" (EventCode=4608 OR EventCode=4609)
```

Monitor Windows service creation or modification events:
```
index=wineventlog source="*:Security" (EventCode=4697 OR EventCode=4698)
```

Monitor Windows account lockout duration and threshold changes:
```
index=wineventlog source="*:Security" EventCode=4767
```

Monitor Windows file and folder permission changes:
```
index=wineventlog source="*:Security" (EventCode=4663 OR EventCode=4670)
```

Detect Windows account privilege changes:
```
index=wineventlog source="*:Security" (EventCode=4672 OR EventCode=4673)
```

Monitor Windows registry modification events:
```
index=wineventlog source="*:Security" (EventCode=4657 OR EventCode=4658)
```

Identify Windows security-related audit policy changes:
```
index=wineventlog source="*:Security" (EventCode=4718 OR EventCode=4907)
```

Monitor Windows account password reset events:
```
index=wineventlog source="*:Security" (EventCode=4724 OR EventCode=4726)
```

Identify Windows account group membership changes:
```
index=wineventlog source="*:Security" (EventCode=4728 OR EventCode=4732)
```

Detect Windows account impersonation events:
```
index=wineventlog source="*:Security" EventCode=4648 | table _time,host,source,action,name,user,user_group
```

Monitor Windows security-related account management events:
```
index=wineventlog source="*:Security" EventCode=4648 | table _time,host,source,action,name,user,user_group
```

Identify Windows process termination events:
```
index=wineventlog source="*:Security" EventCode=4689
```
 
Monitor Windows account privilege use events:
```
index=wineventlog source="*:Security" EventCode=4674
```

Identify Windows security-related user rights assignment changes:
```
index=wineventlog source="*:Security" EventCode=4703
```

Detect Windows account password hash changes:
```
index=wineventlog source="*:Security" (EventCode=4781 OR EventCode=4782)
```

Monitor Windows account password expiration events:
```
index=wineventlog source="*:Security" (EventCode=642 OR EventCode=648)
```

Identify Windows security-related log management events:
```
index=wineventlog source="*:Security" (EventCode=1102 OR EventCode=1104)
```

Monitor Windows account password policy changes:
```
index=wineventlog source="*:Security" EventCode=4713
```

Identify Windows account password expiration reminders:
```
index=wineventlog source="*:Security" (EventCode=768 OR EventCode=769)
```

Detect Windows account password history changes:
```
index=wineventlog source="*:Security" (EventCode=4780 OR EventCode=4783)
```

Monitor Windows account password failed attempts:
```
index=wineventlog source="*:Security" (EventCode=4625 AND Logon_Type=10)
```

Identify Windows security-related object access events:
```
index=wineventlog source="*:Security" (EventCode=4660 OR EventCode=4661 OR EventCode=4662)
```

Monitor Windows account privilege escalation events:
```
index=wineventlog source="*:Security" EventCode=4672 Logon_Type=3
```

Identify Windows security-related account logon failures:
```
index=wineventlog source="*:Security" EventCode=4625 Logon_Type=2
```

Detect Windows account password policy enforcement events:
```
index=wineventlog source="*:Security" (EventCode=4508 OR EventCode=4509)
```

Monitor Windows account password changes made by other users:
```
index=wineventlog source="*:Security" (EventCode=4784 OR EventCode=4785)
```

Identify Windows security-related security log management events:
```
index=wineventlog source="*:Security" (EventCode=1100 OR EventCode=1108)
```

Monitor Windows account password expiration warnings:
```
index=wineventlog source="*:Security" EventCode=769
```

Detect Windows account privilege use failures:
```
index=wineventlog source="*:Security" EventCode=4673
```

Monitor Windows account logon failures due to account restriction:
```
index=wineventlog source="*:Security" EventCode=4625 Failure_Reason="Account restriction"
```

Identify Windows security-related process token adjustments:
```
index=wineventlog source="*:Security" EventCode=4675
```

Monitor Windows account logon events with non-standard logon types:
```
index=wineventlog source="*:Security" EventCode=4624 Logon_Type!=2 Logon_Type!=3 Logon_Type!=10
```

Identify Windows security-related events for system time changes:
```
index=wineventlog source="*:Security" EventCode=4616
```

Detect Windows account logon events with failed authentication:
```
index=wineventlog source="*:Security" EventCode=4625 Logon_Type=3 Status="0xC000006D"
```

Monitor Windows account password change failures:
```
index=wineventlog source="*:Security" EventCode=627
```

Identify Windows security-related events for changes in system audit policy:
```
index=wineventlog source="*:Security" EventCode=4706
```

Monitor Windows account logon events with failed network authentication:
```
index=wineventlog source="*:Security" EventCode=4625 Logon_Type=3 Failure_Reason="Network Error"
```

Identify Windows security-related events for changes in user rights assignment:
```
index=wineventlog source="*:Security" EventCode=4702
```

Detect Windows account logon events with expired passwords:
```
index=wineventlog source="*:Security" EventCode=4625 Failure_Reason="Expired Password"
```

Monitor Windows account password changes made by privileged accounts:
```
index=wineventlog source="*:Security" (EventCode=4784 OR EventCode=4785) Account_Name!="SYSTEM" Account_Name!="Administrator"
```

Identify Windows security-related events for changes in trusted domain settings:
```
index=wineventlog source="*:Security" EventCode=4707
```

Monitor Windows account logon events with failed Kerberos pre-authentication:
```
index=wineventlog source="*:Security" EventCode=4625 Logon_Type=3 Failure_Reason="KDC_ERR_PREAUTH_FAILED"
```

Identify Windows security-related events for changes in security log settings:
```
index=wineventlog source="*:Security" EventCode=4719
```

Detect Windows account logon events with invalid workstation or server name:
```
index=wineventlog source="*:Security" EventCode=4625 Logon_Type=3 Failure_Reason="Unknown user name or bad password"
```

Monitor Windows account password changes made by service accounts:
```
index=wineventlog source="*:Security" (EventCode=4784 OR EventCode=4785) Account_Name="*SERVICE*"
```

Identify Windows security-related events for changes in audit policy subcategory settings:
```
index=wineventlog source="*:Security" EventCode=4718
```

Monitor Windows account logon events with failed smart card authentication:
```
index=wineventlog source="*:Security" EventCode=4625 Logon_Type=3 Failure_Reason="Smart Card Logon Failed"
```

Identify Windows security-related events for changes in account logon settings:
```
index=wineventlog source="*:Security" (EventCode=4716 OR EventCode=4717)
```

Detect Windows account logon events with expired or disabled accounts:
```
index=wineventlog source="*:Security" EventCode=4625 Failure_Reason="User Account Expired" OR Failure_Reason="Account Disabled"
```

Monitor Windows account password changes made with elevated privileges:
```
index=wineventlog source="*:Security" (EventCode=4784 OR EventCode=4785) Privileged_Account=true
```

Identify Windows security-related events for changes in account logon policies:
```
index=wineventlog source="*:Security" EventCode=4715
```

Monitor Windows account logon events with failed NTLM authentication:
```
index=wineventlog source="*:Security" EventCode=4625 Logon_Type=3 Failure_Reason="NTLM blocked"
```

Identify Windows security-related events for changes in group account settings:
```
index=wineventlog source="*:Security" (EventCode=4727 OR EventCode=4729 OR EventCode=4733)
```

Detect Windows account logon events with expired or disabled passwords:
```
index=wineventlog source="*:Security" EventCode=4625 Failure_Reason="Expired Password" OR Failure_Reason="Disabled Account"
```

Monitor Windows account password changes made by remote systems:
```
index=wineventlog source="*:Security" (EventCode=4784 OR EventCode=4785) Workstation_Name!="*LOCAL*"
```

Identify Windows security-related events for changes in audit policy category settings:
```
index=wineventlog source="*:Security" (EventCode=4717 OR EventCode=4906)
```

