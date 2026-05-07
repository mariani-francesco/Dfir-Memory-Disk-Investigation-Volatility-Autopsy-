# Phase 01 – Environment Setup

## Objective

The objective of this phase is to prepare a controlled virtual lab environment for a DFIR investigation focused on memory and disk forensic analysis.

This phase covers only the initial environment preparation and baseline configuration.

---

## Lab Environment

The lab was built using VMware Workstation and consists of two virtual machines:

- Windows 10
- Ubuntu Linux

The Windows system will later be used as the machine under investigation, while the Ubuntu machine will be used as the analyst workstation during the forensic analysis phases.

---

## Virtual Machine Configuration

| Machine | Role | CPU | RAM | Disk | Network |
|---|---|---:|---:|---:|---|
| Windows 10 | System under investigation | 2 cores | 5 GB | 60 GB | NAT |
| Ubuntu Linux | Analyst workstation | 2 cores | 4 GB | 30 GB | NAT |

NAT networking was selected to provide internet access for updates and future tool installation while keeping the environment simple and isolated.

---

## Conclusion

The virtual lab environment was successfully prepared using VMware Workstation.

Both virtual machines were configured with NAT networking, providing a controlled foundation for the next phase of the DFIR investigation.
