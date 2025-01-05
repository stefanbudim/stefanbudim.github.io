---
title: "Linux: systemctl"
categories: [linux, systemctl]
tags: [linux]     # TAG names should always be lowercase
---

Useful systemctl commands.

# System and Service Management Commands

## List Loaded Systemd Units and Services
- `systemctl`
- `systemctl list-units --type=service`
- `systemctl --type=service`

## Show Running Services
- `systemctl list-units --type=service --state=running`
- `systemctl --type=service --state=running`

## Check Open Ports and Services
- `netstat -ltup | grep zabbix_agentd`
- `ss -ltup | grep zabbix_agentd`

## Check Firewall Open Services/Ports
- `firewall-cmd --list-services` (FirewallD)
- `firewall-cmd --list-ports` (FirewallD)
- `sudo ufw status` (UFW Firewall)

## Show Service File Content
- `systemctl cat portainer.service`

## Check if Systemd is Running
- `ps -eaf | grep [s]ystemd`

## Analyze Systemd Boot Process
- `systemd-analyze`
- `systemd-analyze blame`
- `systemd-analyze critical-chain`

## List All Available Units
- `systemctl list-unit-files`
- `systemctl list-units`
- `systemctl --failed`

## Check Service Status
- `systemctl is-enabled crond.service`
- `systemctl status firewalld.service`

# Manage Services
- List all services: `systemctl list-unit-files --type=service`
- Start: `systemctl start httpd.service`
- Restart: `systemctl restart httpd.service`
- Stop: `systemctl stop httpd.service`
- Reload: `systemctl reload httpd.service`
- Status: `systemctl status httpd.service`
- Check Active: `systemctl is-active httpd.service`
- Enable: `systemctl enable httpd.service`
- Disable: `systemctl disable httpd.service`
- Mask: `systemctl mask httpd.service`
- Unmask: `systemctl unmask httpd.service`
- Kill: `systemctl kill httpd.service`

# Manage Mount Points
- List mount points: `systemctl list-unit-files --type=mount`
- Start: `systemctl start tmp.mount`
- Stop: `systemctl stop tmp.mount`
- Restart: `systemctl restart tmp.mount`
- Reload: `systemctl reload tmp.mount`
- Status: `systemctl status tmp.mount`
- Active Check: `systemctl is-active tmp.mount`
- Enable: `systemctl enable tmp.mount`
- Disable: `systemctl disable tmp.mount`
- Mask: `systemctl mask tmp.mount`
- Unmask: `systemctl unmask tmp.mount`

# Manage Sockets
- List sockets: `systemctl list-unit-files --type=socket`
- Start: `systemctl start cups.socket`
- Restart: `systemctl restart cups.socket`
- Stop: `systemctl stop cups.socket`
- Reload: `systemctl reload cups.socket`
- Status: `systemctl status cups.socket`
- Active Check: `systemctl is-active cups.socket`
- Enable: `systemctl enable cups.socket`
- Disable: `systemctl disable cups.socket`
- Mask: `systemctl mask cups.socket`
- Unmask: `systemctl unmask cups.socket`

# CPU Utilization (Shares) of a Service
- Check CPU shares: `systemctl show -p CPUShares httpd.service`
