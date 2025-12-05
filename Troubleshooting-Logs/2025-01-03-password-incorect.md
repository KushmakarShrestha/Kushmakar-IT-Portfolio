Troubleshooting-log-13.md

Issue: User unable to log in – “Password Incorrect.”
Impact: Low

Diagnosis
Checked AD: account locked out
Lockout triggered from an old mapped drive using cached credentials
User recently changed password

Actions
Unlocked account in AD.
Removed old credentials from Control Panel > Credential Manager.
Updated mapped drive settings.

Resolution
Login successful.

Root Cause
Stored credentials causing repeated failed login attempts.