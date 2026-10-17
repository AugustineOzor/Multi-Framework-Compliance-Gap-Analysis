# 🛡️ Controls

> 15 controls assessed across PCI DSS v4.0, SOC 2 Type II, and HIPAA. The gap analysis rates each one, so the ratings below show where the platform falls short today.

## Coverage by framework

| Framework | Controls | Effective | Partially Effective | Ineffective | Not Tested |
|---|---|---|---|---|---|
| PCI DSS | 5 | 1 | 2 | 2 | 0 |
| SOC 2 | 5 | 2 | 2 | 0 | 1 |
| HIPAA | 5 | 1 | 2 | 1 | 1 |
| **Total** | **15** | **4** | **6** | **3** | **2** |

## All controls

| # | Control | Framework | Reference | Effectiveness | Frequency |
|---|---|---|---|---|---|
| 1 | Quarterly Internal Vulnerability Scans of the Cardholder Data Environment | PCI DSS | `11.3.1` | ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) | Quarterly |
| 2 | MFA for All Access into the Cardholder Data Environment | PCI DSS | `8.4.2` | ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) | Continuous |
| 3 | Automated Daily Review of CDE Audit Logs | PCI DSS | `10.4.1.1` | ![Ineffective](https://img.shields.io/badge/status-Ineffective-d73a49) | Continuous |
| 4 | Semi-Annual Review of Firewall and Network Security Control Rules | PCI DSS | `1.2.7` | ![Effective](https://img.shields.io/badge/status-Effective-28a745) | Quarterly |
| 5 | Central Inventory of Trusted Keys and Certificates | PCI DSS | `4.2.1.1` | ![Ineffective](https://img.shields.io/badge/status-Ineffective-d73a49) | Quarterly |
| 6 | Quarterly User Access Reviews with Documented Manager Sign-Off | SOC 2 | `CC6.3` | ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) | Quarterly |
| 7 | Incident Response Plan with Annual Tabletop Exercise | SOC 2 | `CC7.4` | ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) | Annual |
| 8 | Annual Security Review of Critical Vendors and Sub-Processors | SOC 2 | `CC9.2` | ![Effective](https://img.shields.io/badge/status-Effective-28a745) | Annual |
| 9 | Peer Review and Approval Before Production Deployment | SOC 2 | `CC8.1` | ![Effective](https://img.shields.io/badge/status-Effective-28a745) | Continuous |
| 10 | Quarterly Restore Test of Production Database Backups | SOC 2 | `A1.3` | ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) | Quarterly |
| 11 | Encryption of ePHI at Rest with Managed Keys | HIPAA | `164.312(a)(2)(iv)` | ![Effective](https://img.shields.io/badge/status-Effective-28a745) | Continuous |
| 12 | Annual Enterprise HIPAA Security Risk Analysis | HIPAA | `164.308(a)(1)(ii)(A)` | ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) | Annual |
| 13 | Annual HIPAA Security Awareness Training with Completion Tracking | HIPAA | `164.308(a)(5)(i)` | ![Ineffective](https://img.shields.io/badge/status-Ineffective-d73a49) | Annual |
| 14 | Audit Logging of Access to ePHI | HIPAA | `164.312(b)` | ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) | Continuous |
| 15 | Signed Business Associate Agreements with Every ePHI Subcontractor | HIPAA | `164.308(b)(1)` | ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) | Annual |

## PCI DSS

### 1. Quarterly Internal Vulnerability Scans of the Cardholder Data Environment

**Reference:** `11.3.1` &nbsp;·&nbsp; **Frequency:** Quarterly  
**Effectiveness:** ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) &nbsp;·&nbsp; **Owner:** Security Engineering Team

**Description**  
Run authenticated internal vulnerability scans of every system in the cardholder data environment each quarter, remediate all high-risk findings, and re-scan until the results come back clean, keeping each scan report as evidence.

**Decision Rationale**  
Rated Partially Effective because scans run on schedule and reports are retained, but the last cycle closed without a clean re-scan for every high-risk finding, so the requirement to rescan until resolved is not consistently met.

---

### 2. MFA for All Access into the Cardholder Data Environment

**Reference:** `8.4.2` &nbsp;·&nbsp; **Frequency:** Continuous  
**Effectiveness:** ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) &nbsp;·&nbsp; **Owner:** Security Engineering Team

**Description**  
Require multi-factor authentication through Okta for every user and administrator access into the cardholder data environment, not only administrative access, with push approvals that use number matching.

**Decision Rationale**  
Rated Partially Effective because MFA is enforced for administrators and engineers, but a gap review found that some service-desk and support roles still reach CDE systems with a password only. v4.0 extends MFA to all access into the CDE, so this is a gap against the new requirement.

---

### 3. Automated Daily Review of CDE Audit Logs

**Reference:** `10.4.1.1` &nbsp;·&nbsp; **Frequency:** Continuous  
**Effectiveness:** ![Ineffective](https://img.shields.io/badge/status-Ineffective-d73a49) &nbsp;·&nbsp; **Owner:** Security Engineering Team

**Description**  
Use automated log analysis in the SIEM to review CDE audit logs for anomalies every day, with alerts for failed logins, privilege changes, and access to cardholder data routed to the on-call security engineer.

**Decision Rationale**  
Rated Ineffective because logs are collected centrally but reviewed manually and irregularly, which does not meet the v4.0 requirement for automated mechanisms to perform log reviews. The current practice cannot reliably detect suspicious activity within a day.

---

### 4. Semi-Annual Review of Firewall and Network Security Control Rules

**Reference:** `1.2.7` &nbsp;·&nbsp; **Frequency:** Quarterly  
**Effectiveness:** ![Effective](https://img.shields.io/badge/status-Effective-28a745) &nbsp;·&nbsp; **Owner:** Network Security Team

**Description**  
Review every firewall and network security control rule set protecting the cardholder data environment each quarter, remove rules with no business justification, and record the reviewer, date, and changes made. This exceeds the six-month interval the requirement sets.

**Decision Rationale**  
Rated Effective because the last two review cycles were completed on schedule with documented sign-off, unused rules were removed, and no rule was found without a recorded business justification.

---

### 5. Central Inventory of Trusted Keys and Certificates

**Reference:** `4.2.1.1` &nbsp;·&nbsp; **Frequency:** Quarterly  
**Effectiveness:** ![Ineffective](https://img.shields.io/badge/status-Ineffective-d73a49) &nbsp;·&nbsp; **Owner:** Security Engineering Team

**Description**  
Maintain a single inventory of every certificate and key used to protect cardholder data in transit, with owner, expiry date, and issuing authority, and review it each quarter to retire expired or unused entries.

**Decision Rationale**  
Rated Ineffective because certificates are tracked informally by individual engineers and no central inventory exists, so the v4.0 requirement to maintain an inventory of trusted keys and certificates is not met and expiry or unknown certificates would go unnoticed.

---

## SOC 2

### 6. Quarterly User Access Reviews with Documented Manager Sign-Off

**Reference:** `CC6.3` &nbsp;·&nbsp; **Frequency:** Quarterly  
**Effectiveness:** ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) &nbsp;·&nbsp; **Owner:** IT Operations

**Description**  
Each quarter, export user and role lists for production infrastructure and every in-scope SaaS application, have each system owner confirm or remove access, and retain the signed review as evidence of removal of access that is no longer needed.

**Decision Rationale**  
Rated Partially Effective because reviews are completed and signed for production cloud infrastructure, but in-scope SaaS applications are not yet covered, so access that is no longer needed could persist outside the reviewed systems.

---

### 7. Incident Response Plan with Annual Tabletop Exercise

**Reference:** `CC7.4` &nbsp;·&nbsp; **Frequency:** Annual  
**Effectiveness:** ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) &nbsp;·&nbsp; **Owner:** Compliance Team

**Description**  
Maintain a documented incident response plan with severity levels, roles, and customer notification steps, and run one tabletop exercise per year, recording the lessons learned and the plan updates that result.

**Decision Rationale**  
Rated Not Tested because the plan is written and approved, but no tabletop exercise has been run against it, so whether the team can execute it under pressure is unconfirmed.

---

### 8. Annual Security Review of Critical Vendors and Sub-Processors

**Reference:** `CC9.2` &nbsp;·&nbsp; **Frequency:** Annual  
**Effectiveness:** ![Effective](https://img.shields.io/badge/status-Effective-28a745) &nbsp;·&nbsp; **Owner:** Vendor Management

**Description**  
Keep a vendor register that tiers every vendor by data access, and review each critical vendor's SOC 2 report, bridge letter, and open exceptions once a year, documenting a decision to continue, remediate, or exit.

**Decision Rationale**  
Rated Effective because the vendor register is complete and the most recent annual cycle produced a documented review and decision for every critical vendor, with no overdue reviews found.

---

### 9. Peer Review and Approval Before Production Deployment

**Reference:** `CC8.1` &nbsp;·&nbsp; **Frequency:** Continuous  
**Effectiveness:** ![Effective](https://img.shields.io/badge/status-Effective-28a745) &nbsp;·&nbsp; **Owner:** DevOps Lead

**Description**  
Require at least one approving review and a passing automated test pipeline before any change merges to the main branch, enforced by repository branch protection rules, with emergency changes logged and reviewed afterward.

**Decision Rationale**  
Rated Effective because branch protection technically blocks merges without review and passing tests, and a sample of recent production changes showed no unreviewed deployments or untracked emergency changes.

---

### 10. Quarterly Restore Test of Production Database Backups

**Reference:** `A1.3` &nbsp;·&nbsp; **Frequency:** Quarterly  
**Effectiveness:** ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) &nbsp;·&nbsp; **Owner:** DevOps Lead

**Description**  
Each quarter, restore the latest production database backup into an isolated environment, confirm the platform starts and data validates against checksums, and record the time taken to restore.

**Decision Rationale**  
Rated Partially Effective because the primary database restore is tested and documented every quarter, but object storage holding customer documents is not yet included, so recovery of that data is unproven.

---

## HIPAA

### 11. Encryption of ePHI at Rest with Managed Keys

**Reference:** `164.312(a)(2)(iv)` &nbsp;·&nbsp; **Frequency:** Continuous  
**Effectiveness:** ![Effective](https://img.shields.io/badge/status-Effective-28a745) &nbsp;·&nbsp; **Owner:** Security Engineering Team

**Description**  
Encrypt all databases and object storage that hold electronic protected health information using AES-256 with keys managed in the cloud key management service, with key rotation enabled and a policy that blocks creation of unencrypted storage.

**Decision Rationale**  
Rated Effective because configuration review confirmed encryption at rest is enabled on every data store holding ePHI, key rotation is on, and the preventive policy has blocked unencrypted resource creation with no exceptions.

---

### 12. Annual Enterprise HIPAA Security Risk Analysis

**Reference:** `164.308(a)(1)(ii)(A)` &nbsp;·&nbsp; **Frequency:** Annual  
**Effectiveness:** ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) &nbsp;·&nbsp; **Owner:** Compliance Team

**Description**  
Perform and document a risk analysis once a year covering every system that creates, receives, maintains, or transmits ePHI, with likelihood and impact ratings, and update it when a new product module or data flow goes live.

**Decision Rationale**  
Rated Partially Effective because an annual risk analysis exists, but it predates the healthcare reporting module added since, so that module's ePHI flows have not been assessed.

---

### 13. Annual HIPAA Security Awareness Training with Completion Tracking

**Reference:** `164.308(a)(5)(i)` &nbsp;·&nbsp; **Frequency:** Annual  
**Effectiveness:** ![Ineffective](https://img.shields.io/badge/status-Ineffective-d73a49) &nbsp;·&nbsp; **Owner:** People Operations

**Description**  
Deliver HIPAA-specific security awareness training to every employee and contractor with access to ePHI at onboarding and once a year, track completion in the learning system, and escalate overdue completions to managers.

**Decision Rationale**  
Rated Ineffective because current training covers general security topics but not HIPAA-specific content, and completion is not tracked for contractors, so the requirement for a security awareness program for the workforce is not met.

---

### 14. Audit Logging of Access to ePHI

**Reference:** `164.312(b)` &nbsp;·&nbsp; **Frequency:** Continuous  
**Effectiveness:** ![Partially Effective](https://img.shields.io/badge/status-Partially%20Effective-dbab09) &nbsp;·&nbsp; **Owner:** Engineering Team

**Description**  
Record every read, export, and change of electronic protected health information, with user, timestamp, and record identifier, retain the logs for six years, and review access reports for unusual patterns each month.

**Decision Rationale**  
Rated Partially Effective because ePHI access in the core application is fully logged and retained, but export jobs in the newer healthcare reporting module do not yet write to the audit log, leaving a blind spot for bulk data extraction.

---

### 15. Signed Business Associate Agreements with Every ePHI Subcontractor

**Reference:** `164.308(b)(1)` &nbsp;·&nbsp; **Frequency:** Annual  
**Effectiveness:** ![Not Tested](https://img.shields.io/badge/status-Not%20Tested-6a737d) &nbsp;·&nbsp; **Owner:** Vendor Management

**Description**  
Hold a signed business associate agreement with every subcontractor that creates, receives, maintains, or transmits ePHI, and review the agreements once a year to confirm required clauses such as breach notification timelines are present.

**Decision Rationale**  
Rated Not Tested because agreements are on file for known subcontractors, but they have never been checked against the required clauses, so it is unconfirmed that each one meets the standard.

---


---

<div align="center">

[← Overview](README.md) &nbsp;|&nbsp; [🏠 Home](README.md) &nbsp;|&nbsp; [Issues →](02-issues.md)

</div>
