# Active Directory Homelab

## Project Overview

This project demonstrates the deployment and administration of a Windows Server Active Directory environment in VMware Workstation.

The environment includes:

- Windows Server 2022 Domain Controller
- Active Directory Domain Services (AD DS)
- DNS Services
- Organizational Units (OUs)
- Security Groups
- User Management
- Shared Folder Permissions
- Domain-Joined Windows 11 Client
- PowerShell Administration

---

## Environment

### Domain Controller

- Hostname: DC01
- Operating System: Windows Server 2022
- Domain: fresno.local

### Client Workstation

- Hostname: CLIENT01
- Operating System: Windows 11 Pro
- Joined to the fresno.local domain

---

## Organizational Structure

HypotheticalCorp

- Users
- Groups
- Computers
- IT

---

## User Accounts Created

- John Smith
- Martha Jones
- Aaron Wilkes
- Desii Drew
- MiKayla Mathis
- IT Admin

---

## Security Groups

### Employees

Members:

- John Smith
- Martha Jones
- Aaron Wilkes
- Desii Drew
- MiKayla Mathis

### Finance

Members:

- Desii Drew

### IT_Admins

Members:

- IT Admin

---

## Shared Resources

### Public Share

Purpose:

Accessible to all Employees group members.

Validation:

- John Smith successfully accessed
- Aaron Wilkes successfully accessed
- Desii Drew successfully accessed

### Finance Share

Purpose:

Restricted to Finance group members.

Validation:

- Desii Drew successfully accessed
- John Smith denied access
- Aaron Wilkes denied access

---

## PowerShell Administration

Commands used:

```powershell
Get-ADUser -Filter *
Get-ADGroupMember Employees
Get-ADGroupMember Finance
Add-ADGroupMember -Identity Employees -Members m.mathis
```

---

## Challenges Encountered

During deployment, several issues were identified and resolved:

- Incorrectly configured share permissions on the CompanyShares parent folder.
- NTFS inheritance conflicts that required restoring inherited permissions.
- Windows 11 local account creation issues during setup that required bypassing Microsoft account enforcement.
- File share access testing that initially produced permission errors until group membership and security settings were validated.
- Verification of Finance group access restrictions to ensure only authorized users could access sensitive resources.

These issues were resolved through troubleshooting, permissions review, Active Directory validation, and user testing.