# Mythic C2 Attack Simulation

## Overview

This document describes the adversary simulation performed within the SOC Analyst Enterprise Lab using Mythic Command and Control (C2).

The objective of this exercise was to simulate a real-world attack against a monitored Windows endpoint, validate endpoint visibility, generate security alerts, and investigate the resulting activity using Elastic Security.

The simulation followed a complete attack lifecycle from payload generation to detection and investigation.

---

# Objectives

The objectives of this exercise were to:

- Deploy Mythic C2
- Generate a payload
- Execute the payload on a monitored endpoint
- Establish a successful callback
- Execute post-exploitation commands
- Validate Elastic Defend detections
- Generate security alerts
- Investigate malicious activity
- Validate the SOC monitoring workflow

---

# Lab Components

The attack simulation involved the following systems:

| Component | Purpose |
|------------|---------|
| Kali Linux | Attack workstation |
| Mythic C2 | Command and Control platform |
| Windows Server | Target endpoint |
| Elastic Agent | Endpoint telemetry collection |
| Elastic Defend | Endpoint Detection and Response (EDR) |
| Fleet Server | Agent management |
| Elasticsearch | Event storage |
| Kibana | Alert investigation |
| osTicket | Incident ticket creation |

---

# Attack Workflow

The simulated attack followed these stages:

1. Deploy Mythic C2
2. Generate payload
3. Deliver payload to Windows endpoint
4. Execute payload
5. Establish callback to Mythic C2
6. Execute post-exploitation commands
7. Generate endpoint telemetry
8. Trigger Elastic Defend detection
9. Create Kibana security alert
10. Forward alert through Webhook
11. Create incident ticket in osTicket
12. Investigate the alert

---

# Payload Generation

A payload was generated within Mythic C2 and prepared for execution on the monitored Windows endpoint.

The payload was used exclusively inside the controlled laboratory environment for educational purposes and to validate endpoint monitoring.

---

# Payload Execution

The payload was executed on the Windows endpoint.

After execution:

- Elastic Agent collected endpoint telemetry.
- Elastic Defend monitored process activity.
- The endpoint communicated with the Mythic C2 server.
- Security events were forwarded to Elasticsearch.

---

# Successful Callback

The payload successfully established a callback with the Mythic C2 server.

This confirmed that:

- The payload executed successfully.
- Communication between the endpoint and Mythic C2 was established.
- Post-exploitation commands could be issued.

---

# Post-Exploitation Activity

After the callback was established, several commands were executed to simulate attacker behavior.

Examples included:

- `whoami`
- `ipconfig`

These commands generated endpoint telemetry that was collected and analyzed by Elastic Security.

---

# Elastic Defend Detection

Elastic Defend monitored the endpoint throughout the simulation.

The executed payload generated endpoint events that resulted in a security alert within Kibana.

The alert included:

- Affected host
- Detection time
- Process information
- Alert severity
- Detection rule
- Investigation timeline

---

# Alert Investigation

The generated alert was investigated using Kibana.

Investigation activities included:

- Reviewing alert details
- Examining affected endpoint
- Inspecting process events
- Reviewing related telemetry
- Validating malicious activity
- Confirming detection accuracy

---

# Webhook Integration

Following alert generation:

Elastic Security forwarded the alert to osTicket through a configured Webhook Connector.

This simulated an automated SOC workflow where security detections automatically generate incident tickets for analyst investigation.

---

# MITRE ATT&CK Mapping

The simulated activity aligns with several MITRE ATT&CK techniques, including:

| Technique | Description |
|-----------|-------------|
| Initial Access | Payload execution |
| Command and Scripting Interpreter | Command execution |
| Discovery | System information gathering (`whoami`, `ipconfig`) |
| Command and Control | Mythic callback communication |

---

# Skills Demonstrated

This exercise demonstrates experience with:

- Adversary simulation
- Mythic C2
- Command and Control operations
- Endpoint Detection and Response (EDR)
- Elastic Defend
- Elastic Security
- Threat detection
- Alert investigation
- Incident response
- Threat hunting
- SOC workflows

---

# Screenshots

Store screenshots in:

images/
└── mythic/
    ├── Mythic-Dashboard.png
    ├── Payload-Generation.png
    ├── Callback.png
    ├── Whoami.png
    ├── Ipconfig.png
    ├── Elastic-Alert.png
    ├── Investigation.png
    └── osTicket-Ticket.png

---

# Lessons Learned

This exercise demonstrated how an enterprise SOC detects and investigates endpoint compromise.

It highlighted the importance of centralized logging, endpoint telemetry, detection engineering, and incident response workflows.

The integration of Mythic C2, Elastic Defend, Fleet Server, Kibana, and osTicket provided practical experience with a complete attack-and-detect lifecycle within a controlled environment.

---

# Summary

The Mythic C2 attack simulation successfully validated the monitoring and detection capabilities of the SOC Analyst Enterprise Lab.

The exercise demonstrated an end-to-end workflow beginning with payload generation and execution, followed by endpoint detection, alert generation, automated ticket creation, and incident investigation using enterprise security technologies.
