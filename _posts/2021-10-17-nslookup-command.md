---
title: "NSLookup Command"
date: 2021-10-17
category: Other
---

Displays information you can use to diagnose Domain Name System (DNS) infrastructure.

Reference: [nslookup syntax (Microsoft docs)](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/nslookup)

```powershell
nslookup -type=soa minibytes.com.au 9.9.9.9
nslookup -type=ns minibytes.com.au 9.9.9.9
nslookup -type=mx minibytes.com.au 9.9.9.9
nslookup -type=txt minibytes.com.au 9.9.9.9
nslookup -type=a minibytes.com.au 9.9.9.9
nslookup -type=any minibytes.com.au 9.9.9.9
```

(Using Quad9's `9.9.9.9` resolver here — swap in whichever DNS server you want to query against.)
