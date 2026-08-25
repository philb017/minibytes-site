---
title: "Chocolatey Setup and Use"
date: 2019-10-16
category: Windows
---

Requires Windows 7+ / Server 2003+, PowerShell v2+, and .NET Framework 4+ (Chocolatey will try to install .NET 4.0 if it's missing).

**Install**

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

**Base setup**

```powershell
choco install adobereader 7zip anydesk -y
```

**Individual apps** (pick what you need)

```powershell
choco install firefox -y
choco install googlechrome -y
choco install microsoft-edge -y
choco install ccleaner -y
choco install vlc -y
choco install winscp -y
choco install putty -y
choco install keepass -y
choco install vmware-vsphere-client -y
```

**Antimalware**

```powershell
choco install kaspersky -y
choco install bitdefender -y
choco install esetnod32antivirus -y
choco install malwarebytes -y
```

See also: [Assign a static ip address]({{ '/2019/10/assign-a-static-ip-address/' | relative_url }}), [Eset Antivirus]({{ '/2021/10/eset-antivirus/' | relative_url }})
