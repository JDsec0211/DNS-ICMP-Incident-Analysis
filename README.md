# DNS-ICMP-Incident-Analysis
Beginner cybersecurity project analyzing DNS, UDP, and ICMP traffic using tcpdump to investigate a network incident.
# DNS & ICMP Traffic Analysis

Beginner cybersecurity project analyzing network traffic using tcpdump to investigate DNS resolution failure and ICMP error responses.
# DNS and ICMP Incident Analysis

## Project Overview
This project analyzes a simulated cybersecurity incident in which users were unable to access the website `www.yummyrecipesforme.com`. Using tcpdump log data, the investigation identifies the affected protocols and determines the likely cause of the issue.

## Scenario
Users reported that they could not load the website and received the error message: `destination port unreachable`.

A packet analysis showed that DNS requests were being sent from the client to the DNS server using UDP port 53. Instead of returning a valid DNS response, the server returned ICMP error messages stating: `udp port 53 unreachable`.

## Protocols Involved
- **DNS** – used to resolve the website domain name to an IP address
- **UDP** – transport protocol used to send the DNS request
- **ICMP** – used to return the error message

## Key Findings
- The client sent DNS queries to the DNS server on UDP port 53
- The DNS server responded with ICMP unreachable messages
- The error repeated multiple times
- DNS resolution failed, so the browser could not continue to the website

## Suspected Root Cause
The DNS service was unavailable on UDP port 53. Possible causes include:
- DNS service not running
- Firewall blocking port 53
- DNS server misconfiguration

## Next Steps
- Verify DNS service status
- Check whether UDP port 53 is open
- Review firewall rules
- Confirm DNS configuration
- Retest DNS resolution

## Skills Demonstrated
- Network traffic analysis
- Packet inspection
- DNS troubleshooting
- Understanding UDP and ICMP
- Cybersecurity incident reporting
