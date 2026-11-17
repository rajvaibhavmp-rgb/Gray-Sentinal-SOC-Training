# Day 01 — Splunk Enterprise Security (ES)

**Training:** Gray Sentinel — SOC Analyst Training  
**Week:** 01  
**Day:** 01  
**Topic:** Splunk ES Architecture & UI Orientation  
**Status:** Completed  
**Date:** 17 November 2026

## 1. What I Studied

On Day 1 of my SOC Analyst training, I explored the Splunk Enterprise Security environment and learned how Splunk is used for security monitoring, log analysis, and investigating security events.

The lab introduced me to the Splunk CLI, REST API, Common Information Model (CIM), data models, and security data inventory.

## 2. Lab Activities and Commands

### Phase 1 — Splunk ES Environment Verification

**Objective:** Verify the Splunk platform status, license, installed applications, and configured indexes.

Commands covered:

```bash
splunk status
splunk show license
splunk display app
splunk list index
```

**Observations:**
- Splunk Enterprise Security 8.6.0 was reported as present.
- The platform health check and license verification returned successful results.
- I explored how to identify installed applications and configured indexes.

**What I learned:** How to check Splunk platform health and inspect its configuration before beginning security investigations.

### Phase 2 — Splunk REST API and CIM Discovery

**Objective:** Explore Splunk's management REST API and identify installed applications and CIM data models.

REST API endpoints explored:

```text
https://localhost:8089/services/apps/local
https://localhost:8089/services/data/models
```

The lab used `curl` to query these endpoints with JSON output.

**What I learned:** How the Splunk REST API can retrieve information about installed applications and available data models.

### Phase 3 — CIM Data Model Verification

**Objective:** Explore the Authentication and Endpoint Processes data models.

Searches covered:

```spl
| datamodel Authentication Authentication search
| stats count
```

```spl
| datamodel Endpoint Processes search
| stats count
```

**Observations:**
- The Authentication data model returned a populated count.
- The Endpoint Processes data model returned a successful response.

**What I learned:** CIM provides a standardized structure for security data and helps analysts perform consistent searches across different data sources.

### Phase 4 — Security Data Inventory

**Objective:** Examine indexed events, Windows Security logs, and internal Splunk data.

Searches covered:

```spl
| tstats count where index=* by index
```

```spl
index=windows sourcetype=WinEventLog:Security
| stats count
```

```spl
index=_internal
| stats count by sourcetype
```

**What I learned:** How to examine event counts, identify available data sources, and assess whether security data is being ingested.

### Phase 5 — Data Flow and Knowledge Assessment

**Objective:** Review the Splunk data flow, complete the safety notice, and verify understanding through a quiz.

**Activities:**
- Reviewed the data flow documentation.
- Reviewed the safety notice.
- Completed the Day 1 knowledge assessment.

**Result:** Passed all 7 quiz questions.

## 3. Key Learning Outcomes

Through this lab, I developed an introductory understanding of:

1. Splunk Enterprise Security architecture and environment verification.
2. Using Splunk CLI commands to inspect platform configuration.
3. Querying Splunk REST API endpoints.
4. Understanding CIM data models.
5. Exploring Authentication and Endpoint Processes data.
6. Checking indexes and security event availability.
7. The importance of verifying data ingestion before security analysis.

## 4. Day 1 Completion Certificate

I successfully completed the Day 1 — Splunk Enterprise Security (ES) lab as part of my Gray Sentinel SOC Analyst Training.

**Achievement:**
- Completed the Day 1 training activities.
- Passed all 7 knowledge assessment questions.
- Received my Day 1 completion certificate.

**Certificate:** [View Day 1 Certificate](Day-01-Certificate.png)

This certificate serves as proof of my Day 1 training completion.
## 5. My Day 1 Reflection

Day 1 helped me understand the basic components of Splunk Enterprise Security and how security analysts can use the platform to inspect logs, verify data availability, and explore security data models.

This lab gave me a foundation for future hands-on SOC investigations and security monitoring exercises.

## 6. Conclusion

I completed the Day 1 Splunk Enterprise Security training lab and passed the knowledge assessment with 7 out of 7 correct answers.

I will continue documenting my learning, practical activities, and observations throughout the 8-week SOC Analyst training program.
