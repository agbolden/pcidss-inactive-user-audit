# PCI DSS 8.2.6 – Inactive User Account Audit Lab

This lab simulates a real-world PCI DSS 8.2.6 control validation for identifying inactive user accounts in Active Directory. It includes a mock interview, simulated findings with screenshot evidence, and a remediation plan.

---

## 🧠 Mock Interview – Inactive User Accounts

| Question | Response |
|----------|----------|
| How do you identify inactive users in Active Directory? | We audit the `lastLogonTimestamp` and check for accounts with no login activity in the past 90+ days. |
| What tools do you use for this process? | Active Directory Users and Computers (ADUC), PowerShell, and audit documentation. |
| What’s the purpose of this control? | To reduce security risk by disabling unused accounts which could be exploited. |
| What’s your process once an inactive user is found? | Document, verify, notify stakeholders, disable the account, and implement remediation. |

---

## 🔍 Simulated Audit Findings

| Audit Task                                             | Evidence |
|--------------------------------------------------------|----------|
| Created test user in Active Directory                  | ![Screenshot 01](./01_PowerShell_Timestamp.png) |
| Verified general account properties                    | ![Screenshot 02](./02_InactiveUser_Description_Edit.png) |
| Labeled account as inactive with description           | ![Screenshot 03](./03_AD_Attribute_LastLogon_NotSet.png) |
| Reviewed object tab details                            | ![Screenshot 04](./04_AD_Description_Set.png) |
| Inspected lastLogonTimestamp (over 400 days ago)       | ![Screenshot 05](./05_AD_User_Visible.png) |
| Confirmed account is still enabled (violation)         | ![Screenshot 06](./06_User_Disabled_Confirmation.png) |
| Reviewed group membership (still active)               | ![Screenshot 07](./07_Group_Membership_Check.png) |
| Validated password last set date (inactive)            | ![Screenshot 08](./08_Account_Disabled_Confirmation.png) |

---

## ✅ Remediation Plan

1. **Disable Inactive Account:**
   - Account was manually disabled after 400+ days of inactivity.

2. **Documentation:**
   - Description field updated with inactivity status and simulated date.
   - Findings logged and retained for audit trail.

3. **Group Audit Follow-Up:**
   - Membership reviewed; further cleanup planned to remove access.

4. **Password Reset Enforcement:**
   - A policy will be enforced to reset stale credentials if reactivated.

5. **Prevention Control:**
   - Set up automated PowerShell scripts to detect future inactive accounts.

---

## 📁 Lab Summary

- ✅ Simulated real-world inactive user
- ✅ Used PowerShell to calculate timestamp for 400+ days
- ✅ Labeled and documented account in ADUC
- ✅ Collected screenshots for audit proof
- ✅ Wrote and implemented remediation

---

**Built by:** [@trucktotech](https://github.com/agbolden)

**Lab Type:** PCI DSS 8.2.6 Compliance | Active Directory | Manual Audit | Screenshot Evidence



