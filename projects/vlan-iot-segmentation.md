# VLAN and IoT Network Segmentation

## Project Summary

This project documents the VLAN and IoT network segmentation work in my homelab.

The goal of this project is to separate less trusted smart home and IoT devices from the main trusted network while maintaining reliable internet access and basic functionality. This gives me practical experience with network segmentation, managed switch configuration, wireless network planning, firewall thinking and troubleshooting connectivity across different parts of a network.

This documentation is public-safe and does not include live IP addresses, VLAN IDs, firewall exports, MAC addresses, device names, screenshots with sensitive details or private network diagrams.

---

## Objectives

The main objectives of this project were to:

* Separate IoT and smart home devices from trusted personal and lab devices.
* Learn how VLANs are planned and applied across a router, managed switch and wireless access point.
* Practise managed switch configuration using a Cisco Business CBS250 switch.
* Use the UniFi Cloud Gateway Max to manage network segmentation and policy.
* Configure a UniFi access point to support a dedicated IoT wireless network.
* Understand the difference between access ports, trunk ports and tagged/untagged traffic.
* Reduce unnecessary access between IoT devices and the rest of the homelab.
* Document the design and troubleshooting process in a safe, employer-friendly format.

---

## Hardware Used

| Component             | Model                          | Role                                                    |
| --------------------- | ------------------------------ | ------------------------------------------------------- |
| Router / Gateway      | UniFi Cloud Gateway Max        | Main gateway, routing, firewall and network control     |
| Managed Switch        | Cisco Business CBS250-8T-D     | Managed switch used for wired devices and VLAN learning |
| Wireless Access Point | UniFi access point             | Provides Wi-Fi and dedicated IoT wireless network       |
| PoE                   | PoE injector                   | Powers the UniFi access point                           |
| IoT Devices           | Smart home devices             | Devices placed on the separated IoT network             |
| Lab Devices           | Servers, NAS and admin systems | Trusted devices kept on the main/lab network            |

---

## Network Design Approach

The network is designed around separating devices by trust level and purpose.

At a high level, the environment includes:

* A trusted network for personal devices, administration and core access.
* A server/lab environment for NAS, media, admin, monitoring and download systems.
* A dedicated IoT network for smart devices.
* A learning lab for enterprise switches and CCNA practice.

The IoT network is treated as less trusted because smart devices often have limited security controls, inconsistent update support and do not usually need access to management interfaces or personal systems.

The segmentation approach is based on a simple principle:

> IoT devices should have the access they need to function, but not unrestricted access to trusted systems.

---

## Public-Safe Topology

The live network details are intentionally not published. The simplified design is:

```text
Internet
   |
UniFi Cloud Gateway Max
   |
Cisco CBS250 Managed Switch
   |
   |-- Trusted devices
   |-- NAS / media / admin systems
   |-- Raspberry Pi services
   |-- UniFi access point
          |
          |-- Main Wi-Fi
          |-- IoT Wi-Fi
```

This diagram does not show IP ranges, VLAN IDs, firewall rules, management URLs or device identifiers.

---

## Key Concepts Practised

### VLAN Planning

VLANs are used to logically separate devices on the same physical network infrastructure. This allows different groups of devices to be treated differently from a security and access-control perspective.

For this project, VLAN planning was used to separate IoT devices from trusted devices and lab systems.

### Access Ports

Access ports are used when a connected device should belong to one network only. For example, a wired device that belongs only to the trusted network can be connected to a port configured for that specific network.

### Trunk Ports

Trunk ports are used when multiple networks need to pass through the same physical connection. The connection between the managed switch and wireless access point needs to support more than one wireless network, so trunking/tagging concepts are relevant.

### Wireless Network Mapping

The UniFi access point is used to broadcast wireless networks. One wireless network is intended for trusted devices and another is intended for IoT devices.

The IoT wireless network is mapped to the separated IoT network so that smart devices do not sit directly on the same network as trusted devices.

### Firewall Thinking

Segmentation alone is not enough. Firewall rules or network policies are needed to control what traffic is allowed between networks.

The intended policy is:

* IoT devices can access the internet where required.
* IoT devices should not have unrestricted access to trusted devices.
* Trusted/admin devices can manage infrastructure where appropriate.
* DNS and DHCP should be allowed as required.
* Management interfaces should not be exposed to IoT devices.

No live firewall rules are published in this repository.

---

## Configuration Areas

### UniFi Cloud Gateway Max

The UniFi gateway is used as the main router and network control point.

Relevant configuration areas include:

* Creating separate networks.
* Managing DHCP behaviour.
* Applying firewall or traffic rules.
* Controlling routing between networks.
* Viewing connected devices.
* Supporting the UniFi access point.

### Cisco Business CBS250-8T-D

The Cisco managed switch is used to connect the wired homelab devices and practise managed switch configuration.

Relevant configuration areas include:

* Port configuration.
* VLAN membership.
* Tagged and untagged traffic.
* Access and trunk-style port behaviour.
* Management access.
* Troubleshooting port connectivity.

### UniFi Access Point

The access point provides wireless connectivity and supports the separated IoT Wi-Fi network.

Relevant configuration areas include:

* Main wireless network.
* IoT wireless network.
* Wireless-to-network mapping.
* AP uplink configuration.
* Client isolation considerations.
* Wi-Fi settings for smart devices.

---

## IoT Network Settings Considered

Smart home devices often work best with simple, stable wireless settings. When planning the IoT network, the following areas were considered:

* Use a dedicated IoT SSID.
* Keep IoT devices separated from trusted devices.
* Prefer 2.4GHz where required by smart devices.
* Avoid overly complex Wi-Fi settings that may break older IoT devices.
* Keep DNS and internet access available where needed.
* Restrict access to management interfaces and trusted devices.
* Keep naming clear so devices are easy to identify later.
* Review devices regularly and remove anything no longer used.

Exact wireless settings, SSID names and network identifiers are not published.

---

## Troubleshooting and Learning

This project helped me practise troubleshooting across several layers:

* Router/gateway network configuration.
* Managed switch port configuration.
* Access point uplink behaviour.
* Wi-Fi network mapping.
* Device connectivity.
* DHCP/DNS availability.
* Tagged and untagged traffic concepts.
* Management access to network devices.
* Understanding how a misconfigured port can cause connectivity issues.

A key learning point was that VLAN configuration needs to be consistent across the gateway, switch and access point. If one part is configured incorrectly, devices may connect to Wi-Fi but fail to receive the correct network access, or a management device may become unreachable.

Another important lesson was to make changes in a controlled way. Network changes can lock devices out or move equipment onto the wrong network, so it is important to document the current state, change one thing at a time and keep a recovery route available.

---

## Security Considerations

This project was designed with basic security principles in mind:

* Separate less trusted IoT devices from trusted systems.
* Limit unnecessary communication between networks.
* Avoid exposing management interfaces to IoT devices.
* Keep admin access restricted to trusted devices.
* Avoid publishing live configuration details.
* Keep diagrams and examples sanitised.
* Review connected devices regularly.

The aim is not to claim enterprise-level security, but to demonstrate practical security awareness and sensible network design for a homelab.

---

## Current Status

The IoT segmentation project is part of the active homelab development.

Current focus areas:

* Refining the IoT network design.
* Reviewing smart device connectivity.
* Testing which devices require local network access.
* Improving documentation of switch and AP configuration decisions.
* Building a redacted topology diagram.
* Continuing CCNA-aligned practice around VLANs, trunks and switching concepts.

---

## Skills Demonstrated

This project demonstrates practical experience with:

* VLAN concepts
* Network segmentation
* IoT isolation
* UniFi gateway configuration
* Cisco managed switch configuration
* Access and trunk port concepts
* Wireless network planning
* DHCP and DNS awareness
* Firewall and traffic-control thinking
* Connectivity troubleshooting
* Public-safe technical documentation
* Infrastructure change planning

---

## Future Improvements

Planned or possible improvements include:

* Create a redacted network topology diagram.
* Document the difference between trusted, lab and IoT networks.
* Add a public-safe switch port role table without IPs or sensitive identifiers.
* Review firewall rules and document the intended policy in plain English.
* Test smart device functionality after segmentation changes.
* Improve monitoring for key network services.
* Add a troubleshooting log for network changes and lessons learned.
