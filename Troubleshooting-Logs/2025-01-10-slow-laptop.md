Troubleshooting-log-12.md

Issue: Laptop extremely slow after restart.
Impact: High – user unable to work, Teams lagging.

Diagnosis
CPU at 100%
Process: MsMpEng.exe (Windows Defender) running full scan
Disk usage 95%
RAM usage normal

Actions
Paused real-time protection temporarily to reduce CPU spike.
Disabled scheduled scan during business hours.
Ran DISM /RestoreHealth and sfc /scannow – no corruption.
Updated Windows + Defender definitions.

Resolution
Machine stabilized after scan completion → CPU returned to 8%.

Root Cause
Windows Defender full system scan triggered automatically after update.