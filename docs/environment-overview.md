# Homelab Environment Overview

## Purpose

This document provides a public-safe overview of my homelab environment.

The homelab is used to develop practical skills in IT support, infrastructure, networking, storage, virtualisation, monitoring, self-hosting and troubleshooting. It is designed as a hands-on learning environment that allows me to build, break, repair, document and improve real systems.

This documentation does not include live IP addresses, credentials, VLAN IDs, internal hostnames, serial numbers, MAC addresses, domain names, firewall exports or management URLs.

---

## Design Goals

The main goals of the homelab are to:

* Build practical experience with real infrastructure.
* Develop confidence with networking, switching and segmentation.
* Practise storage planning and NAS administration.
* Host useful self-managed services.
* Learn monitoring and service availability concepts.
* Troubleshoot issues across hardware, network, storage and application layers.
* Support CCNA-aligned networking practice.
* Document technical work in a clear and public-safe way.
* Build a portfolio that demonstrates readiness for IT Support, Technical Support and Junior Infrastructure roles.

---

## High-Level Architecture

The environment is built around a small business / homelab-style network with dedicated systems for storage, media, administration, downloads, DNS and monitoring.

At a high level, the environment includes:

* UniFi gateway for routing, firewall and network management.
* Cisco managed switch for wired connectivity and VLAN learning.
* UniFi wireless access point for Wi-Fi and IoT network separation.
* Lenovo mini PCs used as dedicated servers.
* Raspberry Pi devices used for lightweight services.
* Enterprise hardware used for testing, learning and CCNA practice.

The environment is intentionally split by role so that each system has a clear purpose.

---

## Core Network

| Component             | Model                        | Role                                                    |
| --------------------- | ---------------------------- | ------------------------------------------------------- |
| Router / Gateway      | UniFi Cloud Gateway Max      | Main gateway, firewall and network controller           |
| Managed Switch        | Cisco Business CBS250-8T-D   | Wired connectivity, VLAN learning and switch management |
| Wireless Access Point | UniFi access point           | Wi-Fi and IoT network separation                        |
| PoE                   | PoE injector                 | Powers the UniFi access point                           |
| Learning Switches     | Cisco Catalyst 3560 switches | CCNA switching practice and lab testing                 |

The core network gives me practical exposure to both web-managed network equipment and Cisco CLI-based switching.

---

## Server Inventory

| Role               | Hardware                     | Specification                                               | Purpose                                              |
| ------------------ | ---------------------------- | ----------------------------------------------------------- | ---------------------------------------------------- |
| NAS                | Lenovo M720Q                 | i5-8400T, 32GB RAM, SSD system storage and HDD data storage | TrueNAS storage server                               |
| Media              | Lenovo M720Q                 | i5-9400T, 32GB RAM, 250GB SSD                               | Plex and media applications                          |
| Admin              | Lenovo M920X                 | i7-8700, 48GB RAM, 250GB SSD                                | Services, monitoring and administration              |
| Download / VPN     | Lenovo M700                  | i5-6400T, 8GB RAM, 250GB SSD                                | VPN-protected download workflow                      |
| Monitoring / Kiosk | Raspberry Pi 5               | Raspberry Pi platform                                       | Monitoring display and dashboard use                 |
| DNS                | Raspberry Pi 4               | Raspberry Pi platform                                       | Pi-hole DNS filtering                                |
| Enterprise Lab     | Dell PowerEdge R710          | Enterprise server platform                                  | Testing, server learning and infrastructure practice |
| Enterprise Lab     | Dell SC1435                  | Enterprise server platform                                  | Testing and infrastructure learning                  |
| Switching Lab      | Cisco Catalyst 3560 switches | 4 switches                                                  | CCNA switching practice                              |

Exact addressing, hostnames and management details are not published.

---

## Server Role Separation

The homelab uses role separation to make the environment easier to understand, troubleshoot and maintain.

### NAS Server

The NAS is used for centralised storage and runs TrueNAS SCALE. It supports storage learning, SMB shares, dataset planning, storage health awareness and permissions practice.

### Media Server

The media server runs Plex and related media applications. It is separated from the NAS so that media hosting and storage are easier to troubleshoot independently.

### Admin Server

The admin server is used for services, monitoring and general administration. It supports the wider lab by hosting or managing tools used for visibility and infrastructure management.

### Download / VPN Server

The download server is used for VPN-protected download workflows. It keeps this activity separated from the NAS, media server and admin server.

### Raspberry Pi 5

The Raspberry Pi 5 is used for monitoring and kiosk-style dashboard display. This gives quick visual access to service status and monitoring information.

### Raspberry Pi 4

The Raspberry Pi 4 is used for Pi-hole DNS filtering. This provides practical experience with DNS, filtering, network visibility and core service reliability.

### Enterprise Learning Equipment

The Dell PowerEdge R710, Dell SC1435 and Cisco Catalyst 3560 switches are used for learning and testing. They are not treated as always-on production services. They support server hardware learning, iDRAC/out-of-band management concepts, storage controller awareness, boot behaviour, switching practice and CCNA study.

---

## Main Services

The homelab includes or has included the following services:

| Service               | Purpose                                       |
| --------------------- | --------------------------------------------- |
| TrueNAS SCALE         | NAS storage and SMB file sharing              |
| Plex                  | Media server                                  |
| Pi-hole               | DNS filtering                                 |
| AdGuard               | DNS/network filtering learning                |
| WireGuard             | VPN and remote-access concepts                |
| Caddy                 | Reverse proxy concepts                        |
| Uptime Kuma           | Service availability monitoring               |
| Homarr                | Dashboard and service overview                |
| Home Assistant        | Smart home and IoT learning                   |
| Docker-based services | Self-hosted service deployment and management |
| SMB shares            | Network file access                           |

Only public-safe service descriptions are documented. Live URLs, hostnames, ports, DNS records and reverse proxy details are not published.

---

## Network Segmentation

The network is designed with segmentation in mind.

The main segmentation goals are:

* Keep trusted devices separate from less trusted IoT devices.
* Keep infrastructure management access restricted.
* Use a dedicated IoT network for smart home devices.
* Practise VLAN concepts across gateway, switch and access point.
* Understand access ports, trunk ports and tagged/untagged traffic.
* Avoid unnecessary communication between device groups.

The live VLAN IDs, addressing and firewall rules are not published.

---

## Monitoring Approach

Monitoring is used to improve visibility and troubleshooting.

The monitoring setup is intended to help answer questions such as:

* Is a service reachable?
* Is the host online?
* Is the issue affecting one service or multiple services?
* Is the problem likely to be application, storage, network or DNS related?
* Did a service recently become unavailable?

Uptime Kuma and the Raspberry Pi 5 monitoring/kiosk display support this part of the environment.

---

## Storage Approach

Storage is handled by a dedicated NAS rather than being mixed with application hosting.

The storage design supports:

* Centralised file storage.
* Media storage for Plex and related services.
* SMB access from trusted systems.
* Dataset and permissions learning.
* Future snapshot and backup planning.
* Storage health awareness.

A key principle is that redundancy is not the same as backup. Backup planning remains an active improvement area.

---

## Learning Lab

The learning lab includes enterprise server hardware and Cisco switches.

This part of the environment is used to practise:

* Cisco IOS basics.
* VLANs.
* Access and trunk ports.
* Inter-switch links.
* Layer 2 troubleshooting.
* Server boot behaviour.
* Storage controller awareness.
* RAM and hardware configuration.
* iDRAC and legacy management access concepts.
* CCNA-aligned networking practice.

This equipment allows testing and learning without relying only on the active home network.

---

## Troubleshooting Experience

The homelab has provided hands-on troubleshooting experience across multiple areas, including:

* Network access problems.
* Switch management access.
* VLAN and port configuration issues.
* Power instability on small-form-factor systems.
* NAS storage planning and access.
* SMB permissions.
* Service availability.
* DNS-related connectivity issues.
* Legacy enterprise server access.
* iDRAC browser compatibility.
* PERC controller and SAS storage learning.
* RAM configuration and server hardware checks.

These issues are documented as learning opportunities rather than as perfect final configurations.

---

## Public-Safe Topology

A simplified public-safe version of the environment is:

```text
Internet
   |
Router / Gateway
   |
Managed Switch
   |
   |-- NAS Server
   |-- Media Server
   |-- Admin / Monitoring Server
   |-- Download / VPN Server
   |-- Raspberry Pi DNS
   |-- Raspberry Pi Monitoring Display
   |-- Wireless Access Point
   |       |-- Trusted Wi-Fi
   |       |-- IoT Wi-Fi
   |
   |-- Enterprise Learning Lab
           |-- Dell Servers
           |-- Cisco Switching Lab
```

This diagram intentionally excludes live IP addresses, VLAN IDs, management interfaces, hostnames and firewall details.

---

## Skills Demonstrated

This environment demonstrates practical experience with:

* IT infrastructure basics
* Homelab design
* Network segmentation
* Managed switching
* VLAN concepts
* UniFi gateway management
* Cisco switch learning
* TrueNAS SCALE
* NAS and SMB concepts
* Plex media service hosting
* Pi-hole DNS filtering
* Monitoring with Uptime Kuma
* Raspberry Pi services
* Server hardware troubleshooting
* Service separation
* Documentation and change tracking
* Public-safe technical writing

---

## Current Status

The homelab is active and continues to develop.

Current focus areas include:

* Improving documentation.
* Refining network segmentation.
* Building CCNA-aligned lab notes.
* Improving storage and backup planning.
* Expanding monitoring.
* Creating redacted diagrams.
* Keeping the GitHub portfolio safe and employer-friendly.

---

## Future Improvements

Planned or possible improvements include:

* Add a redacted topology diagram.
* Add a redacted rack layout.
* Improve backup strategy documentation.
* Build a service dependency map.
* Add troubleshooting logs for common issues.
* Document CCNA lab scenarios.
* Improve monitoring and alerting.
* Review DNS redundancy options.
* Add public-safe change log templates.
