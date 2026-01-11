# Mini SOC / Incident Response Lab (Ubuntu)

## Overview
This project simulates a **Mini Security Operations Center (SOC)** workflow on an Ubuntu Linux system.  
The goal is to demonstrate the ability to **detect, analyse, and report security incidents** using real system logs, Linux command-line tools, and SQL-based analysis.

All activity was generated in a **controlled local lab environment** (Ubuntu 24.04 LTS running in VirtualBox).

---

## Objectives
- Simulate benign attack activity (authentication failures, privilege misuse)
- Collect and preserve Linux authentication logs
- Perform triage using Linux CLI tools (`grep`, `awk`)
- Import and analyse logs using SQLite (SIEM-style querying)
- Produce a concise incident report mapped to the **NIST Cybersecurity Framework**

---

## Lab Environment
- **Operating System:** Ubuntu 24.04 LTS (Server)
- **Virtualisation:** Oracle VirtualBox
- **Access:** SSH from host machine
- **Logs Analysed:** `/var/log/auth.log`
- **Tools Used:**
  - Linux CLI (`grep`, `awk`, `tail`)
  - Python (log parsing)
  - SQLite3
  - Git & GitHub

---

## Simulated Activity
The following benign activities were generated to create realistic security events:

- Repeated **failed SSH login attempts** using an invalid user  
- Failed `sudo` authentication attempts  
- User and group management events (baseline system activity)

These activities produced authentication-related log entries commonly investigated by SOC analysts.

---

## Analysis Workflow

### 1. Log Collection & Preservation
- Authentication logs were copied into the project directory
- SHA-256 hashes were generated to demonstrate evidence integrity

### 2. CLI-Based Triage
- Extracted failed SSH attempts
- Identified authentication-related events
- Built a basic event timeline using `grep` and `awk`

### 3. SQL Analysis
- Parsed `auth.log` into CSV format
- Imported logs into SQLite
- Queried for:
  - Total authentication events
  - Failed SSH login attempts

**Key Result:**  
- **22 failed SSH authentication attempts** detected via SQL queries

---

## Incident Report
A 1-page incident report was produced summarising:
- What happened
- Supporting evidence
- Impact assessment
- Security recommendations mapped to **NIST CSF**

**Report:** `report/incident_report.md`

---

## Key Skills Demonstrated
- Linux log analysis and triage
- Understanding of authentication-based attacks
- SQL querying for security investigations
- Evidence handling and integrity concepts
- Incident documentation and reporting
- Familiarity with SOC workflows and NIST CSF

---

## Notes
This project is intended as a **portfolio demonstration** of SOC / Incident Response fundamentals and does not represent a real security breach or production system.

---

## Author
**Gurparsaad Singh**  
Bachelor of Computer Science  
Aspiring SOC / Cybersecurity Analyst

