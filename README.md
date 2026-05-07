# 🔍 DFIR Memory & Disk Investigation

## Overview

This project simulates a digital forensic investigation within a controlled lab environment using memory and disk forensic analysis techniques.

The objective is to demonstrate how forensic artifacts can be acquired, analyzed, and correlated to investigate suspicious activity on a compromised Windows system using tools such as Volatility 3 and Autopsy.

---

## Investigation Scenario

The lab simulates a post-compromise investigation involving suspicious activity on a Windows workstation.

The investigation focuses on identifying forensic evidence related to:

- Suspicious process execution  
- PowerShell activity and command execution  
- Persistence mechanisms  
- User activity artifacts  
- Network-related evidence  
- Memory and filesystem artifacts  

The analysis is performed from a defensive and forensic perspective without focusing on offensive exploitation techniques.

Detailed investigation steps and findings are documented in the `phases/` directory.

---

## Workflow

The project is organized into the following phases:

1. Environment Setup  
2. Incident Simulation  
3. Evidence Acquisition  
4. Memory Forensics Analysis  
5. Disk Forensics Analysis  
6. Final DFIR Report  

Each phase documents both the technical workflow and the investigative reasoning behind the analysis process.

---

## Lab Architecture

The environment consists of two virtual machines:

* **Victim Machine:** Windows 10  
* **Analyst Workstation:** Ubuntu Linux  

### Network Configuration

* NAT (internet access and package installation)

---

## What You Will Find in `phases/`

* Lab environment preparation and configuration  
* Simulated suspicious activity generation  
* Memory acquisition and forensic evidence handling  
* Volatility 3 memory analysis workflow  
* Autopsy disk artifact investigation  
* IOC identification and event reconstruction  
* Final forensic investigation report with findings and conclusions  

---

## Key Skills Demonstrated

* Digital Forensics and Incident Response (DFIR)  
* Memory forensics analysis  
* Disk and filesystem artifact investigation  
* Evidence acquisition and handling  
* Suspicious activity identification  
* Timeline and event reconstruction  
* Technical investigation documentation  

---

## Tools Used

* Volatility 3  
* Autopsy  
* WinPmem  
* Windows 10  
* Ubuntu Linux  
* VMware Workstation  

---

## Project Outcome

This project provided practical experience with forensic investigation methodologies in a controlled virtual environment.

It demonstrates how memory and disk artifacts can be analyzed to identify suspicious behavior, reconstruct system activity, and support a structured DFIR investigation process.
