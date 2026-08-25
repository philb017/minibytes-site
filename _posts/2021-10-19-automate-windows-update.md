---
title: "Automate Windows Update"
date: 2021-10-19
category: Windows
tags: [powershell]
---

Run from an elevated PowerShell session.

```powershell
Set-ExecutionPolicy RemoteSigned
Install-Module -Name PSWindowsUpdate
Add-WUServiceManager -MicrosoftUpdate
Install-WindowsUpdate -MicrosoftUpdate -AcceptAll
```

Note: this will not reboot the system when it's done — schedule a reboot separately if needed.

See also: [Chocolatey Setup and Use]({{ '/2019/10/installing-chocolatey/' | relative_url }}), [Check if a Windows Update is Installed]({{ '/2021/10/check-if-a-windows-update-is-installed/' | relative_url }})
