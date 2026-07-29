 Vultr Cloud Deployment

## Overview

This document explains the cloud infrastructure deployment process for the SOC Analyst Enterprise Lab.

The entire SOC environment was deployed using Vultr Cloud infrastructure. Multiple virtual machines were provisioned to simulate an enterprise environment containing security monitoring servers, endpoints, attack infrastructure, and ticket management systems.

---

# Cloud Platform

## Vultr Cloud

Vultr was selected as the cloud hosting platform for this SOC laboratory because it provides flexible virtual machine deployment, private networking capabilities, and the ability to simulate enterprise infrastructure in a controlled environment.

---

# Infrastructure Design

The lab environment consists of multiple virtual machines with specific roles.

| Server | Purpose |
|---|---|
| Elastic & Kibana Server | SIEM, log storage, visualization, alert management |
| Fleet Server | Centralized Elastic Agent management |
| Windows Server | Endpoint monitoring and security testing |
| Ubuntu Server | Linux endpoint monitoring |
| osTicket Server | Security incident ticket management |
| Mythic C2 Server | Command and Control simulation |
| Kali Linux | Attack simulation |

---

# Virtual Machine Deployment

Each virtual machine was deployed with the required operating system and resources based on its role within the SOC environment.

## Server Roles

### Elastic & Kibana Server

Purpose:

- Hosts Elasticsearch
- Hosts Kibana
- Runs Elastic Security
- Stores security telemetry
- Generates alerts
- Provides dashboards and investigation tools


### Fleet Server

Purpose:

- Manages Elastic Agents
- Controls endpoint policies
- Maintains agent communication
- Provides centralized endpoint management


### Windows Server

Purpose:

- Simulates enterprise workstation/server environment
- Generates Windows security events
- Monitored using Elastic Agent and Elastic Defend


### Ubuntu Server

Purpose:

- Simulates Linux infrastructure
- Generates SSH and system activity logs
- Monitored using Elastic Agent


### osTicket Server

Purpose:

- Provides ticket management workflow
- Receives security alerts through webhook integration


### Mythic C2 Server

Purpose:

- Provides controlled adversary simulation
- Generates endpoint activity
- Validates detection capabilities


### Kali Linux Attack Machine

Purpose:

- Performs security testing
- Simulates attacker behavior
- Validates SOC monitoring capabilities

---

# Network Architecture

The environment uses a private Vultr Virtual Private Cloud (VPC).

Network:

```
172.31.0.0/24
```

The private network allows communication between internal servers while maintaining separation from public traffic.

---

# Deployment Process

The deployment process followed these steps:

1. Created Vultr Cloud account and project environment.
2. Created private VPC network.
3. Provisioned virtual machines.
4. Assigned server roles.
5. Configured operating systems.
6. Configured network communication.
7. Prepared servers for security tool installation.
8. Installed and configured Elastic components.

---

# Security Considerations

During deployment:

- SSH access was configured for Linux systems.
- RDP access was configured for Windows systems.
- Private networking was used for internal communication.
- Firewall rules were configured based on service requirements.
- Credentials were securely managed.

---

# Deployment Challenges

During deployment, several challenges were encountered:

- Server communication issues
- Network configuration troubleshooting
- Service connectivity problems
- Agent communication troubleshooting
- Cloud resource management

These challenges provided practical experience in cloud infrastructure administration and SOC environment deployment.

---

# Screenshots

Screenshots related to this deployment are stored in:

```
images/
└── architecture/
└── infrastructure/
```

---

# Summary

The Vultr cloud deployment provided the foundation for the SOC Analyst Enterprise Lab.

The completed infrastructure enabled centralized security monitoring, endpoint visibility, attack simulation, detection engineering, and incident response workflows using enterprise security technologies.