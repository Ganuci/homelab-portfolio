# TrueNAS NAS Build

## Project Summary

This project documents the NAS server used in my homelab for storage, file sharing and infrastructure learning.

The NAS is built on a Lenovo M720Q and runs TrueNAS SCALE. The purpose of this system is to provide centralised storage for the lab while giving me hands-on experience with NAS planning, storage layout, SMB shares, permissions, storage troubleshooting and service separation.

This documentation is public-safe and does not include live IP addresses, credentials, serial numbers, MAC addresses, private share names or screenshots containing sensitive information.

---

## Objectives

The main objectives of this project were to:

* Build a dedicated NAS system for the homelab.
* Learn how TrueNAS SCALE is installed, configured and managed.
* Understand the difference between system storage and data storage.
* Practise managing disks, pools, datasets and SMB shares.
* Provide storage for media and other lab services.
* Keep storage services separate from application hosting where possible.
* Document configuration decisions and troubleshooting steps in a structured way.

---

## Hardware Used

| Component      | Specification                            |
| -------------- | ---------------------------------------- |
| System         | Lenovo M720Q                             |
| CPU            | Intel Core i5-8400T, 6 cores             |
| RAM            | 32GB                                     |
| System Storage | 2 × 250GB SSD                            |
| Data Storage   | 2 × 6TB HDD + 2 × 3TB HDD                |
| Power          | 135W adapter + Enhance ENP-7145 450W PSU |
| Role           | TrueNAS storage server                   |

The Lenovo M720Q was chosen because it is compact, relatively power-efficient and suitable for a small homelab NAS build. The additional PSU setup supports the extra storage requirements beyond the normal small-form-factor configuration.

---

## Software Used

| Software      | Purpose                                     |
| ------------- | ------------------------------------------- |
| TrueNAS SCALE | NAS operating system and storage management |
| SMB           | File sharing across the network             |
| Web UI        | Storage administration and monitoring       |
| ZFS concepts  | Pool, dataset and storage planning          |

---

## Design Approach

The NAS is designed as a dedicated storage system rather than a general-purpose application server.

The wider homelab separates roles across multiple systems:

* NAS server for storage.
* Media server for Plex and media applications.
* Admin server for monitoring and supporting services.
* Download server for VPN/download workflows.
* Raspberry Pi devices for monitoring display and DNS filtering.

This separation makes the environment easier to understand, troubleshoot and maintain. It also reflects a basic infrastructure principle: storage, compute, networking and application services should be logically separated where practical.

---

## Storage Design

The NAS includes SSD storage for system use and multiple HDDs for data storage.

The storage design is intended to support:

* Centralised file storage.
* Media storage for Plex and related services.
* SMB access from trusted devices.
* Future backup and snapshot planning.
* Testing and learning around ZFS, datasets and permissions.

No live pool names, dataset names, IP addresses or share paths are published in this repository.

---

## Key Configuration Areas

The main configuration areas for this project include:

### TrueNAS SCALE Installation

TrueNAS SCALE was installed as the NAS operating system to provide a dedicated web-managed storage platform. This gave me practical experience with installation, initial setup and basic administration.

### Disk and Pool Planning

The build required identifying available drives, understanding how TrueNAS detects storage and planning how system disks and data disks should be used.

### Dataset Planning

Datasets are used to organise storage logically. This helps separate different types of data and makes it easier to manage permissions, sharing and future backup policies.

### SMB File Sharing

SMB sharing is used to make storage available to other trusted systems on the network. This is useful for media libraries, file access and general homelab storage.

### Permissions

Permissions need to be planned carefully so that services and users can access the data they need without exposing more than necessary. This is an area I continue to develop as part of the lab.

### Service Separation

The NAS is primarily used for storage. Applications such as Plex are kept on a separate media server where practical. This helps reduce complexity and makes troubleshooting easier.

---

## Troubleshooting and Learning

This project helped me build practical experience in several areas:

* Understanding how TrueNAS detects and presents disks.
* Separating boot/system storage from data storage.
* Planning storage around available hardware.
* Thinking about redundancy, backups and snapshots.
* Understanding that RAID/ZFS redundancy is not the same as backup.
* Managing SMB access and permissions.
* Troubleshooting storage access from other devices.
* Documenting storage decisions clearly.

One important lesson from this project is that storage planning should be done carefully before data is added. Changing storage layouts later can be time-consuming, so it is better to plan pools, datasets, shares and backup strategy properly at the start.

---

## Security Considerations

To keep this project safe for public documentation, the following details are not published:

* Internal IP addresses.
* Share paths.
* Usernames.
* Passwords.
* Dataset names used in the live environment.
* Serial numbers.
* MAC addresses.
* Screenshots showing management pages or device identifiers.
* Full configuration exports.

The documentation focuses on design, learning and troubleshooting rather than exposing the live configuration.

---

## Current Status

The NAS is part of the active homelab environment and is used as the dedicated storage server.

Current focus areas:

* Improving dataset organisation.
* Reviewing SMB permissions.
* Planning a clearer backup strategy.
* Documenting storage decisions.
* Improving monitoring of storage health and service availability.

---

## Skills Demonstrated

This project demonstrates practical experience with:

* TrueNAS SCALE
* NAS concepts
* Storage planning
* SSD and HDD role separation
* SMB file sharing
* Permissions awareness
* ZFS concepts
* Infrastructure documentation
* Troubleshooting storage access
* Separating storage and application roles
* Public-safe technical documentation

---

## Future Improvements

Planned or possible improvements include:

* Create a clearer backup plan for important data.
* Document dataset structure in a public-safe way.
* Add storage health monitoring.
* Improve alerting for disk or pool issues.
* Document SMB permission decisions.
* Review snapshot strategy.
* Create a redacted diagram showing how the NAS connects to the wider homelab.
