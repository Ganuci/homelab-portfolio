# Plex Media Server

## Project Summary

This project documents the dedicated media server used in my homelab.

The media server runs on a Lenovo M720Q and is used for Plex and related media applications. The purpose of this system is to separate media/application hosting from the NAS storage server, giving me practical experience with service hosting, storage access, permissions, availability monitoring and troubleshooting.

This documentation is public-safe and does not include live IP addresses, credentials, media library paths, private hostnames, account details, screenshots with sensitive information or exposed service URLs.

---

## Objectives

The main objectives of this project were to:

* Build a dedicated server for Plex and media applications.
* Keep media application hosting separate from NAS storage.
* Practise connecting an application server to centralised storage.
* Learn how media services depend on network, storage and permissions.
* Improve troubleshooting skills across service, storage and network layers.
* Monitor service availability and improve reliability.
* Document configuration decisions in a safe, employer-friendly way.

---

## Hardware Used

| Component | Specification                |
| --------- | ---------------------------- |
| System    | Lenovo M720Q                 |
| CPU       | Intel Core i5-9400T, 6 cores |
| RAM       | 32GB                         |
| Storage   | 250GB SSD                    |
| Power     | 135W adapter                 |
| Role      | Plex and media applications  |

The Lenovo M720Q was chosen because it is compact, efficient and suitable for hosting media services in a small homelab environment.

---

## Software and Services

| Service                       | Purpose                                                  |
| ----------------------------- | -------------------------------------------------------- |
| Plex                          | Media server and library management                      |
| NAS storage access            | Media storage provided by the dedicated NAS              |
| Monitoring tools              | Used to check service availability                       |
| Supporting media applications | Used for media workflow and management where appropriate |

---

## Design Approach

The media server is designed as an application host rather than a storage server.

The wider homelab separates roles across multiple systems:

* NAS server for centralised storage.
* Media server for Plex and related services.
* Admin server for monitoring and supporting services.
* Download server for VPN/download workflows.
* Raspberry Pi devices for monitoring display and DNS filtering.

This separation helps reduce complexity. If there is a media playback issue, I can troubleshoot the media server, storage connection and network path separately rather than treating everything as one combined system.

---

## Storage Access

Media files are stored separately from the Plex application server. The media server accesses the required storage from the NAS.

This design helped me practise:

* Connecting services to network storage.
* Understanding how storage availability affects applications.
* Checking permissions when an application cannot access media.
* Understanding the relationship between server roles.
* Separating application data from media storage.

No private share names, paths or storage identifiers are published.

---

## Key Configuration Areas

### Plex Server Setup

Plex is used to manage and serve media content. The setup helped me understand the practical requirements for running a service that depends on storage, network connectivity and client access.

### Media Library Access

The media server needs reliable access to storage locations. This helped me understand that media issues are not always caused by the application itself; they can also be caused by permissions, storage availability, network connectivity or path changes.

### Service Availability

The media server is monitored as part of the wider homelab. This helps confirm whether the service is reachable and supports a more structured troubleshooting process.

### Role Separation

Keeping Plex on a dedicated media server and storage on a dedicated NAS makes the environment easier to maintain. It also reflects a useful infrastructure principle: services should be separated where practical so issues are easier to isolate.

---

## Troubleshooting and Learning

This project helped me build experience in several areas:

* Installing and managing a media service.
* Understanding application dependency on storage.
* Troubleshooting service availability.
* Checking whether an issue is caused by the service, the network or storage access.
* Understanding permissions and access paths.
* Monitoring uptime and service health.
* Documenting service roles clearly.

A key learning point is that a service can appear to be the problem when the real issue is elsewhere. For example, a media application may fail to show content because of storage access, permissions or network connectivity rather than the application itself.

---

## Security Considerations

This project is documented in a public-safe way. The following information is not published:

* Live IP addresses.
* Plex account details.
* Private media paths.
* Hostnames or exposed URLs.
* Usernames or passwords.
* Screenshots showing management pages.
* API keys or tokens.
* Firewall or reverse proxy configuration exports.

The documentation focuses on system design, role separation, troubleshooting and learning rather than exposing live configuration.

---

## Current Status

The media server is part of the active homelab environment and is used for Plex and media-related services.

Current focus areas:

* Improving service monitoring.
* Reviewing storage access and permissions.
* Keeping media applications separated from NAS storage.
* Documenting common troubleshooting steps.
* Improving reliability and service visibility.

---

## Skills Demonstrated

This project demonstrates practical experience with:

* Plex media server
* Application hosting
* Service troubleshooting
* NAS-backed storage access
* SMB/storage dependency awareness
* Role separation
* Monitoring and availability checks
* User-facing service support
* Public-safe technical documentation

---

## Future Improvements

Planned or possible improvements include:

* Document a public-safe service map showing the relationship between Plex and NAS storage.
* Improve monitoring for media service availability.
* Add a troubleshooting checklist for common media service issues.
* Review backup requirements for application configuration.
* Document service restart and recovery steps in a public-safe way.
