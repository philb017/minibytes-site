---
title: "Smokeping Install"
date: 2019-10-17
category: Linux
---

Start with a minimal install of CentOS 7.

```bash
yum update -y
yum install epel-release -y
yum install smokeping httpd perl-Net-Telnet perl-Net-DNS perl-LDAP perl-libwww-perl cairo pango -y
```

Edit the main config:

```
/etc/smokeping/config.conf
```

**SELinux / firewall**

```bash
setenforce 0
```
(and set `SELINUX=disabled` in `/etc/selinux/config` if you want it permanent)

```bash
firewall-cmd --permanent --add-port=80/tcp
firewall-cmd --reload
```

**Start services**

```bash
systemctl enable --now httpd
systemctl enable --now smokeping
systemctl status httpd
systemctl status smokeping
```

Access at `http://serverip/smokeping/sm.cgi`.

See also: [Cockpit]({{ '/2019/10/cockpit/' | relative_url }})
