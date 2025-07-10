# PCI DSS 8.2.6 – Inactive User Account Audit

This lab simulates a PCI DSS 8.2.6 compliance audit by identifying a user account that has not been used for over 90 days, which violates the requirement for timely account removal or disabling.

---

## 🧠 Mock Interview Table

| Interview Question | Stakeholder Response |
|--------------------|----------------------|
| How often do you review inactive accounts? | Reviews are not currently automated. |
| Do you have a threshold (e.g., 90 days) for disabling unused accounts? | No formal process exists. |
| Who is responsible for account reviews? | System administrator. |
| Is there a tracking method for user last login data? | Not consistently monitored. |

---

## 🔍 Inactive Account Review Summary

| Audit Task | Evidence |
|------------|----------|
| Created test user in Active Directory | ![Screenshot 01](screenshots/01_ADUC_NewInactiveUser_Creation.png) |
| Verified general account properties | ![Screenshot 02](screenshots/02_ADUC_UserAccount_Properties_GeneralTab.png) |
| Labeled account as inactive with description | ![Screenshot 03](screenshots/03_ADUC_UserAccount_Properties_DescriptionField.png) |
| Reviewed object tab details | ![Screenshot 04](screenshots/04_ADUC_UserAccount_ObjectTab.png) |
| Inspected lastLogonTimestamp (over 400 days ago) | ![Screenshot 05](screenshots/05_ADUC_UserAccount_AttributeEditor_LastLogonTimestamp.png) |
| Confirmed account is still enabled (violation) | ![Screenshot 06](screenshots/06_ADUC_UserAccount_EnabledStatus.png) |
| Reviewed group membership (still active) | ![Screenshot 07](screenshots/07_ADUC_UserAccount_GroupMembership.png) |
| Validated password last set date (inactive) | ![Screenshot 08](screenshots/08_ADUC_UserAccount_PasswordLastSet.png) |

---

## 🛠️ Remediation Plan

- Disable or remove user accounts that have not logged in within the last 90 days.
- Implement scheduled PowerShell scripts to audit `lastLogonTimestamp` monthly.
- Add an automated task to alert on accounts exceeding inactivity thresholds.
- Update the internal access review policy to align with PCI DSS 8.2.6.

---

## ✅ Outcome

This lab demonstrates an inactive user account that should have been disabled or removed per PCI DSS 8.2.6. Screenshots and findings reflect a real-world GRC process for compliance audits and remediation documentation.



