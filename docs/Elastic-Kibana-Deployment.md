# Elastic & Kibana Deployment

## Overview

This document explains the deployment and configuration of the Elastic Security platform used in the SOC Analyst Enterprise Lab.

Elastic Stack was deployed as the central Security Information and Event Management (SIEM) platform for collecting, storing, analyzing, and investigating security telemetry from Windows and Linux endpoints.

The deployment includes:

- Elasticsearch
- Kibana
- Elastic Security
- Detection Engine
- Dashboards
- Alert Management

---

# Elastic Stack Components

## Elasticsearch

Elasticsearch is the core data storage and search engine of the Elastic Stack.

Responsibilities:

- Receive security telemetry
- Store event data
- Index logs
- Support fast searching and analysis

Data sources include:

- Windows endpoint events
- Linux system logs
- Authentication events
- Endpoint security events
- Detection alerts

---

## Kibana

Kibana provides the visualization and investigation interface for security analysts.

Responsibilities:

- Security monitoring
- Alert investigation
- Dashboard creation
- Log analysis
- Threat hunting using KQL
- Detection rule management

The SOC Analyst accesses Kibana to investigate security events and respond to alerts.

---

## Elastic Security

Elastic Security provides security monitoring and detection capabilities.

Features used in this lab:

- Security Dashboard
- Alerts
- Detection Rules
- Timeline Investigation
- Hosts View
- Endpoint Security
- Threat Hunting

---

# Deployment Architecture

The Elastic environment consists of:

```
                SOC Analyst

                    |

                 Kibana

                    |

              Elasticsearch

                    |

        -----------------------

        | |

 Windows Endpoint Ubuntu Endpoint

        |

 Elastic Agent

```

---

# Installation Process

The Elastic deployment process included:

## Step 1: Server Preparation

A dedicated Vultr virtual machine was prepared for hosting Elastic services.

Configuration included:

- Operating system installation
- Network configuration
- Required package installation
- System updates

---

## Step 2: Elasticsearch Installation

Elasticsearch was installed and configured as the primary data storage engine.

Configuration tasks:

- Service installation
- Service startup
- Network configuration
- Security configuration
- Connectivity testing

---

## Step 3: Kibana Installation

Kibana was installed to provide the web-based security interface.

Configuration tasks:

- Kibana installation
- Elasticsearch connection
- Service configuration
- Web interface access

---

# Network Access

The following services were used:

| Service | Port | Purpose |
|---|---|---|
| Kibana | 5601 | Web interface |
| Elasticsearch | 9200 | API communication |

---

# Elastic Security Configuration

After successful deployment, Elastic Security was configured.

Configuration included:

- Security application access
- Endpoint monitoring preparation
- Detection engine setup
- Alert management
- Dashboard access

---

# Detection Engine

Elastic Detection Engine was used to create and manage security rules.

Capabilities:

- Event analysis
- Suspicious activity detection
- Alert generation
- Investigation workflow

Detection rules were later validated using controlled attack simulations.

---

# Dashboards

Kibana dashboards were used for security visibility.

Dashboard functions:

- Monitor endpoint activity
- Analyze authentication events
- View security alerts
- Investigate suspicious behavior
- Track system activity

---

# Troubleshooting

During deployment, several issues were encountered:

## Kibana Connectivity Issues

Problem:

Unable to access Kibana after configuration changes.

Resolution:

- Verified Elasticsearch status
- Checked Kibana configuration
- Reviewed network connectivity
- Restarted services

---

## Security Configuration Issues

Problem:

Required encryption settings prevented certain integrations.

Resolution:

- Configured required Kibana security settings
- Updated encryption keys
- Restarted Kibana services

---

## Agent Communication Preparation

Before endpoint monitoring, Elastic Agent communication requirements were verified.

Validation included:

- Network connectivity
- Fleet communication readiness
- Endpoint accessibility

---

# Screenshots

Screenshots related to Elastic deployment are stored in:

```
images/
└── elastic/
    ├── Elasticsearch.png
    ├── Kibana.png
    ├── Security-Dashboard.png
    └── Detection-Engine.png
```

---

# Skills Demonstrated

Through this deployment, practical experience was gained in:

- SIEM deployment
- Elasticsearch administration
- Kibana configuration
- Security monitoring
- Detection management
- Dashboard analysis
- Log investigation

---

# Summary

The Elastic and Kibana deployment established the central monitoring platform for the SOC Analyst Enterprise Lab.

This SIEM foundation enabled endpoint visibility, threat detection, alert generation, investigation workflows, and integration with additional security components including Fleet Server, Elastic Defend, Mythic C2, and osTicket.
