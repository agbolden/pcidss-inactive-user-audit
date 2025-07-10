# PCI DSS Inactive User Audit (Requirement 8.2.6)

This audit simulates a PCI DSS 4.0.1 Requirement 8.2.6 control test to detect inactive user accounts in Active Directory (AD) that have not been used for over 90 days. The goal is to identify and remediate stale accounts that may pose a security risk.

## 📋 Mock Interview Summary

| Question | Answer |
|----------|--------|
| **What’s the PCI DSS requirement being tested?** | Requirement 8.2.6 — Remove/disable inactive user accounts within 90 days. |
| **What was your audit scope?** | Windows Active Directory environment. Focused on a user account inactive for 400+ days. |
| **What tool did you use to validate inactivity?** | Used PowerShell to simulate lastLogonTimestamp and reviewed AD attributes. |
| **What AD attribute did you check?** | `lastLogonTimestamp` (converted to FileTime format). |
| **What findings did you document?** | User account was still active, had not logged in for 400+ days. Password and group membership were still valid. |
| **What action did you take?** | Account was labeled as inactive, validated, and disabled. |
| **What’s the remediation if this is a real finding?** | Implement AD scripts or use IAM tools to automatically disable stale accounts every 90 days. |

---

## 🖼 Screenshot Evidence

### Screenshot 01 - Created Test User with Simulated Inactivity (400 Days Ago)
![Screenshot 01](screenshots/01_PowerShell_Timestamp.png)

### Screenshot 02 - General AD User Properties
![Screenshot 02](screenshots/02_InactiveUser_Description_Edit.png)

### Screenshot 03 - Account Labeled as Inactive (lastLogonTimestamp not set)
![Screenshot 03](screenshots/03_AD_Attribute_LastLogon_NotSet.png)

### Screenshot 04 - Description Set for Inactive User
![Screenshot 04](screenshots/04_AD_Description_Set.png)

### Screenshot 05 - User Visible in AD Tree
![Screenshot 05](screenshots/05_AD_User_Visible.png)

### Screenshot 06 - Account Still Enabled Before Remediation
![Screenshot 06](screenshots/06_User_Disabled_Confirmation.png)

### Screenshot 07 - Group Membership Review
![Screenshot 07](screenshots/07_Group_Membership_Check.png)

### Screenshot 08 - Account Disabled Confirmation
![Screenshot 08](screenshots/08_Account_Disabled_Confirmation.png)

---

## ✅ Remediation Summary
- Disabled user accounts inactive for 400+ days
- Labeled accounts clearly in AD for auditing trail
- All evidence stored in GitHub with visible screenshots

---

## 🧠 Lessons Learned
> PCI auditors often request a review of `lastLogonTimestamp`. Your ability to simulate, detect, document, and remediate inactive accounts shows you're ready for GRC or IAM analyst responsibilities.

---

**Project by:** [@trucktotech](https://github.com/agbolden)

**Requirement Reference:** [PCI DSS v4.0.1 - 8.2.6](https://docs.prismacloud.io/en/enterprise-edition/policy-compliance/pci-dss-v4-0-1)

**License:** MIT





