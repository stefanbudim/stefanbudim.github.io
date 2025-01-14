---
title: "Linux: Set System Timezone Based on your IP Address"
categories: [linux, timezone]
tags: [linux]     # TAG names should always be lowercase
---

## Set system timezone based on your IP Address.
```bash
ln -fs /usr/share/zoneinfo/$(wget -qO - http://ip-api.com/line?fields=timezone) /etc/localtime
```
The more static way would be
```bash
ln -fs /usr/share/zoneinfo/Europe/Berlin /etc/localtime
```
## [ip-api.com](../ip-api.com)


## Limitations
The command depends on the availability and reliability of [ip-api.com](https://ip-api.com/).
