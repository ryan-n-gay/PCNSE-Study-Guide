# PCNSE Study Notes

## Info

### PCNSE Exam Overview

- 80 Minutes
- 75 Questions
- Exam cover Palo Alto Networks firewalls and related technologies

### Resources

- Web-search for "Palo Alto Network PCNSE 8 Study Guide"
- LMS: http://education.paloaltonetworks.com/learningcenter
- Education Course:
  - EDU-110/210: Essentials
  - EDU-120/220: Managing Multiple Firewalls
  - EDU-330: Troubleshooting
- Practice Exams, learning assessments, and ACE certification
- Practice Lab

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

### Firewall 9.0: Security Operating Platform and Architecture

#### Training Objectives

- Describe the characteristics of the Security Operating Platform
- Describe the differences between single-pass architecture and parallel processing
- Describe the Zero Trust security model and how it relates to traffic moving through your network

#### Security Platform Overview

- Cyber Attack Lifecycle
	- The Cyber-Attack Lifecycle is a sequence of events that an attacker goes through to infiltrate a network and exfiltrate data from it.
	- Lifecycle
		
		| Stage | Description |
		| :------------- | :------------- |
		| Reconnaissance | Attackers carefully research, Identify, and select targets, often using phishing tactics or extracting public information from LinkedIn profiles, or from corprate websites. These criminals can also scan for network vulnerabilies and services or applications that they can exploit     |
		| Weaponization | The attacker determins which methods to use in order to deliver malisious payloads. | 
		| Delivery | They may choose to embed intruter code within seemingly innocouos files. Or, attackers may craft deliverables to attract the specific intrests of an individual. |
		| Exploitation | An attacker now deploys an exploit against a vunerable application or system. Deploying an exploit allows the attack to gain initial entry point into the organization. |
		| Installation | Attacker wi ll seek to establish privileged, operations, such as maintaining access, persistance, and escalating priviledges. |
		| Command and Control | Attackers establish a command channel back through the internet to a specific server so that they can communicate and pass data back and forth between infected devices and their own infrastructure |
		| Act on the Object | Now that an attacker has communiucation, they will act upon motivations to achieve their goal. Their motivation could be data exfiltration, destruction of critical infrastructure, to defgace web property, or to create fear or the means for extortion. |
		
- Palo Alto Networks Security
	- Prevention-Focused
		- React-only to the criticaly important threat
	- Highly Automated
		- Reduce or remove manual response
	- Safely enables all applications
		- Granualar use of controllers and prevention of known and unkown cyberthreats
- Security Operating System
	- Cortex
		- Cortex Data Lake
		- Cortex XDR		
			- Apps can be created and deveolped on a common application framework (Cortex) to reapidly build and deliver cloud-based security serives with no additional infrastructure or on-premises hardware changes. Apps are delivered from the cloud to extend the capabilities of the platform, including the ability to effortlessly collaborate between diffrenet apps, share threat context, and intelligence, and drive automated response and enforcement. 
- Network Security
	- Palo Alto Network Security Operating Platform firewalls are designed to safely enable applications and prevent modern threats. The firewall can identify all network traffic based on applications, user, content, and devices, and lets you express your business policies in the form of easy-to-understand security rules.
- Advanced Endpoint Protection
	- Traps Advanced Endpoint Protection provided multi-method prevention, a proprietary combination of malware and exploit prevention methods that preemptively block both known and unknown threats directly on the endpoint. 
- Cloud Security
	- The Palo Alto Networks VM_Series firewall is a virtualized form of the Palo Alto Networks Security Operating Platform firewall. The VM-Series   firewalls are designed for use in a virtualized or cloud environment to identify all network traffic based on applications, users, content, and devices.
- Additional Palo Alto Networks Products
	- Panorama
	- Aperture
	- GlobalProtect
	- AutoFocus
	- MindMeld

#### Next-Generation Firewall Architecture

- Palo Alto Networks Single-Pass Architecture
	- Traditional Firewalls
		- Identify applications only by protocol and port number
	- Palo Alto Firewalls uses packet inspection and a library of applications signatures to
		- Distinguish between applications, that have the same protocol and port
		- Identify potentially malicious applications that use non-standard ports
	- Single Pass:
		- Operations per packet
		- One single policy (per type)

		| Name     | Resposibility     | Addtional info | 
		| :------------- | :------------- | :------------- |
		| Policy Engine       |        |
		| Content-ID | Data Filtering | Content scanning: threats, URLS, confidentiual Data |
		| | URL Filtering |
		| | Real-time Threat Prevention |
		| App-ID | Appliocation Protocol Decoding | Traffic classification with APp-ID technology | 
		| | Application Protocol Detection and Decryption|
		| | Application Signatures|
		| | Heuristics |
		| User-ID | | User or group mapping |
		| L2/L3 Networking, HA, Config Management, Reporting | |
		
		- Parallel Processing:
			- Function-specific parallel processing hardware engines
			- Sperate data and control planes
	- Palo Alto Networks Firewall Architecture
		
		| Plane     | Function     | Insite |
		| :------------- | :------------- | :------------- |
		| Control Plane     | Management       | configuration - logging - reporting |
		| Data Plane | Signature Matching | exploits - virus - spyware - CC# - SSN |
		| | Security Processing | App-ID - User-ID - URL match - policy match - SSL/IPsec - decompression |
		| | Network Processing | flow control - MAC lookup - route lookup - QoS - NAT
		
#### Zero Trust Security Model

- Data flows in and Open Network
	
	| Name     | Description     | Additional Detail |
	| :------------- | :------------- | :------------- |
	| Lack of Visibility       | Intenet       | If IT and Netowrk security teams have no true visibility, they cannot control the users and applications traversing the network. The lack of full visibility means that organizations are vunerable to attacks from both within the organization and from the public internet. |
	| North-South Traffic | Traffic Entering and Leaving the network | |
	| East-West Traffic | Internal Traffic that never leaves the gatway | |
	
- Data Flows Secured by Palo Alto
	- Zero Trust
		- An alternative security model that addresses the shortcomings of failing perimeter-centric strategies by removing the assumption to trust
			- The need to Establish trust boundaries that effectiviely compartmentalize diffrenet segments of the internal computing enviorment
		- Inteneded to remedy the deficiencies with perimiter centric strategies and the legacy devices and technologies used to implement them by promoting "never trust, always verify" as a guiding principal.
			- Move security functionality closer to the diffrent pockets of resources that require protection.
- Integrated Approach to Threat Prevention
	
	| | Delivery     | Expoitation | Installation | C2 | Act on Object
	| :------------- | :------------- |
	| App-ID       | Block high-risk applications | | | Block C2 on non-standard ports | Prevent exfiltration and lateral movement |
	| URL Filtering | Block known malware sites | | | Block Malware, fast-flux domains | |
	| Vulnerability | | Block the request | | | Prevent lateral movement |
	| Anti-Spyware | | | | Block spyware, C2 traffic | |
	| Antivirus | | Block Malware | | Prevent lateral movement |
	| Traps | Monitor allowed processes and executables | Prevent envasions | Prevent malicious .exe from running | | |
	| File Blocking | | | Prevent drive-by downloads | | Prevent exfiltration and lateral movement |
	| DoS and/or Zone | | Prevent evasions | | | Prevent DoS attacks |
	| WildFire | Identify malware | | Detect unknown malware | Detect new C2 traffic | |
	
#### Firewall Offerings

- Physical Platforms
	- Next-Generation Firewalls
		- PA-220
		- PA-200R
		- PA-800 Series
		- PA-3200 Series
		- PA-5200 Series
		- PA-7000 Series
			- Chassi Series
	- Panorama
		- M-200
		- M-500/WF-500-600
- Virtual Firewalls
	- Virtual Systems (vsys) are septate, logical firewall instances within a single physical Palo Alto Networks firewall
	- Rather than use multiple firewalls, service providers can use a single pair of firewalls and enable virtual systems on them.
	- A vsys contains:
		- A set of physical and logical interfaces and subinterfaces
		- Virtual routers
		- Security zones
	- When using a vsys you can segment
		- Administrative access
		- Management of all policies
		- All objects
		- User-ID
		- Certificate management
		- Server Profiles
		- Loggin, reporting, and visibility functions
	- Supporting Firewalls
		- PA-3000 and up
	- Virtual Systems Supported
		- Each firewall has a base number of vsys, number varies by platform
	- License required to
		- Support multiple vsys on the PA-3x00 Series
		- Create additional virtual systems than the base number

## PCNSE Prep

- Authentication & Authorization for Device Administration
- Functions and Concepts of WildFire
- Firewall Integration with AutoFocus
