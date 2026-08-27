---
title: "Screenly OSE"
date: 2019-10-17
category: Utilities
---

Download the image from the GitHub releases page and flash it with balenaEtcher.

**Enable SSH**

After flashing, wait for the boot volume to appear, then drop an empty file named `ssh` (or `ssh.txt`) into the `/boot/` partition.

**Fix 1080p display issues**

Edit `/boot/config.txt`:

```ini
disable_overscan=1
hdmi_group=1
hdmi_mode=16
```

**Update**

```bash
bash <(curl -sL https://www.screenly.io/install-ose.sh)
```

**NTP sync**

```bash
yum install ntpdate -y
timedatectl
```

See also: [Domain Management Websites]({{ '/2021/10/domain-management-websites/' | relative_url }})
