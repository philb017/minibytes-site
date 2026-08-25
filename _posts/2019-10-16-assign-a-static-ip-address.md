---
title: "Assign a static ip address"
date: 2019-10-16
category: Windows
tags: [powershell]
---

**Static IP**

```powershell
Get-NetAdapter
Set-NetIPInterface -InterfaceAlias "Ethernet" -Dhcp Disabled
New-NetIPAddress -InterfaceAlias "Ethernet" -IPAddress 192.168.1.4 -PrefixLength 24 -DefaultGateway 192.168.1.1
```

**Single DNS server**

```powershell
Set-DNSClientServerAddress -InterfaceAlias "Ethernet" -ResetServerAddresses
Set-DNSClientServerAddress -InterfaceAlias "Ethernet" -ServerAddresses 192.168.1.2
```

**Two DNS servers**

```powershell
Set-DNSClientServerAddress -InterfaceAlias "Ethernet" -ResetServerAddresses
Set-DNSClientServerAddress -InterfaceAlias "Ethernet" -ServerAddresses 192.168.1.5,192.168.1.6
```

See also: [Rename a host and join to the domain]({{ '/2019/10/rename-a-host-and-join-to-the-domain/' | relative_url }}), [Chocolatey Setup and Use]({{ '/2019/10/installing-chocolatey/' | relative_url }})
