Troubleshooting-log-15.md

Issue: WiFi disconnecting every 5–10 minutes on laptop.
Impact: Medium

Diagnosis
Event Viewer: Netwtw10 5002/5005 errors
Intel WiFi driver outdated
Power saving enabled on NIC

Actions
Updated Intel AX201 driver to latest version.
Disabled "Allow computer to turn off this device to save power".
Flushed DNS & reset Winsock.

Resolution
Stable WiFi connection for 2+ hours.