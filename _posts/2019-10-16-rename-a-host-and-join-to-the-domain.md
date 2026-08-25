---
title: "Rename a host and join to the domain"
date: 2019-10-16
category: Windows
tags: [powershell]
---

```powershell
$hostname = "NEW-HOSTNAME"
$Domain = "domain.local"
$Credential = Get-Credential

Rename-Computer $hostname
Add-Computer -Domain $Domain -NewName $hostname -Credential $Credential -Restart
```

See also: [Assign a static ip address]({{ '/2019/10/assign-a-static-ip-address/' | relative_url }})
