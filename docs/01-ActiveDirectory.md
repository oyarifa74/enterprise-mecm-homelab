# Active Directory Domain Services

## Project Overview

The first component deployed in the Enterprise MECM Homelab was Active Directory Domain Services (AD DS). This server acts as the identity provider for the lab and provides centralized authentication, authorization, DNS integration, Group Policy, and computer management.

---

## Objectives

- Install Windows Server 2025
- Configure a static IP address
- Install Active Directory Domain Services
- Promote the server to a Domain Controller
- Create the rolandlab.local forest
- Configure DNS
- Create Organizational Units
- Create Security Groups
- Create Test User Accounts
- Join Windows 11 clients to the domain

---

## Server Information

| Setting | Value |
|----------|-------|
| Server Name | DC01 |
| Operating System | Windows Server 2025 |
| Domain | rolandlab.local |
| NetBIOS | ROLANDLAB |
| IP Address | 10.10.10.1 |
| DNS | 10.10.10.1 |

---

## Roles Installed

- Active Directory Domain Services
- DNS Server
- DHCP Server
- RRAS (later phase)

---

## Organizational Unit Structure

```text
ROLANDLAB.LOCAL

Employees

Finance

HR

IT

Sales

Operations
```

---

## Security Groups

| Group | Purpose |
|--------|----------|
| Finance | Finance Department |
| HR | Human Resources |
| IT | IT Administrators |
| Sales | Sales Department |
| Operations | Operations Team |

---

## Test User Accounts

| Username | Department |
|-----------|------------|
| jfinance | Finance |
| jhr | HR |
| jit | IT |
| jsales | Sales |
| joperations | Operations |

---

## Domain Join

The Windows 11 client (CLIENT01) was successfully joined to the rolandlab.local domain.

Domain logon was verified using domain user accounts.

---

## Validation

The following tests were successfully completed.

- Domain Controller operational
- DNS resolving correctly
- DHCP issuing addresses
- Active Directory Users and Computers accessible
- Domain login successful
- Group Policy applied

---

## PowerShell Commands Used

```powershell
Install-WindowsFeature AD-Domain-Services

Install-ADDSForest

Get-ADUser

Get-ADComputer

Get-ADGroup

Get-ADDomain

Get-ADForest

Get-ADUser -Filter *

Get-ADComputer -Filter *

dcdiag

repadmin /replsummary

nslookup rolandlab.local
```

---

## Screenshots

### Domain Controller

![DC01](../images/dc01.png)

### Active Directory Users and Computers

![ADUC](../images/ad-users.png)

### Domain Join

![CLIENT01](../images/client-domain.png)

---

## Skills Demonstrated

- Active Directory Administration
- DNS Configuration
- DHCP Configuration
- Organizational Unit Design
- Security Group Management
- Windows Authentication
- Domain Administration

## Network Configuration

| Component | Value |
|----------|-------|
| Domain Name | rolandlab.local |
| Domain Controller | DC01 |
| IP Address | 10.10.10.1 |
| Subnet Mask | 255.255.255.0 |
| DNS Server | 10.10.10.1 |
| DHCP Scope | 10.10.10.0/24 |


## Deployment Process

The following high level steps were completed to deploy Active Directory:

1. Installed Windows Server 2025.
2. Assigned a static IPv4 address.
3. Installed the Active Directory Domain Services role.
4. Promoted the server to the first domain controller.
5. Created the **rolandlab.local** forest.
6. Verified DNS functionality.
7. Created Organizational Units.
8. Created Security Groups.
9. Created test user accounts.
10. Joined CLIENT01 to the domain.

## Lessons Learned

During the deployment of Active Directory, several important concepts became clear.

* DNS is critical for a healthy Active Directory environment.
* Using Organizational Units makes Group Policy management much easier.
* Security Groups simplify permission management.
* Proper IP planning prevents many deployment issues later in the project.

## References

* Microsoft Learn
* Windows Server 2025 Documentation
* Microsoft Configuration Manager Documentation