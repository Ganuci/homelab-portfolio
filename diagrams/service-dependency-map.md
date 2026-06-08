# Homelab Service Dependency Map

## Purpose

This document provides a public-safe overview of how key homelab services depend on each other.

The aim is to show service relationships, troubleshooting logic and infrastructure thinking without exposing sensitive live configuration such as IP addresses, hostnames, VLAN IDs, domain names, ports, credentials, firewall rules or management URLs.

---

## High-Level Service Map

```text
Core Network
Router / Gateway
Managed Switch
Wireless Access Point
        |
        |-- DNS Filtering
        |     Raspberry Pi 4 / Pi-hole
        |
        |-- NAS Storage
        |     Lenovo M720Q / TrueNAS SCALE
        |
        |-- Media Services
        |     Lenovo M720Q / Plex
        |     Depends on NAS storage and network access
        |
        |-- Admin and Monitoring
        |     Lenovo M920X / Uptime Kuma / Homarr
        |     Monitors selected services
        |
        |-- Monitoring Display
        |     Raspberry Pi 5 / Kiosk dashboard
        |
        |-- Download / VPN Workflow
        |     Lenovo M700
        |     Depends on VPN, DNS and storage access where required
        |
        |-- IoT Services
              Home Assistant / smart devices
              Depends on Wi-Fi, DNS and network segmentation
```

---

## Core Dependencies

| Service Area            | Depends On                                                          | If It Fails                                                               |
| ----------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| DNS filtering           | Raspberry Pi 4, network connectivity, DNS configuration             | Devices may appear connected but websites/services may not load           |
| NAS storage             | TrueNAS server, disks, SMB, permissions, network connectivity       | Media and file access may fail                                            |
| Plex media server       | Media server, NAS access, storage permissions, network connectivity | Media may not appear or playback may fail                                 |
| Monitoring              | Admin server, monitored targets, network connectivity               | Reduced visibility of service status                                      |
| Kiosk display           | Raspberry Pi 5, dashboard access, network connectivity              | Monitoring display may not show current status                            |
| Download / VPN workflow | Download server, VPN connection, DNS, storage path where required   | Downloads or related services may stop working                            |
| IoT devices             | Wi-Fi, IoT network, DNS, internet access, segmentation rules        | Smart devices may fail to connect or respond                              |
| Enterprise learning lab | Power, cabling, switch configuration, test devices                  | Lab testing may be unavailable but core services should remain unaffected |

---

## Troubleshooting Logic

The dependency map helps support structured troubleshooting.

For example:

### If Plex is unavailable

Check in this order:

1. Is the media server online?
2. Is Plex running?
3. Can the media server reach the NAS?
4. Are SMB/storage permissions working?
5. Is DNS working?
6. Is the issue affecting only Plex or other services too?
7. Does monitoring show a wider outage?

### If devices cannot browse the internet

Check in this order:

1. Is the device connected to the correct network?
2. Is the gateway reachable?
3. Is DNS working?
4. Is Pi-hole available?
5. Is the issue affecting one device or multiple devices?
6. Is the problem related to filtering or allowlisting?
7. Is the internet connection itself available?

### If IoT devices stop working

Check in this order:

1. Are the devices connected to the IoT Wi-Fi?
2. Is the access point online?
3. Is DNS available to the IoT network?
4. Do the devices require local network access?
5. Are segmentation rules too restrictive?
6. Is the issue with one device type or all IoT devices?

### If the download workflow fails

Check in this order:

1. Is the download server online?
2. Is the relevant service running?
3. Is the VPN connection active?
4. Is DNS working through the VPN path?
5. Is storage access available where required?
6. Is the issue caused by VPN, DNS, application or storage dependency?

---

## Why Dependencies Matter

A service can fail because of its own configuration, but it can also fail because something it depends on is unavailable.

For example:

* Plex may appear broken when the real issue is NAS access.
* Internet access may appear broken when the real issue is DNS.
* IoT devices may appear unreliable when the issue is Wi-Fi or segmentation.
* Download services may appear down when the issue is VPN connectivity.
* Monitoring may show multiple failures if a shared dependency is unavailable.

Understanding dependencies makes troubleshooting faster and more methodical.

---

## Monitoring Use

Monitoring helps identify whether a problem is isolated or part of a wider issue.

Useful monitoring questions include:

* Is only one service down?
* Are multiple services on the same host down?
* Are services across different hosts down?
* Is DNS unavailable?
* Is storage unavailable?
* Did a service become unavailable after a network change?
* Is a dependency causing multiple alerts?

Monitoring does not replace troubleshooting, but it gives a better starting point.

---

## Public-Safe Documentation Notes

This document intentionally does not publish:

* Internal IP addresses.
* Hostnames.
* Domain names.
* Ports.
* VLAN IDs.
* Firewall rules.
* Storage paths.
* Share names.
* DNS records.
* VPN details.
* Monitoring targets.
* Service URLs.
* Credentials.
* Screenshots from live systems.

The focus is on dependency awareness and troubleshooting logic.

---

## Skills Demonstrated

This document demonstrates practical understanding of:

* Service dependency mapping
* Infrastructure troubleshooting
* DNS dependency
* Storage dependency
* Network service relationships
* Monitoring logic
* Role separation
* Incident-style thinking
* Public-safe technical documentation

---

## Future Improvements

Planned improvements include:

* Create a visual service dependency diagram.
* Add public-safe troubleshooting flowcharts.
* Add service priority levels.
* Document which services are core, useful or experimental.
* Build monitoring checks around the most important dependencies.
* Add a change log for service-impacting updates.
