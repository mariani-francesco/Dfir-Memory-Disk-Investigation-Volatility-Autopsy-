# Phase 06 – Final DFIR Report

## Executive Summary

This project simulated a controlled DFIR investigation involving suspicious PowerShell-based activity on a Windows system.

The investigation included memory acquisition, memory forensic analysis, and disk artifact analysis using WinPmem, Volatility 3, and Autopsy.

The analysis confirmed the presence of PowerShell activity in memory and identified related disk artifacts stored under the user's AppData directory.

---

## Investigation Scope

The scope of this investigation included:

- A Windows 10 system used as the system under investigation
- Memory acquisition using WinPmem
- Memory analysis using Volatility 3
- Disk analysis using Autopsy
- Correlation between volatile and persistent artifacts

The investigation focused on defensive analysis and forensic artifact interpretation.

---

## Evidence Acquired

A full memory image was acquired from the Windows system using WinPmem.

Memory image:

```text
C:\Evidence\memory.raw
```

The memory image was validated using SHA256 hashing to support evidence integrity.

Disk analysis was later performed by importing the Windows virtual disk into Autopsy as a full disk data source.

---

## Memory Analysis Summary

Memory analysis was performed using Volatility 3.

The analysis focused on identifying process activity, process relationships, command-line artifacts, and residual process evidence.

Key Volatility plugins used:

```text
windows.info
windows.pslist
windows.pstree
windows.cmdline
windows.psscan
```

The memory analysis identified:

- `powershell.exe` activity in memory
- associated console activity through `conhost.exe`
- WinPmem execution related to memory acquisition
- additional browser-related process artifacts recovered through process scanning

These findings confirmed that relevant process activity was present in the memory image at the time of acquisition.

---

## Disk Analysis Summary

Disk analysis was performed using Autopsy by importing the Windows virtual disk as a full disk data source.

The analysis identified a suspicious directory under the user's AppData roaming profile:

```text
Users/fraco/AppData/Roaming/SystemUpdate
```

The directory contained:

```text
update.ps1
updater.log
```

The PowerShell script `update.ps1` contained:

```powershell
Start-Sleep -Seconds 300
```

The file `updater.log` contained simulated text associated with the suspicious activity.

---

## Correlation of Findings

The investigation correlated memory and disk evidence to reconstruct the activity.

Memory findings showed that PowerShell activity was present during acquisition.

Disk findings confirmed that a PowerShell script existed on disk under the user's AppData roaming profile.

Together, these findings support the following sequence:

```text
Suspicious files created in AppData
PowerShell activity observed in memory
PowerShell script confirmed on disk
Memory and disk evidence correlated
```

This demonstrates how volatile and persistent artifacts can be combined during a DFIR investigation.

---

## Investigation Timeline

The investigation findings support the following sequence of events:

1. A suspicious directory (`SystemUpdate`) was created under the user's AppData Roaming path.
2. A PowerShell script (`update.ps1`) was stored within the directory.
3. PowerShell execution activity was identified in memory.
4. Process analysis confirmed PowerShell-related execution context and console activity.
5. Memory acquisition was performed using WinPmem.
6. Disk analysis confirmed the presence of persistent filesystem artifacts related to the simulated activity.

This timeline demonstrates how memory and disk artifacts can be correlated to reconstruct suspicious system activity during a DFIR investigation.

---

## Key Findings

- PowerShell activity was identified in the memory image.
- Process tree analysis showed PowerShell-related execution context.
- Command-line analysis confirmed relevant process execution artifacts.
- Process scanning recovered additional process artifacts from memory.
- Autopsy confirmed the presence of `update.ps1` under the user's AppData directory.
- Disk artifacts supported the memory findings and provided persistent evidence.

---

## Limitations

This investigation was performed in a controlled lab environment.

The suspicious activity was simulated and benign. No real malware or malicious payloads were used.

Timestamp-based conclusions were not treated as primary findings due to limited timestamp visibility during disk artifact review.

---

## Conclusion

The investigation successfully demonstrated a complete DFIR workflow involving evidence acquisition, memory analysis, disk analysis, and correlation of forensic artifacts.

Volatility 3 was used to identify memory-resident process activity, while Autopsy confirmed related file-based artifacts on disk.

The project shows how memory and disk forensics can be used together to investigate suspicious activity in a structured and defensible way.
