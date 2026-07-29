# Elastic Agent Enrollment

## Overview

Elastic Agent is the primary endpoint data collection component of the Elastic Stack.

In this SOC Analyst Enterprise Lab, Elastic Agents were installed on both Windows and Ubuntu endpoints to collect system logs, security events, authentication logs, process activity, and endpoint telemetry for centralized monitoring within Elastic Security.

---

# Objectives

The objectives of deploying Elastic Agents were:

- Collect endpoint telemetry
- Monitor Windows and Linux systems
- Forward security events to Elasticsearch
- Enable centralized visibility
- Support Elastic Defend
- Prepare endpoints for threat detection and investigation

---

# Architecture

```
             Kibana

                |

          Elasticsearch

                |

          Fleet Server

          -----|------

          | |

 Windows Ubuntu

 Elastic Elastic

  Agent Agent
```

---

# Endpoint Enrollment

## Windows Server

The Windows Server was enrolled into Fleet by installing the Elastic Agent using the enrollment command generated within Kibana.

After installation, the endpoint successfully appeared in Fleet as a managed agent.

Collected data included:

- Windows Event Logs
- Security Events
- System Logs
- Process Activity
- Endpoint Telemetry

---

## Ubuntu Server

The Ubuntu Server was enrolled using the Linux installation command provided by Fleet.

After enrollment, the agent successfully connected to Fleet Server and began forwarding Linux system logs.

Collected data included:

- Authentication Logs
- SSH Events
- System Logs
- Process Activity

---

# Fleet Policies

After enrollment, both endpoints were assigned Fleet policies.

Configured integrations included:

- System Integration
- Elastic Defend
- Endpoint Monitoring

Policies ensured consistent data collection across all monitored systems.

---

# Endpoint Health

Fleet was used to monitor:

- Agent Status
- Policy Assignment
- Last Check-in
- Elastic Agent Version
- Endpoint Connectivity

Healthy agents continuously forwarded telemetry to Elasticsearch.

---

# Validation

Enrollment was verified by confirming:

- Agent appeared in Fleet
- Status reported as Healthy
- Policies successfully applied
- Endpoint logs visible in Kibana
- Events searchable using KQL

---

# Challenges Encountered

During endpoint enrollment, several issues were encountered:

- Enrollment token validation
- Agent connectivity
- Fleet communication
- Policy synchronization
- Service restarts

Each issue was resolved by validating configuration settings, checking service status, and confirming network communication.

---

# Screenshots

Store screenshots in:

```
images/
└── endpoint/
    ├── Windows-Agent.png
    ├── Ubuntu-Agent.png
    ├── Fleet-Healthy.png
    ├── Agent-Policies.png
    └── Agent-Details.png
```

---

# Skills Demonstrated

This section demonstrates practical experience with:

- Elastic Agent deployment
- Windows endpoint monitoring
- Linux endpoint monitoring
- Fleet enrollment
- Endpoint management
- Policy assignment
- Telemetry collection
- Troubleshooting agent connectivity

---

# Summary

Elastic Agent enrollment established centralized endpoint visibility across the SOC Analyst Enterprise Lab.

By successfully enrolling Windows and Ubuntu systems into Fleet, the environment was able to collect endpoint telemetry, monitor system activity, support Elastic Defend, and provide the data required for threat detection and incident investigation.