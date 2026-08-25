---
title: "Unifi Controller Upgrade Procedure (Red Hat)"
date: 2021-10-16
category: Ubiquiti
---

Should work on any Red Hat based distro.

**1. Stop the UniFi service**

```bash
systemctl stop unifi.service
systemctl status unifi.service
```

**2. Back up the current configuration**

```bash
tar -zcvf /root/backup.tar.gz /opt/UniFi/data/
```

**3. Download the new UniFi package**

Check the current version at [ui.com/download/unifi](https://www.ui.com/download/unifi/) first.

```bash
wget https://dl.ubnt.com/unifi/5.10.24/UniFi.unix
wget https://dl.ui.com/unifi/6.4.54/UniFi.unix.zip
```

**4. Unzip and fix ownership**

```bash
unzip -qo /root/UniFi.unix -d /opt
chown -R ubnt:ubnt /opt/UniFi
```

**5. Restore the configuration backup**

```bash
tar -xzvf backup.tar.gz -C /
```

**6. Start the UniFi service**

```bash
systemctl start unifi.service
systemctl status unifi.service
```

**7. Tidy up**

```bash
mv backup.tar.gz controller-backup-5-10-24.tar.gz
mv UniFi.unix.zip UniFi.unix-5-10-24.zip
rm UniFi.unix
```
