---
title: "Check if a Windows Update is Installed"
date: 2021-10-19
category: Windows
tags: [powershell]
---

Quick PowerShell command to check if a Windows update is installed on a computer.

**List every hotfix installed**

```powershell
Get-HotFix
```

**Check for a specific KB**

```powershell
Get-HotFix -Id KBXXXXXX
```

Reference: [Get-HotFix (PowerShell docs)](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-hotfix)

See also: [Automate Windows Update]({{ '/2021/10/automate-windows-update/' | relative_url }})
