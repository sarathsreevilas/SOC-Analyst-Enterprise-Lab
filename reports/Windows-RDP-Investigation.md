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
