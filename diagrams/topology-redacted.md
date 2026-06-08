# Redacted Homelab Topology

## Purpose

This document provides a simplified, public-safe topology of my homelab.

The purpose is to show how the main systems relate to each other without exposing sensitive details such as live IP addresses, VLAN IDs, hostnames, firewall rules, MAC addresses, serial numbers, DNS records or management URLs.

This topology is intended for documentation and portfolio purposes only. It is not a full live network map.

---

## High-Level Topology

```text
Internet
   |
Router / Gateway
UniFi Cloud Gateway Max
   |
Managed Switch
Cisco Business CBS250-8T-D
   |
   |-- NAS Server
   |     Lenovo M720Q
   |     TrueNAS SCALE / SMB storage
   |
   |-- Media Server
   |     Lenovo M720Q
   |     Plex and media applications
   |
   |-- Admin Server
   |     Lenovo M920X
   |     Services, monitoring and administration
   |
   |-- Download / VPN Server
   |     Lenovo M700
   |     VPN-protected download workflow
   |
   |-- Raspberry Pi DNS
   |     Raspberry Pi 4
   |     Pi-hole DNS filtering
   |
   |-- Monitoring / Kiosk Display
   |     Raspberry Pi 5
   |     Dashboard and monitoring display
   |
   |-- Wireless Access Point
   |     UniFi AP via PoE injector
   |        |
   |        |-- Trusted Wi-Fi
   |        |-- IoT Wi-Fi
   |
   |-- Enterprise Learning Lab
         |
         |-- Dell PowerEdge R710
         |-- Dell SC1435
         |-- Cisco Catalyst 3560 switches
```

---

## Network Zones

The homelab is organised by device role and trust level.

| Zone                    | Purpose                            | Example Devices                         |
| ----------------------- | ---------------------------------- | --------------------------------------- |
| Trusted / Admin         | Personal and administrative access | Main devices used to manage the lab     |
| Server / Lab            | Core homelab services              | NAS, media, admin and download servers  |
| IoT                     | Less trusted smart home devices    | Smart home and connected devices        |
| Monitoring              | Visibility and status checking     | Uptime Kuma, Raspberry Pi kiosk display |
| DNS                     | Name resolution and filtering      | Raspberry Pi running Pi-hole            |
| Enterprise Learning Lab | Testing and CCNA-aligned learning  | Dell servers and Cisco switches         |

Exact VLAN IDs, IP ranges and firewall rules are intentionally not published.

---

## Service Relationships

The main service relationships are:

```text
Trusted/Admin Devices
        |
        |-- Manage core infrastructure
        |-- Access storage where permitted
        |-- View monitoring dashboards

NAS Server
        |
        |-- Provides storage for selected services
        |-- Supports SMB file access
        |-- Supports media storage

Media Server
        |
        |-- Runs Plex and related services
        |-- Depends on storage access from NAS

DNS Server
        |
        |-- Provides DNS filtering
        |-- Supports client name resolution

Monitoring
        |
        |-- Checks selected service availability
        |-- Helps identify service, host or dependency issues

Download / VPN Server
        |
        |-- Runs separated VPN-protected download workflow
        |-- Kept separate from NAS, media and admin systems

IoT Network
        |
        |-- Provides internet access for smart devices
        |-- Restricted from unnecessary access to trusted systems
```

---

## Design Principles

The topology is based on the following design principles:

* Keep system roles clear and separated.
* Avoid running every service on one machine.
* Separate less trusted IoT devices from trusted systems.
* Keep core storage separate from application hosting where practical.
* Use monitoring to improve troubleshooting visibility.
* Use dedicated devices for DNS and monitoring where useful.
* Keep enterprise learning equipment separate from the main live environment.
* Document the environment safely without exposing sensitive details.

---

## Why the Lab Is Split by Role

The lab uses several smaller systems rather than one large all-in-one server.

This approach helps with learning because each system has a clear purpose:

* If storage fails, the NAS is the first area to investigate.
* If media playback fails, the media server and NAS relationship can be checked.
* If browsing or name resolution fails, DNS can be checked.
* If a service becomes unavailable, monitoring can confirm whether it is isolated or wider.
* If IoT devices behave unexpectedly, the IoT network can be reviewed separately.
* If networking concepts need testing, the enterprise learning lab can be used without disrupting core services.

This makes troubleshooting more structured and closer to real infrastructure thinking.

---

## Security and Redaction Notes

This topology does not include:

* Internal IP addresses.
* Public IP addresses.
* VLAN IDs.
* Subnet ranges.
* Hostnames.
* MAC addresses.
* Serial numbers.
* SSIDs.
* Firewall rules.
* DNS records.
* Reverse proxy hostnames.
* Management URLs.
* VPN details.
* Exact switch port mappings.

The aim is to show architecture and design thinking without exposing the live network.

---

## Future Improvements

Planned improvements include:

* Create a visual version of this topology as a redacted diagram.
* Add a separate service dependency map.
* Add a public-safe rack layout.
* Add a simplified network-zone diagram.
* Document how monitoring supports troubleshooting across the topology.
