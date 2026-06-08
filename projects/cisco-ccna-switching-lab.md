# Cisco CCNA Switching Lab

## Project Summary

This project documents the Cisco switching lab used in my homelab for networking practice and CCNA-aligned learning.

The lab uses Cisco Catalyst 3560 switches alongside my main homelab network equipment. The purpose is to practise core switching concepts in a controlled environment, including VLANs, access ports, trunk ports, basic switch management, inter-switch links, troubleshooting and command-line configuration.

This equipment is used for testing and learning rather than as the main production network. Public documentation does not include live IP addresses, credentials, MAC addresses, serial numbers, full configuration exports or sensitive network details.

---

## Objectives

The main objectives of this project were to:

* Build hands-on confidence with Cisco switching.
* Practise CCNA-relevant networking concepts.
* Understand the difference between access ports and trunk ports.
* Configure and test VLAN behaviour in a lab environment.
* Learn basic Cisco IOS command-line navigation.
* Practise switch troubleshooting in a safe environment.
* Understand how switch configuration affects connectivity.
* Document networking concepts in a structured and public-safe way.

---

## Hardware Used

| Component              | Model                             | Role                                         |
| ---------------------- | --------------------------------- | -------------------------------------------- |
| Lab Switches           | 4 × Cisco Catalyst 3560           | CCNA switching practice                      |
| Main Gateway           | UniFi Cloud Gateway Max           | Main homelab gateway                         |
| Main Managed Switch    | Cisco Business CBS250-8T-D        | Active homelab switch and comparison point   |
| Test Devices           | Lab clients / servers as needed   | Used to test connectivity and VLAN behaviour |
| Enterprise Lab Servers | Dell PowerEdge R710 / Dell SC1435 | Infrastructure learning and testing          |

---

## Lab Scope

This lab focuses on switching concepts rather than exposing or changing the live homelab configuration.

The Cisco Catalyst 3560 switches are used to practise:

* Basic switch setup.
* Interface configuration.
* VLAN creation and assignment.
* Access port configuration.
* Trunk port concepts.
* Inter-switch links.
* Basic troubleshooting commands.
* Configuration review.
* Understanding how Layer 2 connectivity works.

The lab supports my wider goal of developing practical networking knowledge for IT Support, Technical Support, Junior Infrastructure and future networking-focused roles.

---

## Key Concepts Practised

### Basic Switch Management

The lab gives me practice with Cisco IOS navigation, including moving between user mode, privileged mode and configuration mode.

Key areas include:

* Viewing running configuration.
* Checking interface status.
* Reviewing VLAN information.
* Saving configuration changes.
* Understanding how switch settings affect connected devices.

### VLANs

VLANs are used to separate network traffic logically. In this lab, VLANs are used to practise how devices can be grouped into separate networks even when connected to the same physical switch.

This supports my wider homelab work around IoT segmentation and network separation.

### Access Ports

Access ports are used for end devices that belong to a single network. This is useful for understanding how wired devices are assigned to a specific VLAN.

### Trunk Ports

Trunk ports are used when more than one VLAN needs to pass over the same link. This is important for switch-to-switch links and connections to devices that need to carry multiple networks.

### Inter-Switch Links

Using multiple Cisco switches makes it possible to practise how switches connect to each other and how VLANs can be carried between them.

### Troubleshooting

Troubleshooting practice includes checking:

* Whether interfaces are up or down.
* Whether devices are connected to the expected port.
* Whether the correct VLAN is assigned.
* Whether trunk links are carrying the intended traffic.
* Whether configuration changes have been saved.
* Whether cabling or port state is affecting connectivity.

---

## Example Public-Safe Lab Topology

The live network details are not published. A simplified version of the learning lab is:

```text
Test Device
    |
Cisco 3560 Switch A
    |
Cisco 3560 Switch B
    |
Test Device / Lab Endpoint
```

A wider lab scenario may include:

```text
UniFi Gateway / Main Network
        |
Cisco Business CBS250
        |
Cisco 3560 Lab Switch
        |
Test Devices
```

These diagrams do not show live IP addressing, VLAN IDs, credentials or management details.

---

## Commands and Skills Practised

The lab is used to practise Cisco IOS command areas such as:

```text
show running-config
show vlan brief
show interfaces status
show interfaces trunk
show mac address-table
configure terminal
interface [interface-id]
switchport mode access
switchport access vlan [redacted]
switchport mode trunk
copy running-config startup-config
```

The examples above are shown for learning purposes only. They do not expose live configuration from my network.

---

## Troubleshooting and Learning

This project helped me build confidence in several practical networking areas:

* Understanding that physical link status does not always mean correct network access.
* Learning how VLAN assignment affects where a device sits logically.
* Understanding why trunk links are needed when multiple networks pass between devices.
* Practising a methodical approach to checking interfaces, VLAN membership and configuration.
* Recognising the importance of saving configuration changes.
* Learning how easily incorrect port configuration can cause connectivity problems.
* Building confidence using CLI-based network equipment rather than only web interfaces.

A key lesson from this lab is that network troubleshooting should be structured. Before changing multiple settings, it is better to check physical connectivity, interface state, VLAN membership, trunk configuration and expected device behaviour step by step.

---

## Relationship to the Main Homelab

The Cisco 3560 switches are mainly used for learning and testing. The active homelab uses a UniFi Cloud Gateway Max and Cisco Business CBS250-8T-D managed switch.

This gives me exposure to both:

* Web-managed network equipment used in a small business / homelab environment.
* CLI-based Cisco equipment used for deeper networking practice.

The combination helps me understand concepts from both a practical support perspective and a CCNA study perspective.

---

## Security Considerations

This project is documented in a public-safe way. The following information is not published:

* Live IP addresses.
* VLAN IDs used in the active environment.
* Passwords or usernames.
* Full switch configuration exports.
* MAC addresses.
* Serial numbers.
* Management URLs.
* Screenshots showing sensitive device details.

The focus is on concepts, learning process and troubleshooting approach rather than exposing live configuration.

---

## Current Status

The Cisco switching lab is used for ongoing CCNA-aligned practice and infrastructure learning.

Current focus areas:

* Practising VLAN configuration.
* Practising access and trunk port behaviour.
* Reviewing basic Cisco IOS commands.
* Understanding inter-switch links.
* Improving troubleshooting confidence.
* Documenting lab scenarios in a public-safe way.

---

## Skills Demonstrated

This project demonstrates practical experience with:

* Cisco switching concepts
* CCNA-aligned learning
* VLANs
* Access ports
* Trunk ports
* Inter-switch links
* Cisco IOS command-line basics
* Layer 2 troubleshooting
* Network documentation
* Safe lab separation
* Public-safe technical writing

---

## Future Improvements

Planned or possible improvements include:

* Create a redacted switching lab diagram.
* Document a basic VLAN lab scenario.
* Document an access-port versus trunk-port lab.
* Add a troubleshooting log for common switching mistakes.
* Practise and document Spanning Tree Protocol concepts.
* Practise and document EtherChannel concepts if supported by the lab equipment.
* Build a CCNA study checklist linked to lab activities.
