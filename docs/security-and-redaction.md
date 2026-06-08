# Security and Redaction Approach

## Purpose

This document explains how this homelab portfolio is written in a public-safe way.

The aim of this repository is to demonstrate infrastructure learning, troubleshooting, documentation and design thinking without exposing sensitive details from my live environment.

A homelab can contain information that would be useful to an attacker if published carelessly. For that reason, this repository focuses on architecture, learning outcomes, troubleshooting approach and project documentation rather than full live configuration.

---

## Public-Safe Documentation Principles

The documentation in this repository follows these principles:

* Explain the purpose of each system without exposing live access details.
* Document design decisions without publishing full configuration exports.
* Show learning and troubleshooting process without revealing private identifiers.
* Use device roles instead of sensitive hostnames where possible.
* Use simplified diagrams rather than exact network maps.
* Avoid publishing information that could help someone target the live environment.
* Keep examples generic, redacted or sanitised.

The goal is to demonstrate practical technical understanding while maintaining sensible security hygiene.

---

## Information Not Published

The following information is intentionally excluded from this repository:

* Public IP addresses.
* Internal IP addresses.
* Subnet ranges.
* Gateway addresses.
* VLAN IDs from the live environment.
* Wi-Fi SSIDs.
* Passwords.
* Usernames.
* API keys.
* SSH keys.
* VPN keys or configuration files.
* Authentication tokens.
* DNS records.
* Reverse proxy hostnames.
* Domain names linked to private services.
* Firewall rule exports.
* Router, switch, TrueNAS, Proxmox or Docker configuration backups.
* MAC addresses.
* Serial numbers.
* Device management URLs.
* Unredacted screenshots from management interfaces.
* Logs containing client names, hostnames, addresses or private activity.
* Share paths or dataset names from the live environment.
* Notification webhook URLs.
* Monitoring targets or live status-page links.

---

## Redaction Approach

When documenting projects, I use one of the following approaches:

### 1. Describe the Concept Instead of the Exact Configuration

For example, instead of publishing a full firewall rule, I describe the intended policy:

* IoT devices should have internet access where required.
* IoT devices should not have unrestricted access to trusted devices.
* Management interfaces should only be reachable from trusted/admin devices.
* DNS and DHCP should be allowed where required.

This demonstrates the design logic without exposing the live implementation.

### 2. Use Roles Instead of Sensitive Names

Instead of publishing real hostnames or device names, documentation uses role-based labels such as:

* Router / Gateway
* Managed Switch
* NAS Server
* Media Server
* Admin Server
* Download / VPN Server
* DNS Server
* Monitoring Display
* Enterprise Learning Lab
* IoT Devices
* Trusted Devices

### 3. Use Sanitised Diagrams

Diagrams are simplified and do not show:

* Live IP addressing.
* VLAN IDs.
* MAC addresses.
* Hostnames.
* Management URLs.
* Firewall rule details.
* Remote access details.

A public-safe diagram should show the general relationship between systems, not the exact live configuration.

### 4. Avoid Configuration Exports

Full configuration exports are not published because they can expose sensitive information even when they appear harmless.

This applies to:

* UniFi gateway backups.
* Cisco switch configuration files.
* TrueNAS configuration exports.
* Proxmox configuration.
* Docker compose files containing environment variables.
* Caddy configuration containing hostnames.
* VPN configuration files.
* Monitoring configuration containing private targets.

Where useful, I may include redacted examples or pseudocode, but not live configuration.

---

## Examples of Safe vs Unsafe Documentation

| Area          | Unsafe Example                                          | Safer Public Example                                        |
| ------------- | ------------------------------------------------------- | ----------------------------------------------------------- |
| IP addressing | Publishing exact internal subnets and gateway addresses | Describing networks as trusted, lab and IoT                 |
| VLANs         | Publishing live VLAN IDs and full switch port maps      | Explaining access/trunk concepts and segmentation goals     |
| Firewall      | Publishing full exported rules                          | Describing intended traffic policy in plain English         |
| DNS           | Publishing internal hostnames and query logs            | Explaining the role of DNS and Pi-hole                      |
| Reverse proxy | Publishing live domains and proxy config                | Explaining reverse proxy concepts and service separation    |
| Monitoring    | Publishing status-page URLs and targets                 | Describing service categories monitored                     |
| Storage       | Publishing private share names and paths                | Explaining NAS role, SMB concepts and permissions awareness |
| Screenshots   | Showing admin dashboards with IPs and device names      | Using cropped, blurred or recreated diagrams                |

---

## Project Documentation Checklist

Before publishing a project page, I check that it does not include:

* [ ] Live IP addresses.
* [ ] Public IP addresses.
* [ ] Subnet ranges.
* [ ] VLAN IDs from the active network.
* [ ] Wi-Fi SSIDs.
* [ ] Usernames or passwords.
* [ ] API keys or tokens.
* [ ] SSH or VPN keys.
* [ ] MAC addresses.
* [ ] Serial numbers.
* [ ] Hostnames or device names that identify the live network.
* [ ] Domain names or reverse proxy URLs.
* [ ] Firewall exports.
* [ ] Full router, switch, NAS, Proxmox or Docker configuration exports.
* [ ] Screenshots showing management pages with sensitive identifiers.
* [ ] Logs showing private activity.
* [ ] Monitoring targets or notification URLs.
* [ ] Share paths or dataset names from the live environment.

---

## Screenshot Guidelines

Screenshots can be useful, but they need to be handled carefully.

Before publishing any screenshot, I check for:

* IP addresses.
* MAC addresses.
* Serial numbers.
* Hostnames.
* Usernames.
* Email addresses.
* Device names.
* Internal URLs.
* Domain names.
* Tokens or secrets.
* QR codes.
* Share names.
* Client lists.
* Connected device lists.
* Logs or activity history.

If a screenshot contains sensitive information, I either redact it properly or recreate the concept as a simplified diagram instead.

---

## Diagram Guidelines

Public diagrams should show the design at a high level.

Good public-safe diagram labels include:

* Internet
* Router / Gateway
* Managed Switch
* Access Point
* Trusted Network
* IoT Network
* NAS Server
* Media Server
* Admin Server
* DNS Filtering
* Monitoring
* Enterprise Learning Lab

Public diagrams should not include:

* Exact addressing.
* Live VLAN IDs.
* Management IPs.
* Real hostnames.
* Device serials.
* Public service URLs.
* Detailed firewall rules.
* VPN endpoint details.

---

## Handling Code and Configuration Examples

Where configuration examples are useful, they should be treated as examples only.

Safe examples may include:

* Generic command examples.
* Redacted configuration snippets.
* Pseudocode.
* Conceptual examples that do not match the live environment.
* Placeholder values such as `[redacted]`, `[example]` or `[lab-only]`.

Unsafe examples include:

* Full exported configuration files.
* Real Docker Compose files with environment variables.
* Caddy files with real hostnames.
* VPN configuration files.
* Firewall rules copied from the live system.
* Switch/router configs copied directly from production equipment.

---

## Why This Matters

Public documentation is useful for learning and employability, but it needs to be balanced with security.

This repository is designed to show:

* Technical curiosity.
* Practical infrastructure experience.
* Troubleshooting ability.
* Documentation discipline.
* Security awareness.
* Professional judgement.

It is not intended to expose the exact live environment.

---

## Current Approach

The current approach is to document each project using:

* Project summary.
* Objectives.
* Hardware and software used.
* Design approach.
* Key concepts practised.
* Troubleshooting and learning.
* Security considerations.
* Current status.
* Skills demonstrated.
* Future improvements.

This format keeps the documentation useful to employers while avoiding unnecessary exposure of sensitive information.

---

## Future Improvements

Planned improvements to the security and redaction approach include:

* Create a reusable public-safe documentation template.
* Add a standard redaction checklist to each project page.
* Build redacted topology diagrams.
* Review existing pages regularly for accidental sensitive information.
* Create example diagrams that show concepts without exposing the live network.
* Keep security notes updated as the homelab grows.
