# PCI DSS 8.2.6 – Inactive User Account Audit Lab

This lab simulates a real-world PCI DSS 8.2.6 control validation for identifying inactive user accounts in Active Directory. It includes a mock interview, simulated findings, screenshots, and a remediation plan.

---

## 🔍 Mock Interview – Inactive User Accounts

| Question | Response |
|----------|----------|
| How often are inactive user accounts reviewed? | Quarterly |
| What tools or scripts are used? | PowerShell, ADUC |
| Is there a defined threshold for inactivity? | Yes, 90 days |
| What action is taken on inactive accounts? | Accounts are disabled or deleted after 90 days of inactivity |
| How is evidence of the review maintained? | Audit reports and screenshots stored in secured location |

---

## 📋 Audit Findings – Inactive User Account

| Finding | Description |
|---------|-------------|
| **Inactive User Not Disabled** | A test account (`InactiveUser01`) was found with no logon activity in the last 400+ days. This violates the organization’s inactive account policy. |

---

## 🖼️ Screenshot Evidence

### 🔹 Pre-Remediation

- Screenshot1 – User created in ADUC with no logon activity
- Screenshot2 – Confirmed `lastLogonTimestamp` with PowerShell
- Screenshot3 – Account details showing 400+ days inactive

### 🔹 Post-Remediation

- Screenshot4 – User account disabled
- Screenshot5 – Audit trail or note added to user description

---

## 🛠️ Remediation Plan

The inactive account `InactiveUser01` has been disabled as of [Insert Date].

Going forward:

- AD scripts will flag accounts inactive for over 90 days
- Review will be added to quarterly compliance checklist
- All remediations logged in audit tracker

---

## ✅ Requirement Reference

**PCI DSS v4.0 – 8.2.6:** Inactive user accounts are either removed or disabled within 90 days of inactivity.


