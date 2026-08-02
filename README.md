# Enterprise Windows and MECM Home Lab

## Project Overview

This repository documents the design, implementation, administration, and troubleshooting of an enterprise-style Windows infrastructure home lab built with Microsoft Hyper-V.

The environment was created to develop practical System Administrator skills in Windows Server, Active Directory, networking, file services, SQL Server, Microsoft Configuration Manager, PowerShell, and infrastructure automation.

The project is maintained as a living technical portfolio. New documentation, scripts, diagrams, screenshots, and automation will be added as the lab continues to expand.

---

## Project Objectives

The primary objectives of this home lab are to:

- Build and manage a Windows domain environment
- Configure centralized identity and access management
- Administer DNS and DHCP services
- Manage Windows workstations through Group Policy
- Configure enterprise file shares and permissions
- Deploy Microsoft Configuration Manager
- Install and manage Configuration Manager clients
- Troubleshoot infrastructure, networking, authentication, and deployment issues
- Automate administrative tasks with PowerShell
- Introduce Infrastructure as Code and configuration management
- Document technical work using Git and GitHub

---

## Lab Architecture
## Architecture Diagram

![Enterprise MECM Home Lab Architecture]
(docs/diagrams/enterprise-mecm-homelab-architecture.png)

The environment is hosted on a Windows computer running Microsoft Hyper-V.

```text
Home Router
192.168.4.1
     |
     |
DC01 External Interface
192.168.4.10
     |
     | Routing and NAT
     |
DC01 Internal Interface
10.10.10.1
     |
     | 10.10.10.0/24 Lab Network
     |
     +---------------------------------------------------+
     |                    |                 |             |
   DC01                 MECM01            FS01        CLIENT01
10.10.10.1          10.10.10.106        Server       10.10.10.102