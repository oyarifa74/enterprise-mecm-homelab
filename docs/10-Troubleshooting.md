# Enterprise Troubleshooting Guide

**Project:** Enterprise MECM Homelab

**Author:** Roland Neequaye

**Version:** 1.0

**Last Updated:** August 2026

---

# Overview

This document records the real technical issues encountered during the design, deployment, and configuration of the Enterprise MECM Homelab.

Each issue includes the symptoms, root cause, diagnostic process, resolution, validation, and lessons learned.

The purpose of this guide is to provide a repeatable troubleshooting methodology that can be applied to future Windows infrastructure deployments.

---

# Troubleshooting Methodology

Each issue was investigated using the following process.

1. Identify symptoms
2. Verify infrastructure
3. Collect logs
4. Test connectivity
5. Validate services
6. Apply corrective action
7. Confirm resolution

---

# Issue 1

## MECM Client Push Failed

### Symptoms

* Client installation never started.
* Device remained unmanaged.

### Root Cause

Administrative share (ADMIN$) access failed.

### Diagnostics

```powershell
Test-Path \\CLIENT01\ADMIN$

Test-NetConnection CLIENT01 -Port 445
```

### Resolution

Verified:

* File and Printer Sharing
* Firewall Rules
* ADMIN$
* SMB

### Validation

Client Push completed successfully.

---

# Issue 2

## Error 53

### Symptoms

```
Network path not found
```

### Root Cause

SMB communication unavailable.

### Diagnostics

```powershell
ping CLIENT01

Test-NetConnection CLIENT01 -Port 445
```

### Resolution

Enabled firewall rules.

Verified DNS.

Verified ADMIN$.

---

# Issue 3

## BITS Error

### Error

```
0x80200010
```

### Symptoms

Client download repeatedly failed.

### Root Cause

Internal network had no internet access.

### Resolution

Configured RRAS NAT.

Verified routing.

Verified DHCP gateway.

---

# Issue 4

## DNS Resolution

### Symptoms

Clients unable to locate MECM.

### Resolution

Verified:

```powershell
nslookup mecm01

Resolve-DnsName mecm01

ipconfig /registerdns
```

---

# Issue 5

## Boundary Configuration

### Symptoms

Client assigned incorrectly.

### Resolution

Verified:

* Boundary
* Boundary Group
* Site Assignment

---

# Issue 6

## SQL Prerequisites

### Symptoms

MECM prerequisite warnings.

### Resolution

Validated SQL services and networking before continuing.

---

# Issue 7

## Enhanced HTTP

### Symptoms

Client authentication issues.

### Resolution

Enabled Enhanced HTTP.

Verified Management Point communication.

---

# Issue 8

## WMI

### Symptoms

Remote client management unavailable.

### Resolution

Verified:

* WMI Service
* Firewall Rules
* RPC Connectivity

---

# Common Diagnostic Commands

```powershell
Test-NetConnection

nslookup

Resolve-DnsName

ping

gpupdate /force

gpresult /r

ipconfig /all

route print

Get-Service

Get-VM

Get-VMSwitch

Get-DhcpServerv4Lease

Get-DnsServerZone
```

---

# Lessons Learned

Most infrastructure failures were not caused by MECM.

They originated from:

* Networking
* DNS
* Firewall Rules
* RRAS
* Windows Services

Systematically validating each infrastructure layer greatly reduced troubleshooting time.

---

# Skills Demonstrated

* Enterprise Troubleshooting
* Windows Networking
* MECM Administration
* DNS
* DHCP
* RRAS
* Hyper-V
* SQL Server
* PowerShell
* Root Cause Analysis

---

# References

Microsoft Learn

Configuration Manager Documentation

Windows Server Documentation