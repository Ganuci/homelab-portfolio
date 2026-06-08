# Uptime Kuma Monitoring

## Project Summary

This project documents the monitoring setup used in my homelab to check service availability and improve troubleshooting.

Uptime Kuma is used to monitor selected services and infrastructure endpoints. The goal is to make service status easier to see, reduce guesswork during troubleshooting and build practical experience with monitoring concepts used in IT support and infrastructure environments.

This documentation is public-safe and does not include live IP addresses, hostnames, service URLs, credentials, notification tokens, screenshots with sensitive details or exposed monitoring targets.

---

## Objectives

The main objectives of this project were to:

* Deploy a monitoring tool for key homelab services.
* Track service availability across storage, media, DNS and administration services.
* Build a simple dashboard for visibility.
* Practise troubleshooting using service status information.
* Understand the value of monitoring in infrastructure support.
* Support a kiosk-style monitoring display using a Raspberry Pi.
* Document monitoring decisions in a public-safe way.

---

## Hardware and Services Used

| Component        | Role                                                     |
| ---------------- | -------------------------------------------------------- |
| Admin server     | Hosts or supports monitoring and administration services |
| Raspberry Pi 5   | Monitoring and kiosk display use                         |
| Uptime Kuma      | Service availability monitoring                          |
| Homelab services | Selected services monitored for reachability and uptime  |

---

## Design Approach

The monitoring setup is designed to provide quick visibility of important services.

The wider homelab includes several systems and services, including:

* NAS storage.
* Media services.
* DNS filtering.
* VPN/download workflow.
* Home automation.
* Administration services.

Monitoring helps identify whether a service is reachable before deeper troubleshooting begins. This is useful because it allows issues to be narrowed down more quickly.

For example, if a media service is unavailable, monitoring can help confirm whether the media application itself is down, whether the host is unreachable or whether the issue may be related to storage or network access.

---

## Key Configuration Areas

### Service Checks

Uptime Kuma is used to check selected services. The exact targets are not published, but the monitoring approach includes checking whether important services are reachable.

### Dashboard Visibility

A dashboard gives a quick view of service availability. This supports faster issue identification and helps build operational awareness.

### Kiosk Display

A Raspberry Pi 5 is used for monitoring and kiosk display purposes. This gives a dedicated visual view of service status and supports the wider goal of making the homelab easier to manage.

### Notification Planning

Monitoring can be extended with alerts or notifications. Any notification tokens, webhook URLs or external service details are excluded from public documentation.

---

## Monitoring Approach

The monitoring setup is intended to answer basic operational questions:

* Is the service reachable?
* Is the host online?
* Has a service gone down recently?
* Is the issue affecting one service or multiple services?
* Does the issue point toward application, host, storage or network problems?

This approach supports more structured troubleshooting rather than relying only on manual checking.

---

## Troubleshooting and Learning

This project helped me build experience in several areas:

* Understanding the value of service monitoring.
* Learning how monitoring supports faster troubleshooting.
* Separating service availability from application-level issues.
* Recognising that monitoring should be simple and useful.
* Thinking about dependencies between services.
* Using dashboards to support operational awareness.
* Treating documentation and visibility as part of infrastructure management.

A key learning point is that monitoring does not fix issues by itself, but it improves visibility. It helps confirm what is down, when it changed and where troubleshooting should begin.

---

## Security Considerations

Monitoring can expose sensitive information if documented carelessly. This project avoids publishing:

* Live service URLs.
* Internal IP addresses.
* Hostnames.
* Status pages linked to private systems.
* Notification tokens.
* API keys.
* Screenshots showing targets or device names.
* Management credentials.

The documentation focuses on monitoring concepts, design decisions and troubleshooting value rather than exposing live configuration.

---

## Current Status

Monitoring is part of the active homelab environment and is used to improve visibility across key services.

Current focus areas:

* Expanding monitored services carefully.
* Improving dashboard organisation.
* Reviewing which checks are genuinely useful.
* Considering alerting for important services.
* Using Raspberry Pi 5 for monitoring/kiosk display.
* Documenting monitoring decisions safely.

---

## Skills Demonstrated

This project demonstrates practical experience with:

* Uptime Kuma
* Service availability monitoring
* Dashboard-based visibility
* Raspberry Pi kiosk/display use
* Infrastructure troubleshooting
* Dependency awareness
* Operational thinking
* Public-safe documentation
* Basic monitoring and alerting concepts

---

## Future Improvements

Planned or possible improvements include:

* Create a redacted monitoring diagram.
* Add a public-safe list of monitored service categories.
* Improve alerting for critical services.
* Document a troubleshooting workflow using monitoring data.
* Add a monitoring checklist for new services.
* Review whether DNS, storage and media services should have different priority levels.
