# Network VPC Setup

## Overview

This document explains the network architecture used for the SOC Analyst Enterprise Lab.

The environment was deployed using Vultr Private Networking to create an isolated internal communication environment between security infrastructure, monitored endpoints, attack systems, and ticket management servers.

The private network allows systems inside the SOC environment to communicate securely while reducing unnecessary exposure to the public Internet.

---

# Network Design

## Cloud Network

Platform:

- Vultr Cloud

Network Type:

- Private Virtual Private Cloud (VPC)

Private Network Range:

```
172.31.0.0/24
```

The private network was used for communication between:

- Elastic & Kibana Server
- Fleet Server
- Windows Endpoint
- Ubuntu Endpoint
- osTicket Server
- Mythic C2 Server

---

# Network Components

## SOC Analyst Workstation

Purpose:

- Access Kibana dashboard
- Monitor alerts
- Perform investigations
- Conduct threat hunting
- Manage Elastic Security

Communication:

```
SOC Analyst Laptop
        |
        |
      Kibana
        |
Elastic Security Platform
```

---

# Elastic & Kibana Communication

The Elastic server acts as the central security monitoring platform.

Responsibilities:

- Receive endpoint telemetry
- Store security events
- Process detection rules
- Generate alerts
- Provide investigation dashboards

Communication flow:

```
Elastic Agents
      |
      |
Elasticsearch
      |
      |
Kibana
```

---

# Fleet Server Communication

Fleet Server manages all Elastic Agents deployed throughout the environment.

Communication flow:

```
Fleet Server

      |
      |
-------------------------
| |
Windows Agent Ubuntu Agent
```

Responsibilities:

- Agent enrollment
- Policy management
- Agent health monitoring
- Configuration management

---

# Endpoint Communication

## Windows Server

Services:

- RDP
- Elastic Agent
- Elastic Defend

Purpose:

- Generate Windows telemetry
- Monitor endpoint activity
- Detect malicious behavior


## Ubuntu Server

Services:

- SSH
- Elastic Agent

Purpose:

- Generate Linux authentication logs
- Monitor system activity
- Support threat hunting

---

# Attack Infrastructure Communication

## Kali Linux

Kali Linux is used as the attacker simulation machine.

Purpose:

- Security testing
- Attack simulation
- Detection validation


## Mythic Command and Control

Mythic C2 is used to simulate attacker command-and-control activity.

Communication:

```
Kali Linux

      |
      |
Mythic C2

      |
      |
Target Endpoint
```

The activity generated during simulations is monitored by Elastic Security.

---

# Ticketing Communication

Security alerts are forwarded from Elastic Security to osTicket using a Webhook Connector.

Flow:

```
Elastic Detection Rule

        |

Kibana Alert

        |

Webhook Connector

        |

osTicket Incident Ticket
```

---

# Required Network Services

| Service | Purpose |
|---|---|
| SSH | Linux administration |
| RDP | Windows administration |
| HTTPS | Kibana access |
| Elastic Agent Communication | Endpoint telemetry |
| Webhook Communication | Alert forwarding |

---

# Security Considerations

Network security practices implemented:

- Private VPC communication
- Limited service exposure
- Controlled administrative access
- Separation of attack and monitoring systems
- Secure endpoint communication

---

# Troubleshooting

Common issues encountered:

- Server-to-server communication failures
- Agent connection problems
- Firewall restrictions
- Incorrect network configuration
- Service accessibility issues

Troubleshooting steps included:

- Checking network connectivity
- Verifying service status
- Reviewing firewall rules
- Validating Elastic Agent communication

---

# Summary

The Vultr VPC network provided the foundation for communication between all SOC components.

The network design enabled centralized monitoring, endpoint visibility, controlled attack simulation, automated alerting, and incident response workflows.
