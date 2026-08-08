## Table of Contents

* [Overview](#overview)
* [Architecture](#architecture)
* [Lab Topology](#lab-topology)
* [Virtual Machines](#virtual-machines)
* [Networking](#networking)
* [Documentation](#documentation)
* [PowerShell Automation](#powershell-automation)
* [Future Roadmap](#future-roadmap)
* [Screenshots](#screenshots)
* [Skills Demonstrated](#skills-demonstrated)

# Enterprise MECM Homelab

Enterprise Microsoft infrastructure built using Hyper-V, Windows Server 2025, SQL Server 2022, Active Directory, DNS, DHCP, RRAS, Group Policy, and Microsoft Configuration Manager (MECM).

Designed, deployed, documented, and managed as a production style learning environment for System Administration and Cloud Infrastructure engineering.

![Windows Server](https://img.shields.io/badge/Windows_Server-2025-0078D4?logo=windows&logoColor=white)

![Hyper-V](https://img.shields.io/badge/Hyper--V-Virtualization-0078D4?logo=microsoft&logoColor=white)

![SQL Server](https://img.shields.io/badge/SQL_Server-2022-CC2927?logo=microsoftsqlserver&logoColor=white)

![MECM](https://img.shields.io/badge/MECM-Current_Branch-107C10)

![PowerShell](https://img.shields.io/badge/PowerShell-5.1-5391FE?logo=powershell)

![GitHub](https://img.shields.io/badge/GitHub-Portfolio-181717?logo=github)

![License](https://img.shields.io/badge/License-MIT-green)

An enterprise Windows infrastructure built entirely in a home lab.

This project demonstrates the deployment and administration of Microsoft enterprise technologies including:

* Active Directory Domain Services
* DNS
* DHCP
* Group Policy
* Hyper V
* RRAS NAT
* SQL Server
* Microsoft Configuration Manager (MECM/SCCM)
* Windows 11 Client Management
* PowerShell Automation

---

## Architecture

![Architecture](images/architecture.png)

---

## Current Environment

| Server | Operating System | Purpose |
|---------|-----------------|----------|
| DC01 | Windows Server 2025 | AD DS, DNS, DHCP, RRAS |
| MECM01 | Windows Server 2025 | SQL Server + MECM |
| FS01 | Windows Server 2022 | File Server |
| CLIENT01 | Windows 11 | Managed Client |

---

## Technologies

* Active Directory
* Group Policy
* DNS
* DHCP
* Hyper V
* SQL Server
* MECM
* Windows Server
* Windows 11
* PowerShell
* Git
* GitHub

---

## Project Status

✅ Active Directory

✅ DNS

✅ DHCP

✅ RRAS

✅ SQL Server

✅ MECM

✅ Client Deployment

⬜ WSUS

⬜ PKI

⬜ Infrastructure as Code

⬜ Intune

⬜ Monitoring

## Documentation

| Document | Description |
|----------|-------------|
| [01 Active Directory](docs/01-ActiveDirectory.md) | Domain deployment |
| [02 DNS](docs/02-DNS.md) | DNS configuration |
| [03 DHCP](docs/03-DHCP.md) | DHCP implementation |
| [04 Group Policy](docs/04-GroupPolicy.md) | GPO configuration |
| [05 Hyper-V](docs/05-HyperV.md) | Virtualization |
| [06 RRAS](docs/06-RRAS.md) | Routing and NAT |
| [07 SQL Server](docs/07-SQLServer.md) | Database services |
| [08 MECM Installation](docs/08-MECMInstallation.md) | Site deployment |
| [09 MECM Client Deployment](docs/09-MECMClientDeployment.md) | Client onboarding |
| [10 Enterprise Troubleshooting](docs/10-Troubleshooting.md) | Operational issues |
| [11 Lessons Learned](docs/11-LessonsLearned.md) | Project reflection |

# Repository Structure
enterprise-mecm-homelab/

README.md

docs/

images/

powershell/

automation/

configs/

scripts/

backups/