# Linux SSH Investigation

## Incident Summary

This report documents the investigation of Secure Shell (SSH) authentication events collected from the Ubuntu server within the Enterprise SOC Analyst Lab.

The objective was to validate Linux log collection, monitor SSH authentication activity, investigate successful and failed login attempts, and demonstrate SOC investigation techniques using Elastic Security.

---

# Incident Information

| Field | Value |
|--------|-------|
| Incident Type | Linux SSH Authentication |
| Severity | Low (Lab Activity) |
| Detection Source | Elastic Security |
| Data Source | Ubuntu System Logs |
| Investigation Platform | Kibana |
| Status | Closed |

---

# Objective

The investigation aimed to:

- Monitor SSH authentication events
- Validate Linux log collection
- Review authentication logs
- Identify successful and failed login attempts
- Practice SOC investigation workflows

---

# Investigation Process

The investigation followed these steps:

1. Opened Kibana Discover.
2. Filtered SSH authentication events using KQL.
3. Reviewed successful login events.
4. Reviewed failed authentication attempts.
5. Verified usernames and timestamps.
6. Correlated related events.
7. Documented findings.

---

# Evidence Collected

The following evidence was reviewed:

- SSH authentication events
- Login status
- Username
- Source IP address
- Timestamp
- Hostname
- Authentication method

---

# KQL Queries Used

## All SSH Events

```kql
system.auth.ssh.event:*
```

## Successful SSH Logins

```kql
system.auth.ssh.event:"Accepted"
```

## Failed SSH Logins

```kql
system.auth.ssh.event:"Failed"
```

---

# Investigation Findings

The investigation confirmed:

- Ubuntu logs were successfully collected.
- SSH authentication events were forwarded to Elasticsearch.
- Kibana displayed successful and failed login events.
- Event filtering using KQL functioned correctly.
- The monitoring pipeline operated as expected.

---

# Screenshots

Store screenshots in:

images/ubuntu/

- SSH-Authentication.png
- Successful-Login.png
- Failed-Login.png
- Kibana-Discover.png

---

# Lessons Learned

This investigation provided experience with:

- Linux log analysis
- SSH authentication monitoring
- KQL filtering
- Event investigation
- Evidence collection
- SOC documentation

---

# Conclusion

The Linux SSH investigation successfully validated the collection and analysis of authentication logs from the Ubuntu endpoint.

The exercise demonstrated how Elastic Security can be used to monitor Linux systems, investigate SSH activity, and support enterprise SOC monitoring and incident response workflows.

On Sat, Aug 1, 2026, 12:07 p.m. Sarath Somasekharan <hcahamilton8800@gmail.com> wrote:
# Windows RDP Investigation

## Incident Summary

This report documents the investigation of Remote Desktop Protocol (RDP) authentication activity observed within the Enterprise SOC Analyst Lab.

The objective was to monitor Windows authentication events, validate log collection, investigate RDP activity using Elastic Security, and practice the incident investigation workflow.

---

# Incident Information

| Field | Value |
|--------|-------|
| Incident Type | Windows RDP Authentication |
| Severity | Low (Lab Activity) |
| Detection Source | Elastic Security |
| Data Source | Windows Event Logs |
| Investigation Platform | Kibana |
| Status | Closed |

---

# Objective

The investigation aimed to:

- Monitor RDP authentication events
- Validate Windows log collection
- Review authentication logs
- Analyze login activity
- Practice SOC investigation techniques

---

# Investigation Process

The investigation followed these steps:

1. Reviewed security alerts in Kibana.
2. Filtered Windows authentication events.
3. Identified RDP logon activity.
4. Verified the affected endpoint.
5. Reviewed related Windows Event Logs.
6. Confirmed successful authentication.
7. Documented findings.

---

# Evidence Collected

Evidence reviewed during the investigation included:

- Windows Security Event Logs
- Authentication Events
- Logon Type
- Username
- Source Host
- Timestamp
- Endpoint Details

---

# KQL Queries Used

## Successful Windows Logons

```kql
event.code:4624
```

## Failed Windows Logons

```kql
event.code:4625
```

## RDP Logons

```kql
event.category:authentication AND winlog.event_data.LogonType:10
```

---

# Investigation Findings

The investigation confirmed:

- Windows logs were successfully collected.
- Authentication events were indexed in Elasticsearch.
- Kibana displayed the relevant events.
- RDP activity was visible for analysis.
- The monitoring pipeline functioned correctly.

---

# Screenshots

Store screenshots in:

images/windows/

- RDP-Logon.png
- Authentication-Event.png
- Event-Details.png
- Kibana-Search.png

---

# Lessons Learned

This investigation demonstrated:

- Windows authentication monitoring
- RDP log analysis
- KQL searching
- Event investigation
- Evidence collection
- SOC documentation

---

# Conclusion

The investigation successfully validated the collection and analysis of Windows RDP authentication events.

The exercise demonstrated how Elastic Security can be used to monitor authentication activity, investigate Windows events, and support SOC analyst workflows in a controlled lab environment.
