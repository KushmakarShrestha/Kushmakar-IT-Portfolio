Troubleshooting Log 03 — Login Page Fails on Incorrect Credentials

Application: Web App (UAT)
Build: v1.4.22
Issue Type: QA Bug
Severity: Medium

Description
Incorrect password produces blank page instead of error message.

Steps to Reproduce
Go to /login
Enter valid username + invalid password
Click “Login”

Expected
User sees: “Incorrect username or password.”

Actual
White blank screen.

Analysis
Frontend fails to render error component. Backend returns status 401 correctly.

Reported To
Frontend dev team with console logs + HAR file.