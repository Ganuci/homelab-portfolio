# Homelab Infrastructure Portfolio

This repository documents my personal homelab, built to develop practical skills in IT support, infrastructure, networking, storage, virtualisation, monitoring, self-hosting and troubleshooting.

The purpose of this lab is to create a hands-on environment where I can configure real systems, troubleshoot technical issues, document changes and build confidence with technologies used in IT Support, Technical Support, Desktop Support and Junior Infrastructure roles.

This repository is written in a public-safe way and does not include live IP addresses, credentials, VLAN IDs, hostnames, firewall exports, domain records, MAC addresses, serial numbers or unredacted screenshots.

---

## Current Environment

### Core Network

| Component             | Model                        | Purpose                                                 |
| --------------------- | ---------------------------- | ------------------------------------------------------- |
| Router / Gateway      | UniFi Cloud Gateway Max      | Main router, firewall and network management            |
| Managed Switch        | Cisco Business CBS250-8T-D   | Wired connectivity, VLAN learning and switch management |
| Wireless Access Point | UniFi AP via PoE injector    | Wi-Fi and IoT network separation                        |
| Learning Switches     | Cisco Catalyst 3560 switches | CCNA switching practice and lab testing                 |

### Server Roles

| Role               | Hardware                                                | Purpose                                    |
| ------------------ | ------------------------------------------------------- | ------------------------------------------ |
| NAS                | Lenovo M720Q                                            | TrueNAS storage server                     |
| Media              | Lenovo M720Q                                            | Plex and media applications                |
| Admin              | Lenovo M920X                                            | Services, monitoring and administration    |
| Download / VPN     | Lenovo M700                                             | VPN-protected download workflow            |
| Monitoring / Kiosk | Raspberry Pi 5                                          | Monitoring display and dashboard use       |
| DNS                | Raspberry Pi 4                                          | Pi-hole DNS filtering                      |
| Enterprise Lab     | Dell PowerEdge R710 / Dell SC1435 / Cisco 3560 switches | Testing, server learning and CCNA practice |

---

## Projects

* [TrueNAS NAS Build](projects/truenas-nas-build.md)
* [VLAN and IoT Network Segmentation](projects/vlan-iot-segmentation.md)
* [Cisco CCNA Switching Lab](projects/cisco-ccna-switching-lab.md)
* [Plex Media Server](projects/plex-media-server.md)
* [Pi-hole DNS Filtering](projects/pi-hole-dns.md)
* [Uptime Kuma Monitoring](projects/uptime-kuma-monitoring.md)
* [VPN Download Server](projects/vpn-download-server.md)

---

## Documentation

* [Homelab Environment Overview](docs/environment-overview.md)
* [Security and Redaction Approach](docs/security-and-redaction.md)

---

## Diagrams and Architecture

* [Redacted Homelab Topology](diagrams/topology-redacted.md)
* [Service Dependency Map](diagrams/service-dependency-map.md)

---

## Key Technologies

* UniFi networking
* Cisco managed switching
* VLAN planning and IoT network segmentation
* Proxmox
* TrueNAS SCALE
* Docker-based services
* Plex
* Pi-hole
* AdGuard
* WireGuard
* Caddy reverse proxy concepts
* Uptime Kuma
* Homarr
* Home Assistant
* SMB file sharing
* Raspberry Pi services
* Server hardware troubleshooting
* CCNA switching practice

---

## Key Learning Areas

This homelab is used to practise and document:

* IT infrastructure fundamentals
* User-focused troubleshooting
* Network segmentation and VLAN design
* Managed switch configuration
* Router, switch and access point integration
* NAS storage planning
* SMB shares and storage access
* DNS filtering and name resolution
* Self-hosted service deployment
* VPN and remote-access concepts
* Monitoring and service availability
* Server hardware troubleshooting
* Service dependency mapping
* Documentation and change control
* Public-safe technical writing

---

## What This Demonstrates

This portfolio demonstrates:

* Practical troubleshooting across hardware, network, storage and service layers.
* Ability to document technical systems clearly and safely.
* Hands-on exposure to technologies used in IT support and junior infrastructure roles.
* Understanding of network segmentation, monitoring, service availability and service dependencies.
* A structured approach to learning, testing and improving technical systems.

---

## Security and Redaction

This repository is public-safe.

It does not publish:

* Live IP addresses
* VLAN IDs from the active environment
* Public IP addresses
* Usernames or passwords
* API keys or tokens
* SSH or VPN keys
* Internal hostnames
* Domain records
* Firewall rule exports
* Full router, switch, TrueNAS, Proxmox or Docker configuration backups
* MAC addresses
* Serial numbers
* Management URLs
* Unredacted screenshots
* Logs showing private activity

For more detail, see: [Security and Redaction Approach](docs/security-and-redaction.md)

---

## Repository Status

This repository is actively being developed. Current documentation covers the main homelab environment, storage, networking, DNS, monitoring, media services, VPN/download workflow and public-safe architecture notes.

Future updates may include redacted diagrams, troubleshooting logs, change logs, backup planning notes and additional CCNA lab scenarios.
