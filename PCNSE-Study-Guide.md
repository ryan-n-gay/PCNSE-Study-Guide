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
	- Configure a Server Profile to forward logs to a syslog server
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
		| Reconnaissance | Attackers carefully research, Identify, and select targets, often using phishing tactics or extracting public information from LinkedIn profiles, or from cooperate websites. These criminals can also scan for network vulnerabilities and services or applications that they can exploit     |
		| Weaponization | The attacker determines which methods to use in order to deliver malicious payloads. |
		| Delivery | They may choose to embed intruder code within seemingly innocuous files. Or, attackers may craft deliverables to attract the specific interests of an individual. |
		| Exploitation | An attacker now deploys an exploit against a venerable application or system. Deploying an exploit allows the attack to gain initial entry point into the organization. |
		| Installation | Attacker will seek to establish privileged, operations, such as maintaining access, persistence, and escalating privileges. |
		| Command and Control | Attackers establish a command channel back through the internet to a specific server so that they can communicate and pass data back and forth between infected devices and their own infrastructure |
		| Act on the Object | Now that an attacker has communication, they will act upon motivations to achieve their goal. Their motivation could be data exfiltration, destruction of critical infrastructure, to deface web property, or to create fear or the means for extortion. |
		
- Palo Alto Networks Security
	- Prevention-Focused
		- React-only to the critically important threat
	- Highly Automated
		- Reduce or remove manual response
	- Safely enables all applications
		- Granualar use of controllers and prevention of known and unkown cyberthreats
- Security Operating System
	- Cortex
		- Cortex Data Lake
		- Cortex XDR		
			- Apps can be created and developed on a common application framework (Cortex) to rapidly build and deliver cloud-based security serives with no additional infrastructure or on-premises hardware changes. Apps are delivered from the cloud to extend the capabilities of the platform, including the ability to effortlessly collaborate between different apps, share threat context, and intelligence, and drive automated response and enforcement.
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

		| Name     | Responsibility     | Additional info |
		| :------------- | :------------- | :------------- |
		| Policy Engine       |        |
		| Content-ID | Data Filtering | Content scanning: threats, URLS, confidential Data |
		| | URL Filtering |
		| | Real-time Threat Prevention |
		| App-ID | Application Protocol Decoding | Traffic classification with APp-ID technology |
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
	| Lack of Visibility       | Internet       | If IT and Network security teams have no true visibility, they cannot control the users and applications traversing the network. The lack of full visibility means that organizations are vulnerable to attacks from both within the organization and from the public internet. |
	| North-South Traffic | Traffic Entering and Leaving the network | |
	| East-West Traffic | Internal Traffic that never leaves the gateway | |
	
- Data Flows Secured by Palo Alto
	- Zero Trust
		- An alternative security model that addresses the shortcomings of failing perimeter-centric strategies by removing the assumption to trust
			- The need to Establish trust boundaries that effectively compartmentalize different segments of the internal computing environment
		- Intended to remedy the deficiencies with perimeter centric strategies and the legacy devices and technologies used to implement them by promoting "never trust, always verify" as a guiding principal.
			- Move security functionality closer to the different pockets of resources that require protection.
- Integrated Approach to Threat Prevention
	
	| | Delivery     | Expoitation | Installation | C2 | Act on Object
	| :------------- | :------------- |
	| App-ID       | Block high-risk applications | | | Block C2 on non-standard ports | Prevent exfiltration and lateral movement |
	| URL Filtering | Block known malware sites | | | Block Malware, fast-flux domains | |
	| Vulnerability | | Block the request | | | Prevent lateral movement |
	| Anti-Spyware | | | | Block spyware, C2 traffic | |
	| Antivirus | | Block Malware | | Prevent lateral movement |
	| Traps | Monitor allowed processes and executables | Prevent evasions | Prevent malicious .exe from running | | |
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
			- Chassis Series
	- Panorama
		- M-200
		- M-500/WF-500-600
- Virtual Firewalls
	- Virtual Systems (vsys) are septate, logical firewall instances within a single physical Palo Alto Networks firewall
	- Rather than use multiple firewalls, service providers can use a single pair of firewalls and enable virtual systems on them.
	- A vsys contains:
		- A set of physical and logical interfaces and sub interfaces
		- Virtual routers
		- Security zones
	- When using a vsys you can segment
		- Administrative access
		- Management of all policies
		- All objects
		- User-ID
		- Certificate management
		- Server Profiles
		- Login, reporting, and visibility functions
	- Supporting Firewalls
		- PA-3000 and up
	- Virtual Systems Supported
		- Each firewall has a base number of vsys, number varies by platform
	- License required to
		- Support multiple vsys on the PA-3x00 Series
		- Create additional virtual systems than the base number

### 9.0 Initial Configuration

#### Module Objectives

- After you complete this module, you should be able to:
	- Connect to the firewall and log in as admin
	- Configure the network settings for the management interface port
	- Describe the difference between the running config and then candidate config
	- Configure dynamic firewall updates top update the applications and threats databases
	- Create a local firewall administrative account
	- Access the firewall logs

#### Administrative Controls

- Initial Access to the Firewall
	- Palo Alto Networks firewalls are built with a dedicated out-of-band network management interface labeled MGT
	- This interface passes only management traffic for the firewall and cannot be configured as a standard traffic interface
	- It is use for direct connectivity to the Management Plane of the firewall
	- You can configure the firewall to allow traffic over the normal in-band traffic interfaces
	- Default MGT IP addressing:
		- Most firewall models
			- 192.168.1.1
		- VM-Series firewalls:
			- Starting with PanOS 8.0 DHCP Client
		- You can configure any model of firewall to use DHCP for Management
	- Initial configuration must be preformed using either:
		- Dedicated out-of-band management Ethernet interface (MGT)
		- Serial Console Connection
			- Default configuration values of 9600-8-n-1
	- Default access:
		- username: admin
		- password: admin
		- A warning message appears at login in the web interface and the CLI until the default password is changed.
- Administrative Access
	- There are 4 ways to access firewall management
		- Web interface
			- Administrators often configure and monitor the firewall through the web-based interface. This graphical interface provides detailed administrative and reporting tools in an intuitive browser-based format
		- SSH/Console CLI
			- The PanOS CLI enables you to access the firewall, display status and configuration information, and modify the configuration. Access to the PanOS CLI is provided through SSH, Telnet, or directly through the serial console.
		- Panorama
			- If multiple firewalls are deployed in your network, use Panorama to manage configuration, policies and software and dynamic content updates. Panorama also will aggregate data from all managed firewalls and give you visibility into the information about all the traffic on your network
		- Rest XML API
			- You can use the Rest-based interface to access operational status, reports, and packet captures, or configure the firewall. The PanOS XML API also can be used to capture login events and send them to the firewall. The XML API is implemented using HTTP/HTTPS requests and responses. Palo Alto Networks also provides and API browser on the firewall at https:://<firewall>/api, where <firewall> is the hostname or IP address of the firewall
- Initial System Access
	- Reset to Factory Configuration
		- From CLI with known admin user password:
			- request system private-data-reset
				- Erase all logs
				- Reset all settings
				- Saves a default configuration after the MGT IP address is changed
		- If admin account password is unknown, reboot firewall to enter maintenace mode
		- From CLI without and admin user password:
			- Type CLI command via console port
				- maint
				- Choose Reset to Factory Default
	- Steps for MGT interface Configuration: Web Interface

		1. Configure your system or laptop Ethernet interface in the 192.168.1.0/24 subnet
		2. Connect to the MGT port with an Ethernet cable
		3. Launch a web-browser connection to https://192.168.1.1
		4.  Log in using the default firewall username and password
		5. Select **Device > Setup > Interfaces**
		6. Click **Management**
		7. In the window that opens, configure the network settings for the MGT interface
		8. Reconnect to the web interface using the new network configuration
		
	- MGT Interface configuration: Web Interface
		- Enabled by default are:
			- HTTPS
				- Is required to access and manage the firewall through the MGT interface using the web interface
			- SSH
				- Is required to enable CLI access
			- Ping
				- Required for status checks, HA keep alive, and monitoring purposes.
			- For addition security, enter IP addresses in the **Permitted IP Addresses** field to restrict administrative access to those IP addresses
			- Other features are available once enabled depending on what access you need. 
	- Configure General Settings
		- Firewall Hostname can be a maximum of 31 characters long
			- Alphanumeric
			- Hyphen
			- Underscores
			- Default hostname is the firewall model name
		- Domain Name
			- 31 Characters max
			- Alphanumeric
			- Hyphen 
			- Dot characters
			- default id empty
		- DHCP
			- The accept DHCP option are available only if MGT is configured for by DHCP. Select these options to configure the firewall to allow hostname and domain name configuration by DHCP
		- Logon Banner
			- Configure a security message in the Login Banner (Optional)
		- SSL/TLS
			- When SSL/TLS is used, the firewall requires a digital certificates that is trusted by the clients
		- Latitude and longitude
			- Latitude and longitude are used to place the firewall on maps on the ACC tab
	- Configure DNS and NTP Servers
		- **Device > Setup > Service > Gear Icon**
		- DNS server configuration is required to reach updater servers
		- NTP client configuration is optional but recommended
			- If the MGT interface is configured by DHCP, the DNS and NTP server addresses can be assigned by DHCP
			- Configure Domain name of the update server to download updated software and updates to the threat database
			- When **Verify Update Server Identity** is enabled:
				- It adds a level of security for communication between the firewall and the update server
	- Service Routes
		- By default, the MGT port is used to access external services
			- External Services
				- Update services
				- DNS services
				- NTP services
				- Etc.
			- If you do not want to use the out-of-band management port, you must configue an in-band port to access external services (optional)
	- Configure Service Routes
		- **Device > Setup > Services > Servicce Route Configuration**
			- Select any service that will use a in-band interface
			- **Set Selected Service Routes**
			- Choose the Source Interface and Source Address
			- **Commit** changes for the service to start using the in-band interface
- Configuration Management
	- Configuration types
		- Running Config
			- the actual configuration controlling the operation of the firewall. It is maintained in a file on the firewall named running-config.xml
			- Configuration settings currently active on the firewall
		- Candidate Configuration
			- A copy of the running config that is copied over at startup. In-progress edits are made to the candidate config
			- Configuration changes made but not commited
		- After you commit, the candidate configuration overwrites the current running configuration
		- The firewall saves previous running configurations and labels these configuration by date and timestamps
		- The web interface includes a set of operations that are used to manage the running and candidate configurations
	- Global Configuration Management
		- **Device > Setup > Operations**
		- These operations are global in scope and not per-admin
			- **Revert**, **Save**, and **Load** operations all manage configurations local to the firewall
			- **Export** operations transfer configurations as XML-formatted files from the firewall to the host running the web interface
			- **Import** operations import configuration from the host to the firewall running the web interface
	- Configuration Operations
		- Boot Process
		- ![Boot Process](/images/Boot\ Process.png)
	- Save a Candidate Configuration
		- **Device > Setup > Operations**
		- You can save a candidate configuration in several ways. 
			- **Revert to last saved configuration** to abort any changes made to the configuration since the last save
			- **Revert to running configuration** will delete the current candidate configuration and copy the running configuration to the candidate
			- **Save named configuration snapshot** to save the current candidate to an XML filename on disk. Multiple named configurations can be saved on the firewall. These saves will survive a firewall reboot
			- **Saved candidate configuration** to save the configuration to memory. If edits are made and **Save candidate configuration** is clicked again, the configuration that is saved in memory is overwritten. If the firewall is rebooted before the cadidate config is saved, it will no survive a reboot as it is stored in volitile memory
			- **Load named configuration snapshot** to replace the current candidate configuration in an XML file
	- Admin-Level Commit
		- Became avaible as of version 8.0, and allows administrators to only commit their changes to the firewall
		- Simplifies your configuration workflow because you do not have to coordinate commits with other administrators
		- Prior to 8.0
			- Commit operations permited all staged changes
	- Performing a Per-Admin Commit
		- COmmit just your changes, or yours and other admins changes. 
		- You can select just your admin account, or your admin account and another admins account without commiting all changes. 
	- Admin-Level Save and Revert
		- Every Version
			- Save your current progress and continue later without having to commit a partially completed configuration change
			- Saved changes are made by any administrator are written to the same default XML file
			- Each change is tagged with information about the administrator that made the change
		- Every Verion
			- Remove the most recent changes made since last saved candidate configuration
			- You can revert to just your last saved configuration of a select group of other administrators
			- Revert per-admin or all changes to previous saved configuration
	- Preview and Validate Changes
		- **Preview Changes** compares the candidate configuration to the running configuration
		- **Change Summary** lists the individual settings for which you are committing changes
		- **Validate Changes** shows any error messages that would appear during commit
		- **Preview changes** and **Valiadate Commit** display all changes by all administrators or just those changes associated with selected administrators
	- Transaction Locks for Multiple
		- Commit Lock
			- Blocks other admins from committing the candidate config
		- Config Lock
			- Blocks other admins from changing the candidate config
	- Licensing and Software updates
		- Activate the Firewall
			- Regitster with Palo Alto > Activate Support License > Activate the license for each purchased subscription purchased
			- Before you can retrieve a license, the firewall must be configured with an IP address, netmask, default gateway, and DNS server IP addresses
		- Dynamic Updates
			- Which updates are avaible
				- Antivirus, spyware, new malicious domains and URLs, and new application signatures
			- How can updates be downloaded
				- Directly from Palo Alto
			- When are updates release
				- Anitvirus: Daily
				- Applications and ThreatsL weekly updates, new applications added monthly
				- WildFire: approximately every five minutes
		- PanOS Software updates
			- The firewall requires updates to the PanOS software and threat databases to maintain the most current protection levels
	- Account Administration
		- Administrator Account and Role Repositories
			- By default, only the pre-defined admin account has access to the firewall
			- Each administrative account is assigned a role with specific Privlieges
			- Admin Role
				- Custom Role
				- Dynamic Role
			- The firewall can authenticate locally or remotely defined administrators
			- Authentication
				- Local Account and Password
				- Remote Account and Password
		- Creating an Administrator and Local account (Demo)
		- Creating Non-Local Administrators (Demo)
		- Firewall Authentication of Non-Local Passwords
			- Non-local account passwords must be authenticated through their external authentication services
			- Authentication Profile
				- Before you can access an external authentication service, you must create the appropriate profiles on the firewall. 
				- An authentication profile contains the information necessary to authnticate an admin account with an exterternal authentication service after one of the service's servers has been located.
			- Authentication Sequence
				- A firewall can consult multiple external services to authenticate an account. You specify an ordered list of Authentication Profiles by adding them to an optional Authentication Sequenece
				- If you have created an Authentication Sequence, then specify the Authentication Sequence in place of an Authentication Profile when you add a user account on the firewall.
			- Server Profile
				- An Authentication Profile uses a Server Profile, which you have created, to locate an external authentication service's servers. You configure a Server Profile with a list of an external authentication service's servers.
		- Configure Server Profiles
			- Server Profiles define connections that the firewall can make to external servers of specific types
			- For authentication purposes, specify Kerberos, LDAP, RADIUS, SAML, or TACACS+ servers.
			- Authentication profiles require server profiles to validate login information for administrator accounts that are not created on the firewall. 
		- Configure Authentication Profiles
			- An authentication profilfe specifies which authentication server and settings are used to authenticate an admin account
			- An authentication profile can ben specified when an admin account is created
		- Configure Authentication Sequence Profiles
			- An authentication sequencce is optional if you have defined multiple external services
	- Viewing and Filtering Logs
		- Viewing and Filtering Logs (Demo)

## PCNSE Prep

- Authentication & Authorization for Device Administration
- Functions and Concepts of WildFire
- Firewall Integration with AutoFocus
