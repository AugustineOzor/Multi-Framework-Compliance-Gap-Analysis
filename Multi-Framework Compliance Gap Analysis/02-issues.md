# 🐞 Issues

> 5 gaps raised from the control assessment, ordered by severity. Each traces back to the control that failed.

| # | Title | Category | Severity | Status | Owner | Due Date |
|---|---|---|---|---|---|---|
| 1 | Password-only access into the cardholder data environment for service-desk roles | ![Security Gap](https://img.shields.io/badge/category-Security%20Gap-d73a49) | ![Critical](https://img.shields.io/badge/severity-Critical-b60205) | ![Open](https://img.shields.io/badge/status-Open-d73a49) | Security Engineering Team | 2026-11-13 |
| 2 | CDE audit logs reviewed manually and irregularly instead of by automated mechanisms | ![Technical Debt](https://img.shields.io/badge/category-Technical%20Debt-0366d6) | ![High](https://img.shields.io/badge/severity-High-e36209) | ![Open](https://img.shields.io/badge/status-Open-d73a49) | Security Engineering Team | 2026-12-18 |
| 3 | Healthcare reporting module outside the HIPAA risk analysis and ePHI audit logging | ![Compliance Issue](https://img.shields.io/badge/category-Compliance%20Issue-6f42c1) | ![High](https://img.shields.io/badge/severity-High-e36209) | ![Open](https://img.shields.io/badge/status-Open-d73a49) | Compliance Team | 2027-01-29 |
| 4 | HIPAA training lacks HIPAA-specific content and contractor completion tracking | ![Compliance Issue](https://img.shields.io/badge/category-Compliance%20Issue-6f42c1) | ![Medium](https://img.shields.io/badge/severity-Medium-dbab09) | ![Open](https://img.shields.io/badge/status-Open-d73a49) | People Operations | 2026-12-04 |
| 5 | No central inventory of trusted keys and certificates | ![Process Gap](https://img.shields.io/badge/category-Process%20Gap-e36209) | ![Medium](https://img.shields.io/badge/severity-Medium-dbab09) | ![Open](https://img.shields.io/badge/status-Open-d73a49) | Security Engineering Team | 2027-01-15 |

## 1. Password-only access into the cardholder data environment for service-desk roles

**Category:** ![Security Gap](https://img.shields.io/badge/category-Security%20Gap-d73a49) &nbsp;·&nbsp; **Severity:** ![Critical](https://img.shields.io/badge/severity-Critical-b60205) &nbsp;·&nbsp; **Status:** ![Open](https://img.shields.io/badge/status-Open-d73a49)  
**Owner:** Security Engineering Team &nbsp;·&nbsp; **Due Date:** 2026-11-13

**Description**  
Some service-desk and support roles still reach cardholder data environment systems with a password and no second factor. PCI DSS 8.4.2 requires MFA for all access into the CDE, and that requirement has been mandatory since 31 March 2025. Related control: MFA for All Access into the Cardholder Data Environment (Partially Effective). Scope: identify every role with CDE access, enforce Okta MFA for each, and retain the enforcement policy export as evidence.

---

## 2. CDE audit logs reviewed manually and irregularly instead of by automated mechanisms

**Category:** ![Technical Debt](https://img.shields.io/badge/category-Technical%20Debt-0366d6) &nbsp;·&nbsp; **Severity:** ![High](https://img.shields.io/badge/severity-High-e36209) &nbsp;·&nbsp; **Status:** ![Open](https://img.shields.io/badge/status-Open-d73a49)  
**Owner:** Security Engineering Team &nbsp;·&nbsp; **Due Date:** 2026-12-18

**Description**  
CDE audit logs are collected in the SIEM, but no automated review rules exist, so anomalies depend on someone looking. PCI DSS 10.4.1.1 requires automated mechanisms to perform log reviews, mandatory since 31 March 2025. Related control: Automated Daily Review of CDE Audit Logs (Ineffective). Scope: build detection rules for failed logins, privilege changes, and cardholder data access, route alerts to the on-call engineer, and keep a daily review record.

---

## 3. Healthcare reporting module outside the HIPAA risk analysis and ePHI audit logging

**Category:** ![Compliance Issue](https://img.shields.io/badge/category-Compliance%20Issue-6f42c1) &nbsp;·&nbsp; **Severity:** ![High](https://img.shields.io/badge/severity-High-e36209) &nbsp;·&nbsp; **Status:** ![Open](https://img.shields.io/badge/status-Open-d73a49)  
**Owner:** Compliance Team &nbsp;·&nbsp; **Due Date:** 2027-01-29

**Description**  
The healthcare reporting module was added after the last annual risk analysis, so its ePHI flows have not been assessed, and its export jobs do not write to the audit log. This leaves both HIPAA 164.308(a)(1)(ii)(A) and 164.312(b) unmet for that module and creates a blind spot for bulk extraction of ePHI. Related controls: Annual Enterprise HIPAA Security Risk Analysis (Partially Effective) and Audit Logging of Access to ePHI (Partially Effective).

---

## 4. HIPAA training lacks HIPAA-specific content and contractor completion tracking

**Category:** ![Compliance Issue](https://img.shields.io/badge/category-Compliance%20Issue-6f42c1) &nbsp;·&nbsp; **Severity:** ![Medium](https://img.shields.io/badge/severity-Medium-dbab09) &nbsp;·&nbsp; **Status:** ![Open](https://img.shields.io/badge/status-Open-d73a49)  
**Owner:** People Operations &nbsp;·&nbsp; **Due Date:** 2026-12-04

**Description**  
Current security awareness training covers general topics but not HIPAA-specific content, and completion is not tracked for contractors with ePHI access. This does not satisfy HIPAA 164.308(a)(5)(i). Related control: Annual HIPAA Security Awareness Training with Completion Tracking (Ineffective). Scope: add a HIPAA module, enroll contractors in the learning system, and report completion to managers with escalation for overdue staff.

---

## 5. No central inventory of trusted keys and certificates

**Category:** ![Process Gap](https://img.shields.io/badge/category-Process%20Gap-e36209) &nbsp;·&nbsp; **Severity:** ![Medium](https://img.shields.io/badge/severity-Medium-dbab09) &nbsp;·&nbsp; **Status:** ![Open](https://img.shields.io/badge/status-Open-d73a49)  
**Owner:** Security Engineering Team &nbsp;·&nbsp; **Due Date:** 2027-01-15

**Description**  
Certificates protecting cardholder data in transit are tracked informally by individual engineers, with no central record of owner, expiry, or issuer. PCI DSS 4.2.1.1 requires an inventory of trusted keys and certificates, mandatory since 31 March 2025, and the gap also risks an unnoticed certificate expiry causing an outage. Related control: Central Inventory of Trusted Keys and Certificates (Ineffective).

---


---

<div align="center">

[← Controls](01-controls.md) &nbsp;|&nbsp; [🏠 Home](README.md) &nbsp;|&nbsp; [Treatments →](03-treatments.md)

</div>
