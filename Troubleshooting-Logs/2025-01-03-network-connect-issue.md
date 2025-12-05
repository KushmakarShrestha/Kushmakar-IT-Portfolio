Troubleshooting Log 01 — Network Connectivity Issue
Technician: Kushmakar Shrestha
Device: Windows 10 Laptop
Network: Home WiFi
Date: 05 Dec 2025

1. Issue Summary
User reports they cannot access a website and suspects the internet is down.

2. Initial Hypothesis
Connectivity issue may be caused by:
Local device issue
Router/gateway issue
DNS failure
Internet outage

Goal: Identify where the connection fails.

3. Diagnostics Performed
Step 1 — Confirm local network configuration
Command:
ipconfig
Findings:
Device IP: 10.222.77.36
Default Gateway: 10.222.77.107
This confirms the device has an IP.

Step 2 — Test connectivity to gateway
Command:
ping 10.222.77.107
Result:
100% packet loss
This means the device cannot reach the router.

Step 3 — Test loopback / self-connectivity
Command:
ping 10.222.77.36

Result:
0% loss, <1ms
NIC (network card) is functioning normally.

Step 4 — Test DNS / external routing
Command:
tracert www.google.com
Result (summary):
Hop 1: 10.222.77.107 (reachable in traceroute, NOT ping)
Multiple ISP hops resolved successfully
Final hop resolves to Google server (142.250.xx.xx)

Important Discovery:
Gateway responds to traceroute but does not respond to ping.
This strongly indicates router firewall/ICMP blocking, not connectivity failure.

4. Root Cause Analysis
 Internet connectivity is working
 DNS is resolving
 Routing is successful
 Gateway is blocking ICMP echo requests (ping)

This is a common behaviour on some routers and ISPs.
User assumed “no internet” because ping failed, but connectivity is normal.

5. Resolution
Explained difference between ICMP blocking vs true network downtime
Provided instruction to test internet properly:
Open browser to multiple sites
Perform tracert instead of relying on ping
Try nslookup to verify DNS
The internet is working — false alarm caused by blocked ping.

6. Concepts Learned
Ping failing ≠ Internet down
Routers can block ICMP requests
Traceroute gives deeper visibility into network hops
Distinguishing between:
Local NIC issues
Gateway reachability
DNS resolution
Routing connectivity