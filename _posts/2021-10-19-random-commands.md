---
title: "Random Commands"
date: 2021-10-19
category: Windows
---

A grab-bag of one-liners that come up often enough to keep handy.

**Force an immediate reboot**

```powershell
shutdown /f /r /t 0
```

**PsExec — remote command execution**

```powershell
psexec \\computername cmd
psexec \\computername -u domain\user -p password cmd
psexec \\computername powershell enable-psremoting -force
```

See also: [AnyDesk]({{ '/2021/10/anydesk/' | relative_url }}) for remote access without PsExec.
