<div align="center">

![RegTech Solutions Compliance Gap Analysis Banner](banner.jpg)

# RegTech Solutions — Multi-Framework Compliance Gap Analysis

![Progress](https://img.shields.io/badge/Progress-3%2F4%20Tasks-dbab09) ![PCI DSS](https://img.shields.io/badge/-PCI%20DSS%20v4.0-informational) ![SOC 2](https://img.shields.io/badge/-SOC%202%20Type%20II-informational) ![HIPAA](https://img.shields.io/badge/-HIPAA-informational)

</div>

## Project Brief

> RegTech Solutions provides compliance automation software to clients in healthcare, financial services, and retail payments. Their platform must meet PCI DSS v4.0, SOC 2 Type II, and HIPAA requirements simultaneously. As Compliance Architect, perform gap analysis and create a prioritized remediation roadmap.

| | |
|---|---|
| **Client** | RegTech Solutions |
| **Sector** | Compliance automation software (healthcare, financial services, retail payments) |
| **Scale** | 350 employees |
| **Role** | Compliance Architect |
| **Objective** | Perform a gap analysis and create a prioritized remediation roadmap |
| **Frameworks** | PCI DSS v4.0, SOC 2 Type II, HIPAA |

## About this repository

This repo is a structured, portfolio-style write-up of a multi-framework gap analysis: a realistic (fictional) case study that assesses one platform against three overlapping frameworks at once, turns the failures into prioritized issues, and plans the remediation and the audits that will verify it.

## What's inside

| Page | Contents |
|---|---|
| [🛡️ Controls](01-controls.md) | 15 controls, five per framework, each rated for effectiveness, with a coverage summary |
| [🐞 Issues](02-issues.md) | 5 gaps raised from the assessment, from Critical to Medium |
| [🧭 Treatments](03-treatments.md) | The remediation roadmap: one plan per issue, ordered by target date |
| [🔍 Audits](04-audits.md) | The completed gap analysis plus the verification and external audits that follow |

## How to read this

Each page links to the next through the navigation bar at the bottom: Controls → Issues → Treatments → Audits. That is the order of a gap analysis: assess what exists, record what falls short, plan the fix, then arrange the audits that prove it.

## Methodology at a glance

- **Gap analysis by control:** every control is rated Effective, Partially Effective, Ineffective, or Not Tested, with a written rationale, so the ratings expose the gaps rather than hide them.
- **Three frameworks, one platform:** controls are balanced across PCI DSS v4.0, SOC 2, and HIPAA. Several satisfy more than one framework, which is why the roadmap is built around fixing shared controls first.
- **PCI DSS v4.0 future-dated requirements:** three of the gaps (MFA for all CDE access, automated log review, and the certificate inventory) come from requirements that have been mandatory since 31 March 2025, so they carry the highest urgency.
- **Prioritized roadmap:** treatments are sequenced by target date, starting with the Critical gap, and each has concrete steps, a done condition, and the evidence to retain.
- **Standards referenced:** PCI DSS (`1.2.7`, `4.2.1.1`, `8.4.2`, `10.4.1.1`, `11.3.1`), SOC 2 (`CC6.3`, `CC7.4`, `CC8.1`, `CC9.2`, `A1.3`), and HIPAA (`164.308`, `164.312`)

---

<div align="center">

**[Start with Controls →](01-controls.md)**

</div>
