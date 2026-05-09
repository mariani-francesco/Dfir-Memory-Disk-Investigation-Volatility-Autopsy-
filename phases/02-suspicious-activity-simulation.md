# Phase 02 – Suspicious Activity Simulation

## Objective

The objective of this phase is to simulate suspicious activity on the Windows system in order to generate forensic artifacts for later analysis.

The simulated activity was designed to mimic common post-compromise behavior while remaining fully controlled and benign.

---

## Simulation Scope

The activity performed during this phase focuses on generating forensic evidence commonly associated with suspicious system behavior, including:

- PowerShell execution
- File creation within AppData
- Execution policy bypass
- Persistence through a scheduled task

No real malware or malicious payloads were used during this simulation.

---

## Suspicious File Creation

A directory named `SystemUpdate` was created within the user's AppData roaming profile:

```text
AppData\Roaming\SystemUpdate
```

Within this directory, the following files were created:

- `updater.log`
- `update.ps1`

These files were intentionally placed in a user-accessible AppData location to simulate suspicious post-compromise artifacts often observed during forensic investigations.

---

## PowerShell Activity

A PowerShell script named `update.ps1` was executed using the following command:

```powershell
powershell.exe -ExecutionPolicy Bypass -File "$env:APPDATA\SystemUpdate\update.ps1"
```

The script execution generated process activity and command-line artifacts that will later be analyzed during the memory forensics phase.

The use of `ExecutionPolicy Bypass` was intentionally selected to simulate suspicious PowerShell behavior frequently encountered during incident investigations.

---

## Persistence Mechanism

To simulate persistence behavior, a scheduled task named:

```text
System Update Check
```

was created to execute the PowerShell script during user logon.

This persistence mechanism was added to generate additional forensic artifacts for later analysis.

---

## Conclusion

The Windows system now contains multiple simulated forensic artifacts, including suspicious PowerShell execution, user-level filesystem artifacts, and a persistence mechanism.

These artifacts will be used in the next phases to perform evidence acquisition and forensic analysis using Volatility 3 and Autopsy.
