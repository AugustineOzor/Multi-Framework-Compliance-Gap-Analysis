# 🧭 Treatments (Remediation Roadmap)

> 5 treatment plans, one per issue, sequenced by target date, starting with the Critical MFA gap.

| # | Related Issue | Strategy | Status | Owner | Target Date |
|---|---|---|---|---|---|
| 1 | Password-only access into the cardholder data environment for service-desk roles | ![Mitigate](https://img.shields.io/badge/strategy-Mitigate-0366d6) | ![In Progress](https://img.shields.io/badge/status-In%20Progress-dbab09) | Security Engineering Team | 2026-11-06 |
| 2 | HIPAA training lacks HIPAA-specific content and contractor completion tracking | ![Mitigate](https://img.shields.io/badge/strategy-Mitigate-0366d6) | ![Planned](https://img.shields.io/badge/status-Planned-6a737d) | People Operations | 2026-11-27 |
| 3 | CDE audit logs reviewed manually and irregularly instead of by automated mechanisms | ![Mitigate](https://img.shields.io/badge/strategy-Mitigate-0366d6) | ![Planned](https://img.shields.io/badge/status-Planned-6a737d) | Security Engineering Team | 2026-12-11 |
| 4 | No central inventory of trusted keys and certificates | ![Mitigate](https://img.shields.io/badge/strategy-Mitigate-0366d6) | ![Planned](https://img.shields.io/badge/status-Planned-6a737d) | Security Engineering Team | 2027-01-08 |
| 5 | Healthcare reporting module outside the HIPAA risk analysis and ePHI audit logging | ![Mitigate](https://img.shields.io/badge/strategy-Mitigate-0366d6) | ![Planned](https://img.shields.io/badge/status-Planned-6a737d) | Compliance Team | 2027-01-22 |

## 1. Password-only access into the cardholder data environment for service-desk roles

**Strategy:** ![Mitigate](https://img.shields.io/badge/strategy-Mitigate-0366d6) &nbsp;·&nbsp; **Status:** ![In Progress](https://img.shields.io/badge/status-In%20Progress-dbab09)  
**Owner:** Security Engineering Team &nbsp;·&nbsp; **Target Date:** 2026-11-06

**Plan / Description**  
Export every account and role with access to CDE systems and flag those without MFA. Enroll the flagged service-desk and support roles in Okta Verify with number matching, then switch the CDE application policy to require MFA for all users with no exceptions. Keep the Okta policy export and a before-and-after list of unprotected accounts as evidence, and re-run the account export 30 days later to confirm none have regressed.

---

## 2. HIPAA training lacks HIPAA-specific content and contractor completion tracking

**Strategy:** ![Mitigate](https://img.shields.io/badge/strategy-Mitigate-0366d6) &nbsp;·&nbsp; **Status:** ![Planned](https://img.shields.io/badge/status-Planned-6a737d)  
**Owner:** People Operations &nbsp;·&nbsp; **Target Date:** 2026-11-27

**Plan / Description**  
Commission or write a HIPAA module covering the Privacy and Security Rules, ePHI handling, and breach reporting. Enroll all employees and every contractor with ePHI access in the learning system, set a completion deadline with automatic reminders, and send managers a weekly overdue report. Done when completion is recorded for 100 percent of in-scope staff and contractors, with the completion report retained as evidence.

---

## 3. CDE audit logs reviewed manually and irregularly instead of by automated mechanisms

**Strategy:** ![Mitigate](https://img.shields.io/badge/strategy-Mitigate-0366d6) &nbsp;·&nbsp; **Status:** ![Planned](https://img.shields.io/badge/status-Planned-6a737d)  
**Owner:** Security Engineering Team &nbsp;·&nbsp; **Target Date:** 2026-12-11

**Plan / Description**  
Build SIEM detection rules for failed-login bursts, privilege changes, and access to cardholder data, and route alerts to the on-call engineer with a defined response time. Add a daily review record generated from the SIEM so evidence of review exists for each day. Validate the rules with simulated events before sign-off, and retain the rule set and the first 30 days of review records as evidence for PCI DSS 10.4.1.1.

---

## 4. No central inventory of trusted keys and certificates

**Strategy:** ![Mitigate](https://img.shields.io/badge/strategy-Mitigate-0366d6) &nbsp;·&nbsp; **Status:** ![Planned](https://img.shields.io/badge/status-Planned-6a737d)  
**Owner:** Security Engineering Team &nbsp;·&nbsp; **Target Date:** 2027-01-08

**Plan / Description**  
Scan load balancers, application endpoints, and internal services to discover every certificate protecting cardholder data in transit. Record each one in a central inventory with owner, issuer, expiry date, and the system it protects, and set expiry alerts at 60 and 30 days. Assign a named owner per certificate, review the inventory each quarter, and retain the first inventory export as evidence for PCI DSS 4.2.1.1.

---

## 5. Healthcare reporting module outside the HIPAA risk analysis and ePHI audit logging

**Strategy:** ![Mitigate](https://img.shields.io/badge/strategy-Mitigate-0366d6) &nbsp;·&nbsp; **Status:** ![Planned](https://img.shields.io/badge/status-Planned-6a737d)  
**Owner:** Compliance Team &nbsp;·&nbsp; **Target Date:** 2027-01-22

**Plan / Description**  
Add the healthcare reporting module to the HIPAA risk analysis by mapping its ePHI data flows and rating the risks found. In parallel, have Engineering add audit log writes to the module's export jobs, recording user, timestamp, and record identifier, with a six-year retention setting. Test by running a sample export and confirming it appears in the audit log, then update the risk analysis document and attach both as evidence.

---


---

<div align="center">

[← Issues](02-issues.md) &nbsp;|&nbsp; [🏠 Home](README.md) &nbsp;|&nbsp; [Audits →](04-audits.md)

</div>
