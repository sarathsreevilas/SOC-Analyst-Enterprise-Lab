# Elastic Defend Configuration

## Overview

Elastic Defend is the Endpoint Detection and Response (EDR) solution within the Elastic Security platform. It provides continuous endpoint monitoring, malware detection, behavioral analysis, and threat prevention across managed systems.

In this SOC Analyst Enterprise Lab, Elastic Defend was deployed on the Windows endpoint through Fleet Server. It monitored endpoint activity, generated security telemetry, and detected malicious behavior during attack simulations performed using Mythic C2.

---

# Objectives

The primary objectives of deploying Elastic Defend were to:

- Protect Windows endpoints
- Monitor endpoint activity in real time
- Detect malicious behavior
- Generate security alerts
- Support incident investigation
- Validate detection capabilities through attack simulation

---

# Architecture

```
SOC Analyst

      |

   Kibana

      |

Elastic Security

      |

Fleet Server

      |

Elastic Agent

      |

Elastic Defend

      |

Windows Endpoint
```

Elastic Defend operates as part of the Elastic Agent and sends endpoint telemetry directly to Elasticsearch for analysis.

---

# Deployment Process

Elastic Defend was enabled by adding the Elastic Defend integration to the Fleet policy assigned to the Windows endpoint.

Deployment included:

- Installing Elastic Agent
- Enrolling the endpoint into Fleet
- Assigning the appropriate policy
- Adding the Elastic Defend integration
- Verifying endpoint health
- Confirming telemetry collection

After deployment, the endpoint appeared as **Healthy** in Fleet and began reporting endpoint events to Elastic Security.

---

# Endpoint Monitoring

Elastic Defend continuously monitored endpoint activity, including:

- Process creation
- Command execution
- File operations
- Network connections
- User logons
- Registry activity
- Security events

This telemetry provided visibility into normal system behavior as well as suspicious activity generated during attack simulations.

---

# Malware Detection

A Mythic C2 payload was executed on the monitored Windows endpoint to validate Elastic Defend's detection capabilities.

During execution:

- The endpoint generated security telemetry.
- Elastic Defend detected the malicious activity.
- A security alert was created in Kibana.
- The event was available for investigation within Elastic Security.

This demonstrated that endpoint protection and detection were functioning correctly.

---

# Alert Investigation

After the alert was generated, the following investigation activities were performed:

- Reviewed alert details
- Examined affected host
- Identified the triggering process
- Investigated endpoint events
- Reviewed related telemetry
- Validated the detection rule
- Confirmed malicious activity

These steps simulated the workflow of a Security Operations Center (SOC) analyst investigating a potential endpoint compromise.

---

# Integration with Mythic C2

The attack simulation included:

- Payload generation
- Payload execution
- Successful callback to the Mythic C2 server
- Post-exploitation commands such as `whoami` and `ipconfig`

Elastic Defend successfully monitored the endpoint activity throughout the simulation, demonstrating its ability to detect and record malicious behavior for further investigation.

---

# Troubleshooting

Several issues were encountered during deployment and testing.

## Agent Communication

Issue:

The endpoint was temporarily unable to communicate with Fleet Server.

Resolution:

- Verified Fleet Server status
- Confirmed network connectivity
- Restarted the Elastic Agent service
- Validated policy synchronization

---

## Detection Validation

Issue:

Detection rules did not immediately generate alerts during initial testing.

Resolution:

- Confirmed Elastic Defend was enabled
- Verified endpoint telemetry collection
- Executed additional attack simulations
- Reviewed detection rule configuration

---

# Screenshots

Store related screenshots in:

```
images/
└── elastic-defend/
    ├── Elastic-Defend-Policy.png
    ├── Endpoint-Healthy.png
    ├── Malware-Alert.png
    ├── Alert-Details.png
    ├── Process-Tree.png
    └── Endpoint-Events.png
```

---

# Skills Demonstrated

This section demonstrates experience with:

- Endpoint Detection and Response (EDR)
- Elastic Defend deployment
- Fleet policy management
- Endpoint monitoring
- Malware detection
- Security alert analysis
- Threat investigation
- Incident response
- Endpoint telemetry analysis

---

# Summary

Elastic Defend provided enterprise-grade endpoint protection throughout the SOC Analyst Enterprise Lab.

By integrating Elastic Defend with Fleet Server and Elastic Security, the environm