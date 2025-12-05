Troubleshooting-log-11.md

Issue: User unable to print to network printer (HP LaserJet Pro M404dn).
User Impact: Moderate – printing delayed for a team of 5.
Environment: Windows 10, HP Universal Print Driver, SMB share printer.

Symptoms
Print jobs stuck in queue
Printer status shows “Offline”
HP Web UI reachable over browser

Actions Taken
Checked printer IP (192.168.1.87) – ping successful.
Restarted Print Spooler service on user machine → no change.
Removed & re-added printer via \\printserver01\Marketing_HP_M404.
Verified driver integrity – updated to latest HP UPD v7.0.1.
Found printer mapped via WSD port instead of TCP/IP.

Resolution
Re-added printer using standard TCP/IP port → printer online, jobs printing normally.

Root Cause
Incorrect port mapping due to Windows auto-discovery.

Prevention
Disable WSD auto-add via GPO.