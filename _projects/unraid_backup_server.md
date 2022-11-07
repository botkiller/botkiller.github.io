---
layout: page
title: Configure unRAID Remote Backup Server
description: Turning an old computer into a NAS for offsite backups.
img: assets/img/docker_sql.png
importance: 4
category: documentation
---

## Boot Drive
- For this build I'm using a 64GB USB Type-A flash drive as the OS boot drive. 
- Download unRAID drive maker
- Format and create boot drive
- Alter BIOS/UEFI to boot from the USB drive

## Storage Pool 
```mermaid
flowchart TB
subgraph OFFSITE
    subgraph Boot
        usb1[64GB Flash Drive]
    end

    subgraph Parity
        hdd1[14TB HDD]
    end
    subgraph Array
        hdd2[4TB HDD]
        hdd3[3TB HDD]
    end
    subgraph Cache
        ssd1[250GB SSD]
        ssd2[250GB SSD]
    end
end
```

## Apps
### Tailscale
### Plex


