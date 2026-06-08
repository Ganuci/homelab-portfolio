# VPN Download Server

## Project Summary

This project documents the dedicated download server used in my homelab.

The server runs on a Lenovo M700 and is used for VPN-protected download workflows. The purpose of this system is to keep download-related activity separate from the NAS, media server, admin server and core network services while giving me practical experience with VPN concepts, service isolation, storage paths, monitoring and troubleshooting.

This documentation is public-safe and does not include live IP addresses, VPN provider details, credentials, download sources, private paths, usernames, hostnames, logs, exposed service URLs or configuration files.

---

## Objectives

The main objectives of this project were to:

* Build a dedicated system for download-related workflows.
* Keep download services separate from storage, media and administration systems.
* Practise VPN-protected service operation.
* Understand how VPN connectivity affects applications and network access.
* Improve troubleshooting across application, VPN, DNS, storage and network layers.
* Reduce unnecessary risk by isolating this workload from core systems.
* Document the setup in a safe and employer-friendly way.

---

## Hardware Used

| Component | Specification                |
| --------- | ---------------------------- |
| System    | Lenovo M700                  |
| CPU       | Intel Core i5-6400T, 4 cores |
| RAM       | 8GB                          |
| Storage   | 250GB SSD                    |
| Power     | 65W adapter                  |
| Role      | VPN and download workflow    |

The Lenovo M700 was chosen because it is compact, low-power and suitable for running a dedicated workload without using the NAS or media server directly.

---

## Design Approach

The download server is designed as a separated workload.

The wider homelab separates systems by role:

* NAS server for storage.
* Media server for Plex and media applications.
* Admin server for monitoring and administration.
* Download server for VPN-protected download workflows.
* Raspberry Pi devices for DNS filtering and monitoring display.

This separation helps make the environment easier to manage and troubleshoot. If there is an issue with downloads or VPN connectivity, it can be investigated on the dedicated download server without immediately affecting the NAS, media server or DNS services.

---

## Key Configuration Areas

### VPN-Protected Workflow

The server is used to practise VPN-related concepts, including how applications behave when traffic is routed through a VPN.

Key learning areas include:

* Understanding VPN dependency.
* Checking whether the VPN connection is active.
* Understanding how DNS can behave differently when a VPN is involved.
* Troubleshooting application connectivity through a VPN.
* Separating VPN-protected traffic from other services.

No VPN configuration files, provider details, credentials or endpoint information are published.

### Service Isolation

The download workflow is kept on a dedicated system rather than running directly on the NAS or media server.

This helps reduce complexity and makes it easier to understand which system is responsible for which function.

### Storage Relationship

The download server may interact with storage, but private paths, share names and dataset details are not published.

This helped me practise the relationship between:

* Application server.
* Storage server.
* Permissions.
* Network access.
* File movement or availability.

### Monitoring

The server can be monitored as part of the wider homelab to confirm whether the host and relevant services are reachable.

---

## Troubleshooting and Learning

This project helped me practise troubleshooting across several areas:

* Checking whether a service issue is caused by the application, VPN, DNS or network connectivity.
* Understanding that VPN failures can make a service appear broken even when the application is running.
* Separating download workflows from storage and media services.
* Thinking about service dependencies.
* Understanding why role separation makes troubleshooting easier.
* Checking service availability using monitoring tools.
* Documenting a sensitive workflow without exposing private details.

A key learning point is that VPN-dependent systems need clear monitoring and troubleshooting steps. If the VPN connection fails, the service may behave differently even though the host is still online.

---

## Security Considerations

This project is documented carefully because VPN and download workflows can expose sensitive details if published incorrectly.

The following information is not published:

* VPN provider details.
* VPN configuration files.
* VPN endpoints.
* Usernames or passwords.
* Download sources.
* Download history.
* Logs.
* Private storage paths.
* Internal IP addresses.
* Hostnames.
* Service URLs.
* API keys or tokens.
* Screenshots showing live configuration.

The documentation focuses on system design, separation, VPN dependency awareness and troubleshooting approach.

---

## Current Status

The download server is part of the homelab environment and is used as a dedicated system for VPN-protected download workflows.

Current focus areas:

* Keeping the workload separated from core services.
* Improving monitoring and visibility.
* Reviewing storage access and permissions.
* Documenting troubleshooting steps safely.
* Ensuring public documentation does not expose sensitive details.

---

## Skills Demonstrated

This project demonstrates practical experience with:

* Dedicated service hosting
* VPN concepts
* Workload separation
* Network dependency awareness
* DNS and connectivity troubleshooting
* Storage access awareness
* Monitoring and availability checks
* Service isolation
* Public-safe documentation

---

## Future Improvements

Planned or possible improvements include:

* Add a public-safe service dependency map.
* Improve monitoring for VPN-dependent services.
* Document a generic troubleshooting checklist.
* Review storage access permissions.
* Improve recovery steps for VPN or service failures.
* Add a redacted diagram showing the download server’s role in the wider homelab.
