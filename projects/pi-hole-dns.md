# Pi-hole DNS Filtering

## Project Summary

This project documents the Raspberry Pi used for Pi-hole DNS filtering in my homelab.

The purpose of this system is to provide network-level DNS filtering while helping me understand DNS behaviour, client name resolution, network service dependency and the importance of reliable core services.

This documentation is public-safe and does not include live IP addresses, domain logs, client names, MAC addresses, screenshots with sensitive information, blocklists showing private activity or internal DNS records.

---

## Objectives

The main objectives of this project were to:

* Deploy a dedicated DNS filtering service using Pi-hole.
* Learn how DNS supports day-to-day network functionality.
* Understand the role of DNS in browsing, applications and connected devices.
* Practise managing a small network service on Raspberry Pi hardware.
* Improve awareness of privacy, filtering and network visibility.
* Understand why DNS reliability matters in a homelab.
* Document the service in a safe and employer-friendly way.

---

## Hardware Used

| Component    | Specification                             |
| ------------ | ----------------------------------------- |
| Device       | Raspberry Pi 4                            |
| Role         | Pi-hole DNS filtering                     |
| Network Role | DNS filtering and name resolution support |
| Environment  | Homelab network service                   |

The Raspberry Pi 4 was chosen because it is low-power, reliable for lightweight services and suitable for running a dedicated DNS filtering role.

---

## Software and Services

| Software              | Purpose                                              |
| --------------------- | ---------------------------------------------------- |
| Pi-hole               | DNS filtering and network-level ad/tracker blocking  |
| Web UI                | Service administration and visibility                |
| DNS                   | Name resolution for network clients                  |
| Supporting monitoring | Used to check service availability where appropriate |

---

## Design Approach

Pi-hole is treated as a core network support service because DNS affects most client activity.

The service is kept on a dedicated Raspberry Pi so it can run independently from larger servers. This gives the network a lightweight DNS filtering service without depending on the NAS, media server or admin server.

The design helps me practise:

* Running a lightweight Linux-based network service.
* Understanding DNS dependency.
* Monitoring a small but important service.
* Troubleshooting client connectivity issues linked to DNS.
* Keeping infrastructure roles clearly separated.

---

## DNS Learning

This project helped me understand that DNS is a critical part of user experience. When DNS fails or is misconfigured, users may experience internet or application issues even when the physical network connection is working.

Key learning areas include:

* DNS translates names into addresses.
* DNS issues can look like general internet failure.
* Filtering can improve privacy but must be managed carefully.
* Some devices and services may require allowlisting.
* Reliable DNS configuration is important for network stability.
* DNS should be documented clearly because it affects many devices.

---

## Key Configuration Areas

### Pi-hole Deployment

Pi-hole was deployed on a Raspberry Pi 4 as a dedicated DNS filtering service. This gave me hands-on experience with installing and managing a lightweight network service.

### Client DNS Behaviour

The project helped me understand how devices receive DNS settings and how DNS filtering affects client browsing and application behaviour.

### Filtering and Allowlisting

DNS filtering requires careful management because overly aggressive filtering can break legitimate services. This helped me practise balancing privacy, filtering and usability.

### Monitoring and Availability

Because DNS is important to the wider network, the service should be monitored so that failures can be identified quickly.

---

## Troubleshooting and Learning

This project helped me practise troubleshooting across several areas:

* Checking whether DNS is working when a device appears to have internet issues.
* Understanding the difference between network connectivity and name resolution.
* Reviewing blocked requests when an application or website does not work as expected.
* Allowlisting legitimate services where required.
* Understanding the impact of DNS changes on multiple devices.
* Recognising that small services can have a large effect on user experience.

A key learning point is that DNS should be treated as a core service. If users cannot resolve names, many services will appear broken even when the network itself is connected.

---

## Security and Privacy Considerations

Pi-hole provides visibility into DNS activity, so public documentation must avoid exposing private browsing or device information.

This project does not publish:

* Client names.
* Query logs.
* Internal domains.
* Live IP addresses.
* MAC addresses.
* Blocklist activity linked to private devices.
* Screenshots from the live admin interface.
* Configuration exports.

The documentation focuses on service purpose, DNS learning and troubleshooting approach.

---

## Current Status

The Pi-hole service is part of the active homelab and runs on a dedicated Raspberry Pi 4.

Current focus areas:

* Improving reliability and monitoring.
* Reviewing allowlist requirements.
* Documenting DNS troubleshooting steps.
* Understanding how DNS interacts with IoT devices and segmented networks.
* Keeping the public documentation safe and non-sensitive.

---

## Skills Demonstrated

This project demonstrates practical experience with:

* Raspberry Pi service hosting
* Pi-hole
* DNS concepts
* Network-level filtering
* Basic Linux service management
* Troubleshooting name resolution
* Monitoring core network services
* Privacy-aware documentation
* Public-safe technical writing

---

## Future Improvements

Planned or possible improvements include:

* Add a public-safe DNS troubleshooting checklist.
* Improve monitoring and alerting for DNS availability.
* Document how DNS supports the wider homelab without exposing private details.
* Review redundancy options for DNS.
* Create a sanitised diagram showing Pi-hole’s role in the network.
