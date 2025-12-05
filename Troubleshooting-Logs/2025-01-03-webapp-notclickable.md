Troubleshooting Log 06 — Web App Button Not Clickable

Build: UAT 1.3.88
Severity: High
Module: Cart → Checkout

Issue
“Place Order” button unresponsive.

Investigation
UI element overlapped by transparent div

Z-index conflict
Occurs only on 1366×768 screens 

Fix Request
Sent CSS patch suggestion:

div.confirm-overlay { pointer-events: none; }
button.submit { z-index: 9999; }