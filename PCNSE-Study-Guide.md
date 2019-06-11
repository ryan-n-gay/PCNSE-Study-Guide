# PCNSE Study Notes

## Info

### PCNSE Exam Overview

- 80 Minutes
- 75 Questions
- Exam cover Palo Alto Networks firewalls and related technologies

### Resources

Web-search for "Palo Alto Network PCNSE 8 Study Guide"
LMS: http://education.paloaltonetworks.com/learningcenter
Education Course:
  EDU-110/210: Essentials
  EDU-120/220: Managing Multiple Firewalls
  EDU-330: Troubleshooting
Practice Exams, learning assessments, and ACE certification
Practice Lab

### Suggestions

- Focus on the firewall
- Know the Security Operating Platform "story"
- Understand default behaviors
- Know what policy rules look like in the CLI
- Questions test understanding, not memorization

### Topics of Interest

- Firewall Features
  - Security Profiles
  - Decryption
  - HA
  - Global Protect
  - Site-to-site VPN
  - App-ID
  - User-ID
  - Zone and DoS Protection
  - Log Forwarding
  - Policies
  - QoS

### Additional Topics of Interest

- Architecture
  - Management Plane
  - Data Plane
  - Single Pass Architecture (SPA)
- Processes and Procedures
  - Installing Licenses
  - Upgrades
- Panorama
  - Templates
  - Device Groups
  - Logging and Reporting
- 
### Top Challenging Topics

- Administrative roles
- Authentication methodologies
- AutoFocus integration
- MFA enablement and use
- Wildfire concepts

## Firewall 9.0 Essentials: Configuration and Management (EDU-110)

### Firewall 9.0: Overview

#### Training Objective

- Use network segmentation to reduce your attack surface
- Use App-ID to determine application usage
- Use Content-ID to reduce your attack surface
- Use WildFire to reduce the number of zero-day attacks
- Use User-ID to determine who is accessing the internet
- Use firewall logs to recognize threats
- Use best practice configuration to successfully block malware

#### Module Learning Objectives

1. Security Operating Platform and Architecture
	- Describe the characteristics of the Security Operating Platform
	- Describe the single-pass architecture
	- Describe the Zero Trust security model and how it relates to traffic moving through your network
2. Initial Configuration
	- Connect to the firewall and log in as admin
	- Configure the network settings for the management interface port
	- Describe the differences between the running config and candidate config
	- Configure dynamic firewall updates to update the applications and threats databases
	- Create a local firewall administrative account
	- Access the firewall logs
3. Interface configuration
	- Describe the flow logic of the next-generation firewall
	- Create a security zone
	- Describe the differences between Tap, Virtual Wire, Layer 2, and Layer 3 interfaces
	- Create and configure a virtual router
	- Define a static default route
	- Configure a VLAN interface
	- Configure a loopback interface
4. Security and NAT Policies
	- Display and manage security policy rules
	- Describe the differences between implicit and explicit rules
	- Create a Security Policy
	- Describe the differences between source and destination NAT
	- Configure NAT
	- Configure destination NAT port forwarding
5. App-ID
	- Define application identification
	- Describe the four major technologies to help identify applications
	- Configure application filters and application groups
	- Detect unidentified applications traversing the firewall
	- Configure scheduling of updates to App-ID
6. Content-ID
	- Describe the seven different Security Profiles types
	- Define the two predefined Vulnerability Protection Profiles
	- Configure Security Profiles to prevent virus and spyware infiltration
	- Configure File Blocking Profiles to identify and control the flow of file types through the firewall
	- Configure a DoS Profile to help mitigate Layer 3 and 4 protocol-based attacks
7. URL Filtering
	- Describe how the firewall uses the PAN_DB database to filter user access to websites
	- Configure a custom URL Filtering Profile to minimize the number of blocked websites between trusted zones
	- Configure safe search and logging options
	- Configure access to only enterprise versions of SaaS applications
8. Decryption
	- Describe the benefits of decrypting traffic
	- Define the three decryption types that can be configured at the firewall
	- Describe how a certificate chain of trust is used to authenticate a device, service, or person
	- Configure an SSL Forward Proxy policy
	- Review Traffic logs to determine whether SSL sessions are being decrypted
9. WildFire
	- Describe how a firewall works with the WildFire Threat Intelligence Cloud
	- Describe how WildFire analysis is used to update URL categories listed in the PAN_DB URL Filtering database
	- Configure Session Information Settings to specify which type of information will be sent to WildFire
	- Define a WildFire Analysis Profile
	- Configure the types of information submitted to WildFire and the amount of information returned to the firewall in the report
10. User-ID
	- Describe the four main components of User-ID
	- Describe the differences between the integrated agent and the Windows-based agent
	- Define the methods to map IP addresses to users
	- Configure the PAN-OS integrated agent to connect to monitored services
	- Configure the Windows-based agent to probe IP addresses for username information
11. GlobalProtect
	- Describe the three major components of GlobalProtect
	- Configure the client and server certificates to authenticate the agent and the portal
	- Define the three methods supported for GlobalProtect client connections
	- Configure the tunnel parameters for an external gateway connection
12. Site-to-Site VPNs
	- Describe the three basic requirements for creating a VPN
	- Configure the interface, IP addresses, and PSK for the IKE Gateway
	- Configure the DH group, encryption methods, and authentication methods for an IKE Cryptographic Profile
	- Configure a static route in the route table to the tunnel
	- Troubleshoot your IPsec VPN issues from the responder side of the VPN tunnel
13. Monitoring and Reporting
	- Create an interactive, graphical summary of the applications with the ACC
	- Export policy rules, objects, and IPS signatures using the configuration table export
	- Create a predefined report to view traffic statistics for the previous day.
	- Describe how log files are forwarded to and external source
	- Configure a Server Profile to froward logs to a syslog server
14. Active/Passive High Availability
	- Describe the differences between active/active and active/passive HA
	- Define the prerequisites for creating an HA pair
	- Describe the metrics used to detect a firewall failure
	- Configure the firewall interfaces used for heartbeats and hellos
	- Configure an HA pair
15. Next-Generation Security Practices
	- Describe the migration process when moving from port-based firewall policies to application based firewall policies
	- Use Application Command Center, or ACC, to view trends in network activity
	- Define actions to take for optimizing Security Profiles
	- Describe the benefits and differences between the Heatmap and BPA reports

## PCNSE Prep

- Authentication & Authorization for Device Administration
- Functions and Concepts of WildFire
- Firewall Integration with AutoFocus
