# Discovery.md


[MITRE ATT&CK - Discovery](https://attack.mitre.org/wiki/Discovery)
* Discovery consists of techniques that allow the adversary to gain knowledge about the system and internal network. When adversaries gain access to a new system, they must orient themselves to what they now have control of and what benefits operating from that system give to their current objective or overall goals during the intrusion. The operating system provides many native tools that aid in this post-compromise information-gathering phase. 





-------------------------------
### Account Discovery
* [Account Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1087)
	* Adversaries may attempt to get a listing of local system or domain accounts. 

#### Linux
* On Linux, local users can be enumerated through the use of the `/etc/passwd` file which is world readable. In mac, this same file is only used in single-user mode in addition to the `/etc/master.passwd` file. 

#### OS X
* On Mac, groups can be enumerated through the `groups` and `id` commands. In mac specifically, `dscl . list /Groups` and `dscacheutil -q group` can also be used to enumerate groups and users. 
* `dscl . list /Users`

#### Windows
* [Account Discovery - ATT&CK](https://attack.mitre.org/wikipediai/Technique/T1087)
	* Adversaries may attempt to get a listing of local system or domain accounts. 
	* Example commands that can acquire this information are `net user`, `net group <groupname>`, and `net localgroup <groupname>` using the Net utility or through use of `dsquery`. If adversaries attempt to identify the primary user, currently logged in user, or set of users that commonly uses a system, System Owner/User Discovery may apply. 
* [Net.exe reference](http://windowsitpro.com/windows/netexe-reference)
* [Dsquery - technet](https://technet.microsoft.com/en-us/library/cc732952.aspx)
* [“I Hunt Sys Admins” - Harmjoy](http://www.harmj0y.net/blog/penetesting/i-hunt-sysadmins/)
* [Powerview | Powershell Mafia - Powersploit - Recon](https://github.com/PowerShellMafia/PowerSploit/tree/master/Recon)
	* PowerView is a PowerShell tool to gain network situational awareness on Windows domains. It contains a set of pure-PowerShell replacements for various windows "`net *`" commands, which utilize PowerShell AD hooks and underlying Win32 API functions to perform useful Windows domain functionality. It also implements various useful metafunctions, including some custom-written user-hunting functions which will identify where on the network specific users are logged into. It can also check which machines on the domain the current user has local administrator access on. Several functions for the enumeration and abuse of domain trusts also exist. See function descriptions for appropriate usage and available options. For detailed output of underlying functionality, pass the -Verbose or -Debug flags.






-------------------------------
### Application Window Discovery
* [Application Window Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1010)
	* Adversaries may attempt to get a listing of open application windows. Window listings could convey information about how the system is used or give context to information collected by a keylogger. In Mac, this can be done natively with a small AppleScript script.

#### OS X
* [Listing all windows of all applications - StackOverflow](https://stackoverflow.com/questions/14551419/listing-all-windows-of-all-applications)

#### Linux
* [How to get the list of open windows from xserver](https://stackoverflow.com/questions/252906/how-to-get-the-list-of-open-windows-from-xserver)

#### Windows
* [Get Active Window on User Desktop - technet](https://gallery.technet.microsoft.com/scriptcenter/Get-Active-Window-on-User-352fa957)
	* This script will tell you the application that user is currently using. This also called active window. This script replies on unmanaged dll, user32.dll, to get this information. It has a function called GetForegroundWindow() which returns the Windowhandle of the active process. 
* [Get-Window](https://www.vexasoft.com/pages/get-window)
	* Gets the application windows that are open on the local desktop. 
* [Get Active Window titles of remote computer? - reddit](https://www.reddit.com/r/PowerShell/comments/2onpdm/get_active_window_titles_of_remote_computer/)
* [How to get list of running applications using PowerShell or VBScript](https://stackoverflow.com/questions/191206/how-to-get-list-of-running-applications-using-powershell-or-vbscript)




-------------------------------
## Browser Bookmark Discovery
* [Browser Bookmark Discovery](https://attack.mitre.org/wiki/Technique/T1217)
	* Adversaries may enumerate browser bookmarks to learn more about compromised hosts. Browser bookmarks may reveal personal information about users (ex: banking sites, interests, social media, etc.) as well as details about internal network resources such as servers, tools/dashboards, or other related infrastructure.
	* Browser bookmarks may also highlight additional targets after an adversary has access to valid credentials, especially Credentials in Files associated with logins cached by a browser.
	* Specific storage locations vary based on platform and/or application, but browser bookmarks are typically stored in local files/databases.


-------------------------------
### File and Directory Discovery
* [File and Directory Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1083)
	* Adversaries may enumerate files and directories or may search in specific locations of a host or network share for certain information within a file system. 

#### Linux
* MITRE
	* In Mac and Linux, this kind of discovery is accomplished with the `ls`, `find`, and `locate` commands.
* [find - ss64](https://ss64.com/bash/find.html)
* [Find Files in Linux, Using the Command Line - linode](https://www.linode.com/docs/tools-reference/tools/find-files-in-linux-using-the-command-line/)
* [25 simple examples of Linux find command - binarytides](http://www.binarytides.com/linux-find-command-examples/)
* [The locate Command - linfo](http://www.linfo.org/locate.html)

#### OS X
* MITRE
	* In Mac and Linux, this kind of discovery is accomplished with the `ls`, `find`, and `locate` commands.
* [find - SS64](https://ss64.com/osx/find.html)
* [mdfind - manpagez](https://www.manpagez.com/man/1/mdfind/)

#### Windows
* MITRE
	* Example utilities used to obtain this information are `dir` and `tree`. JPCERT Custom tools may also be used to gather file and directory information and interact with the Windows API. 
* [Microsoft DOS tree command](https://www.computerhope.com/treehlp.htm)
	* Is present on MS DOS -> 10.
* [dir - technet](https://technet.microsoft.com/en-us/library/cc755121(v=ws.11).aspx)
	* Displays a list of a directory's files and subdirectories. If used without parameters, dir displays the disk's volume label and serial number, followed by a list of directories and files on the disk (including their names and the date and time each was last modified). For files, dir displays the name extension and the size in bytes. Dir also displays the total number of files and directories listed, their cumulative size, and the free space (in bytes) remaining on the disk.





### Network Service Scanning
-------------------------------
* [Network Service Scanning - ATT&CK](https://attack.mitre.org/wiki/Technique/T1046)
	* Adversaries may attempt to get a listing of services running on remote hosts, including those that may be vulnerable to remote software exploitation. Methods to acquire this information include port scans and vulnerability scans using tools that are brought onto a system.

#### Windows
* [scanless](https://github.com/vesche/scanless)
	* Command-line utility for using websites that can perform port scans on your behalf. Useful for early stages of a penetration test or if you'd like to run a port scan on a host and have it not come from your IP address.
* [ms15-034.nse Script](https://github.com/pr4jwal/quick-scripts/blob/master/ms15-034.nse)



#### DNS:
DNS
* [Altdns](https://github.com/infosec-au/altdns)
	* Altdns is a DNS recon tool that allows for the discovery of subdomains that conform to patterns. Altdns takes in words that could be present in subdomains under a domain (such as test, dev, staging) as well as takes in a list of subdomains that you know of.
* [AQUATONE](https://github.com/michenriksen/aquatone)
	* AQUATONE is a set of tools for performing reconnaissance on domain names. It can discover subdomains on a given domain by using open sources as well as the more common subdomain dictionary brute force approach. After subdomain discovery, AQUATONE can then scan the hosts for common web ports and HTTP headers, HTML bodies and screenshots can be gathered and consolidated into a report for easy analysis of the attack surface.
* [DNSRecon](https://github.com/darkoperator/dnsrecon)
	* [Quick Reference Guide](http://pentestlab.wordpress.com/2012/11/13/dns-reconnaissance-dnsrecon/)
* [dns-discovery](https://github.com/mafintosh/dns-discovery)
	* Discovery peers in a distributed system using regular dns and multicast dns.
* [dns-parallel-prober](https://github.com/lorenzog/dns-parallel-prober)
	* This script is a proof of concept for a parallelised domain name prober. It creates a queue of threads and tasks each one to probe a sub-domain of the given root domain. At every iteration step each dead thread is removed and the queue is replenished as necessary.
* [DNS Recon](https://github.com/darkoperator/dnsrecon)
* [DNS Dumpster](https://www.dnsdumpster.com)
	* DNSdumpster.com is a free domain research tool that can discover hosts related to a domain. Finding visible hosts from the attackers perspective is an important part of the security assessment process.
* [enumall](https://github.com/Dhayalan96/enumall)
	* Script to enumerate subdomains, leveraging recon-ng. Uses google scraping, bing scraping, baidu scraping, yahoo scarping, netcraft, and bruteforces to find subdomains. Plus resolves to IP.
* [Knockpy](https://github.com/guelfoweb/knock)
	* Knockpy is a python tool designed to enumerate subdomains on a target domain through a wordlist. It is designed to scan for DNS zone transfer and to try to bypass the wildcard DNS record automatically if it is enabled.
* [Sublist3r](https://github.com/aboul3la/Sublist3r)
	* Fast subdomains enumeration tool for penetration testers
* [sub6](https://github.com/YasserGersy/sub6)
	* subdomain take over detector and crawler
* [TXTDNS](http://www.txdns.net/)
	* TXDNS is a Win32 aggressive multithreaded DNS digger. Capable of placing, on the wire, thousands of DNS queries per minute. TXDNS main goal is to expose a domain namespace trough a number of techniques: Typos: Mised, doouble and transposde keystrokes; TLD/ccSLD rotation; Dictionary attack; Full Brute-force attack using alpha, numeric or alphanumeric charsets; Reverse grinding.
* [DNSEnum](https://github.com/fwaeytens/dnsenum)
	* Multithreaded perl script to enumerate DNS information of a domain and to discover non-contiguous ip blocks.


#### Email
Email
* [SIMPLYEMAIL](https://github.com/killswitch-GUI/SimplyEmail)
	* What is the simple email recon tool? This tool was based off the work of theHarvester and kind of a port of the functionality. This was just an expansion of what was used to build theHarvester and will incorporate his work but allow users to easily build Modules for the Framework. Which I felt was desperately needed after building my first module for theHarvester.
* [Swaks - Swiss Army Knife for SMTP](http://www.jetmore.org/john/code/swaks/)



#### Network Host/Service:
Network Host/Service
* [Nmap](http://nmap.org/)
	* Nmap ("Network Mapper") is a free and open source (license) utility for network discovery and security auditing. Many systems and network administrators also find it useful for tasks such as network inventory, managing service upgrade schedules, and monitoring host or service uptime. Nmap uses raw IP packets in novel ways to determine what hosts are available on the network, what services (application name and version) those hosts are offering, what operating systems (and OS versions) they are running, what type of packet filters/firewalls are in use, and dozens of other characteristics. It was designed to rapidly scan large networks, but works fine against single hosts. Nmap runs on all major computer operating systems, and official binary packages are available for Linux, Windows, and Mac OS X. In addition to the classic command-line Nmap executable, the Nmap suite includes an advanced GUI and results viewer (Zenmap), a flexible data transfer, redirection, and debugging tool (Ncat), a utility for comparing scan results (Ndiff), and a packet generation and response analysis tool (Nping). 
* [Enumerator](https://pypi.python.org/pypi/enumerator/0.1.4)
	* enumerator is a tool built to assist in automating the often tedious task of enumerating a target or list of targets during a penetration test.
* [hostmap](https://github.com/jekil/hostmap)
	* hostmap is a free, automatic, hostnames and virtual hosts discovery tool written in Ruby by Alessandro Tanasi
* [Angry IP Scanner](http://angryip.org/)
	* Angry IP Scanner (or simply ipscan) is an open-source and cross-platform network scanner designed to be fast and simple to use. It scans IP addresses and ports as well as has many other features. 
* [UnicornScan](http://www.unicornscan.org/)
	* Unicornscan is a new information gathering and correlation engine built for and by members of the security research and testing communities. It was designed to provide an engine that is Scalable, Accurate, Flexible, and Efficient. It is released for the community to use under the terms of the GPL license. 
* [hping](http://www.hping.org/)
	* hping is a command-line oriented TCP/IP packet assembler/analyzer. The interface is inspired to the ping(8) unix command, but hping isn't only able to send ICMP echo requests. It supports TCP, UDP, ICMP and RAW-IP protocols, has a traceroute mode, the ability to send files between a covered channel, and many other features. 
* [Consul](https://github.com/hashicorp/consul)
	* Consul is a tool for service discovery and configuration. Consul is distributed, highly available, and extremely scalable.
* [CloudFail](https://github.com/m0rtem/CloudFail)
	* CloudFail is a tactical reconnaissance tool which aims to gather enough information about a target protected by CloudFlare in the hopes of discovering the location of the server.
* [discover - Kali Scripts](https://github.com/leebaird/discover)
	* For use with Kali Linux - custom bash scripts used to automate various portions of a pentest.
* [Firewalk](http://packetfactory.openwall.net/projects/firewalk/)
	* Firewalk is an active reconnaissance network security tool that attempts to determine what layer 4 protocols a  given IP forwarding device will pass. Firewalk  works  by sending out TCP or UDP packets with a TTL one greater than the targeted gateway.  If the gateway allows the traffic, it will forward the packets to the next hop where they will expire and elicit an ICMP_TIME_EXCEEDED  message.  If the gateway hostdoes not allow the traffic, it will likely drop the packets on  the floor and we will see no response. To get  the  correct  IP  TTL that will result in expired packets one beyond the gateway we need  to  ramp  up  hop-counts.   We  do  this  in the same manner that traceroute works.  Once we have the gateway hopcount (at  that point the scan is said to be `bound`) we can begin our scan.
* [CiscoRouter - tool](https://github.com/ajohnston9/ciscorouter)
	* CiscoRouter is a tool for scanning Cisco-based routers over SSH. Rules can be created using accompanying CiscoRule application (see this repo) and stored in the "rules" directory.



#### SSH: 
SSH
* [ssh-audit](https://github.com/arthepsy/ssh-audit)
	* SSH server auditing (banner, key exchange, encryption, mac, compression, compatibility, security, etc)




#### SQL:
SQL
* [SQLMap](https://github.com/sqlmapproject/sqlmap)
	* sqlmap is an open source penetration testing tool that automates the process of detecting and exploiting SQL injection flaws and taking over of database servers. It comes with a powerful detection engine, many niche features for the ultimate penetration tester and a broad range of switches lasting from database fingerprinting, over data fetching from the database, to accessing the underlying file system and executing commands on the operating system via out-of-band connections.
* [PowerUpSQL: A PowerShell Toolkit for Attacking SQL Server](https://github.com/NetSPI/PowerUpSQL)
	* The PowerUpSQL module includes functions that support SQL Server discovery, auditing for common weak configurations, and privilege escalation on scale. It is intended to be used during internal penetration tests and red team engagements. However, PowerUpSQL also includes many functions that could be used by administrators to quickly inventory the SQL Servers in their ADS domain.
	* [Documentation](https TLS/SSL Vulnerabilities ://github.com/NetSPI/PowerUpSQL/wiki)
	* [Overview of PowerUpSQL](https://github.com/NetSPI/PowerUpSQL/wiki/Overview-of-PowerUpSQL)


#### Netbios:
Netbios
* [NbtScan](http://www.unixwiz.net/tools/nbtscan.html)
	* This is a command-line tool that scans for open NETBIOS nameservers on a local or remote TCP/IP network, and this is a first step in finding of open shares. It is based on the functionality of the standard Windows tool nbtstat, but it operates on a range of addresses instead of just one. I wrote this tool because the existing tools either didn't do what I wanted or ran only on the Windows platforms: mine runs on just about everything.



#### SMTP:
* [SMTP User Enumeration](https://pentestlab.blog/2012/11/20/smtp-user-enumeration/)
* [Swaks - Swiss Army Knife for SMTP](http://www.jetmore.org/john/code/swaks/)


#### SNMP:
SNMP
* [Onesixtyone](http://www.phreedom.org/software/onesixtyone/)
	* onesixtyone is an SNMP scanner which utilizes a sweep technique to achieve very high performance. It can scan an entire class B network in under 13 minutes. It can be used to discover devices responding to well-known community names or to mount a dictionary attack against one or more SNMP devices.
* [SNMPWALK](http://net-snmp.sourceforge.net/docs/man/snmpwalk.html)
	*  snmpwalk - retrieve a subtree of management values using SNMP GETNEXT requests



#### SIP:
* [A Hitchhiker's Guide to the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc5411)
* [Session Initiation Protocol - Wikipedia](https://en.wikipedia.org/wiki/Session_Initiation_Protocol)
* [sipvicious](https://github.com/EnableSecurity/sipvicious)
* [bluebox-ng](https://github.com/jesusprubio/bluebox-ng)
	* Pentesting framework using Node.js powers, focused in VoIP.




#### MISC:
* [t50 - the fastest packet injector.](https://github.com/fredericopissarra/t50)
	* T50 was designed to perform “Stress Testing”  on a variety of infra-structure
network devices (Version 2.45), using widely implemented protocols, and after
some requests it was was re-designed to extend the tests (as of Version 5.3),
covering some regular protocols (ICMP,  TCP  and  UDP),  some infra-structure
specific protocols (GRE,  IPSec  and  RSVP), and some routing protocols (RIP,
EIGRP and OSPF).
* [gateway-finder](https://github.com/pentestmonkey/gateway-finder)
	* Gateway-finder is a scapy script that will help you determine which of the systems on the local LAN has IP forwarding enabled and which can reach the Internet.
* [a](https://github.com/fmtn/a)
	* ActiveMQ CLI testing and message management
* [OnionScan](https://github.com/s-rah/onionscan)
	* [What OnionScan Scans for](https://github.com/s-rah/onionscan/blob/master/doc/what-is-scanned-for.md)






#### Web:
Web
* [WPScan](https://github.com/wpscanteam/wpscan)
	* WPScan is a black box WordPress vulnerability scanner.
* [WhatWeb](https://github.com/urbanadventurer/WhatWeb)
	* WhatWeb identifies websites. Its goal is to answer the question, "What is that Website?". WhatWeb recognises web technologies including content management systems (CMS), blogging platforms, statistic/analytics packages, JavaScript libraries, web servers, and embedded devices. WhatWeb has over 1500 plugins, each to recognise something different. WhatWeb also identifies version numbers, email addresses, account IDs, web framework modules, SQL errors, and more.
* [webDisco](https://github.com/joeybelans/webDisco)
	* Web discovery tool to capture screenshots from a list of hosts & vhosts.  Requests are made via IP address and vhosts to determine differences. Additionallty checks for common administrative interfaces and web server  misconfigurations.
* [w3af](https://github.com/andresriancho/w3af)
	* w3af: web application attack and audit framework, the open source web vulnerability scanner.
* [Tachyon](https://github.com/delvelabs/tachyon)
	* Tachyon is a Fast Multi-Threaded Web Discovery Tool
* [dirsearch](https://github.com/maurosoria/dirsearch)
	* dirsearch is a simple command line tool designed to brute force directories and files in websites.
* [virtual-host-discovery](https://github.com/jobertabma/virtual-host-discovery)
	* This is a basic HTTP scanner that'll enumerate virtual hosts on a given IP address. During recon, this might help expand the target by detecting old or deprecated code. It may also reveal hidden hosts that are statically mapped in the developer's /etc/hosts file.
* [RAWR - Rapid Assessment of Web Resources](https://bitbucket.org/al14s/rawr/wiki/Home)
* [blacksheepwall](https://github.com/tomsteele/blacksheepwall)
	* blacksheepwall is a hostname reconnaissance tool
* [virtual-host-discovery](https://github.com/jobertabma/virtual-host-discovery)
	* This is a basic HTTP scanner that'll enumerate virtual hosts on a given IP address. During recon, this might help expand the target by detecting old or deprecated code. It may also reveal hidden hosts that are statically mapped in the developer's /etc/hosts file.





## Network Share Discovery
-------------------------------
* [Network Share Discovery - ATT&CK](Network Share Discovery)
	* Networks often contain shared network drives and folders that enable users to access file directories on various systems across a network. 

#### Linux

#### OS X
* MITRE
	*  On Mac, locally mounted shares can be viewed with the `df -aH` command.
* [How to list network shared items in terminal - SuperUser](https://superuser.com/questions/376914/how-to-list-network-shared-items-in-terminal)

#### Windows
* MITRE
	* File sharing over a Windows network occurs over the SMB protocol.Wikipedia Shared ResourceTechNet Shared Folder 
	* Net can be used to query a remote system for available shared drives using the net view \\remotesystem command. It can also be used to query shared drives on the local system using `net share`.
	* Adversaries may look for folders and drives shared on remote systems as a means of identifying sources of information to gather as a precursor for Collection and to identify potential systems of interest for Lateral Movement.  
* [Get-SmbShare](https://technet.microsoft.com/en-us/library/jj635704(v=wps.630).aspx)
	* Retrieves the Server Message Block (SMB) shares on the computer.
* [NetResView](http://www.nirsoft.net/utils/netresview.html)
	* NetResView is a small utility that displays the list of all network resources (computers, disk shares, and printer shares) on your LAN. As opposed to "My Network Places" module of Windows, NetResView display all network resources from all domains/workgroups in one screen, and including admin/hidden shares. 
* [Can you use a powershell script to find all shares on servers? - serverfault](https://serverfault.com/questions/623710/can-you-use-a-powershell-script-to-find-all-shares-on-servers)
* [Find shares with PowerShell where Everyone has Full Control permissions](https://4sysops.com/archives/find-shares-with-powershell-where-everyone-has-full-control-permissions/)
* [Obtain a list of non-admin file shares from multiple Windows servers](https://stackoverflow.com/questions/33873961/obtain-a-list-of-non-admin-file-shares-from-multiple-windows-servers)
* [Nmap NSE - smb-enum-shares](https://nmap.org/nsedoc/scripts/smb-enum-shares.html)
	*  Attempts to list shares using the srvsvc.NetShareEnumAll MSRPC function and retrieve more information about them using srvsvc.NetShareGetInfo. If access to those functions is denied, a list of common share names are checked.  Running NetShareEnumAll will work anonymously against Windows 2000, and requires a user-level account on any other Windows version. Calling NetShareGetInfo requires an administrator account on all versions of Windows up to 2003, as well as Windows Vista and Windows 7, if UAC is turned down. Even if NetShareEnumAll is restricted, attempting to connect to a share will always reveal its existence. So, if NetShareEnumAll fails, a pre-generated list of shares, based on a large test network, are used. If any of those succeed, they are recorded. 
* [List Shares in Windows w/ PowerShell](http://krypted.com/windows-server/list-shares-in-windows-w-powershell/)
* 
```
The command, from PowerShell would be something similar to the following:

    get-WmiObject -class Win32_Share 

Assuming communication is working as intended, you can also query for the shares of other systems, by adding a -computer switch and specifying the host you’re listing shares on, as follows:

    get-WmiObject -class Win32_Share -computer dc1.krypted.com

One can also list shared printers with a little trickeration in the {} side of things:
get-WmiObject -list | where {$_.name -match “Printer”}
```





-------------------------------
## Password Policy Discovery
* [Password Policy Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1201)
	* Password policies for networks are a way to enforce complex passwords that are difficult to guess or crack through Brute Force. An adversary may attempt to access detailed information about the password policy used within an enterprise network. This would help the adversary to create a list of common passwords and launch dictionary and/or brute force attacks which adheres to the policy (e.g. if the minimum password length should be 8, then not trying passwords such as 'pass123'; not checking for more than 3-4 passwords per account if the lockout is set to 6 as to not lock out accounts).
	* Password policies can be set and discovered on Windows, Linux, and macOS systems.









-------------------------------
## Peripheral Device Discovery
* [Peripheral Device Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1120)
	* Adversaries may attempt to gather information about attached peripheral devices and components connected to a computer system. The information may be used to enhance their awareness of the system and network environment or may be used for further actions.

#### Linux

#### OS X

#### Windows
* [USBView](https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/usbview)
	* USBView (Universal Serial Bus Viewer, Usbview.exe) is a Windows graphical user interface application that enables you to browse all USB controllers and connected USB devices on your computer. USBView works on all versions of Windows.
* [How to Analyze USB Device History in Windows](https://www.magnetforensics.com/computer-forensics/how-to-analyze-usb-device-history-in-windows/)
* [USBDeview v2.71](http://www.nirsoft.net/utils/usb_devices_view.html)
	* USBDeview is a small utility that lists all USB devices that currently connected to your computer, as well as all USB devices that you previously used. For each USB device, extended information is displayed: Device name/description, device type, serial number (for mass storage devices), the date/time that device was added, VendorID, ProductID, and more... 
* [Displaying USB Devices using WMI - blogs.msdn](https://blogs.msdn.microsoft.com/powershell/2007/02/24/displaying-usb-devices-using-wmi/)
* [Where can I find logs on recent USB insertion in the Event Viewer? - SuperUser](https://superuser.com/questions/1096887/where-can-i-find-logs-on-recent-usb-insertion-in-the-event-viewer)
* [How to capture a USB event trace with Logman](https://msdn.microsoft.com/en-us/library/windows/hardware/jj151573(v=vs.85).aspx)



## Permission Groups Discovery
-------------------------------
* [Permissions Groups Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1069)
	* Adversaries may attempt to find local system or domain-level groups and permissions settings. 

#### Linux
* MITRE
	* On Linux, local groups can be enumerated with the `groups` command and domain groups via the `ldapsearch` command.
* [Linux / Unix: groups Command Examples](https://www.cyberciti.biz/faq/unix-linux-groups-command-examples-syntax-usage/)
* [Linux Users and Groups](https://www.linode.com/docs/tools-reference/linux-users-and-groups/)
* [Managing Group Access](http://www.yolinux.com/TUTORIALS/LinuxTutorialManagingGroups.html)
* [Using ldapsearch](https://www.centos.org/docs/5/html/CDS/ag/8.0/Finding_Directory_Entries-Using_ldapsearch.html)
* [LDAP Command-Line Tools](https://docs.oracle.com/cd/B10501_01/network.920/a96579/comtools.htm)
* [Querying an LDAP server from the command line with ldap-utils: ldapsearch, ldapadd, ldapmodify](http://www.vinidox.com/ldap/querying-an-ldap-server-from-the-command-line-with-ldap-utils-ldapsearch-ldapadd-ldapmodify/)


#### OS X
* MITRE
	* On Mac, this same thing can be accomplished with the `dscacheutil -q group` for the domain, or `dscl . -list /Groups` for local groups. 
* `dscl . list /Users`
* `dscl . list /Groups`


#### Windows
* MITRE
	* Examples of commands that can list groups are `net group /domain` and `net localgroup` using the Net utility.
* [Local Users and Groups overview - technet](https://technet.microsoft.com/en-us/library/cc770756(v=ws.11).aspx)
* [Managing Permissions - technet](https://technet.microsoft.com/en-us/library/cc770962(v=ws.11).aspx)
* [Windows: View “all” permissions of a specific user or group](https://superuser.com/questions/613160/windows-view-all-permissions-of-a-specific-user-or-group)
* [BloodHound](https://github.com/BloodHoundAD/BloodHound)
	* BloodHound is a single page Javascript web application, built on top of Linkurious, compiled with Electron, with a Neo4j database fed by a PowerShell ingestor. BloodHound uses graph theory to reveal the hidden and often unintended relationships within an Active Directory environment. Attackers can use BloodHound to easily identify highly complex attack paths that would otherwise be impossible to quickly identify. Defenders can use BloodHound to identify and eliminate those same attack paths. Both blue and red teams can use BloodHound to easily gain a deeper understanding of privilege relationships in an Active Directory environment.






## Process Discovery
-------------------------------
* [Process Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1057)
	* Adversaries may attempt to get information about running processes on a system. Information obtained could be used to gain an understanding of common software running on systems within the network. 


#### Linux
* MITRE
	*  In Mac and Linux, this is accomplished with the `ps` command.
* [ps manpage](https://linux.die.net/man/1/ps)
* [How To Use ps, kill, and nice to Manage Processes in Linux](https://www.digitalocean.com/community/tutorials/how-to-use-ps-kill-and-nice-to-manage-processes-in-linux)
* [30 Useful ‘ps Command’ Examples for Linux Process Monitoring](https://www.tecmint.com/ps-command-examples-for-linux-process-monitoring/)

#### OS X
* MITRE
	*  In Mac and Linux, this is accomplished with the `ps` command.
* [ps - SS64](https://ss64.com/osx/ps.html)
* [top - SS64](https://ss64.com/osx/top.html)

#### Windows
* MITRE
	* An example command that would obtain details on processes is `"tasklist"` using the Tasklist utility. 	
* [TASKLIST - SS64](https://ss64.com/nt/tasklist.html)
	* TaskList displays all running applications and services with their Process ID (PID) This can be run on either a local or a remote computer.
* [Use WMIC to list processes](https://quux.wiki.zoho.com/WMIC-Snippets.html#Processes)
* [Get-Process - msdn](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-process?view=powershell-5.1)
	* Gets the processes that are running on the local computer or a remote computer.
* [Using the Get-Process Cmdlet - technet](https://technet.microsoft.com/en-us/library/ee176855.aspx)
* [Windows PowerShell Examples Featuring Get-Process](https://www.reddit.com/r/netsec/comments/3goktw/obtaining_domain_administrator_credentials_in_17/)
* [Linux “Top” command for Windows Powershell? - superuser](https://superuser.com/questions/176624/linux-top-command-for-windows-powershell)
* [How do you list all processes on the command line in Windows? - SuperUser](https://superuser.com/questions/914782/how-do-you-list-all-processes-on-the-command-line-in-windows)






## Query Registry
-------------------------------
* [Query Registry - ATT&CK](https://attack.mitre.org/wiki/Technique/T1012)
	* Adversaries may interact with the Windows Registry to gather information about the system, configuration, and installed software. The Registry contains a significant amount of information about the operating system, configuration, software, and security.Wikipedia Windows Registry Some of the information may help adversaries to further their operation within a network. 

#### Windows
* [Windows Registry - Wikipedia](https://en.wikipedia.org/wiki/Windows_Registry)
* [Reg - technet](https://technet.microsoft.com/en-us/library/cc732643.aspx)
* [Reg query](https://technet.microsoft.com/en-us/library/cc742028(v=ws.11).aspx)
* [How do I read values of registry keys? - superuser](https://superuser.com/questions/1117040/how-do-i-read-values-of-registry-keys)
* [Using the Get-ItemProperty Cmdlet - technet](https://technet.microsoft.com/en-us/library/ee176852.aspx)
* [Working with Registry Keys - ms docs](https://docs.microsoft.com/en-us/powershell/scripting/getting-started/cookbooks/working-with-registry-keys?view=powershell-5.1)
* [How can I get the value of a registry key from within a batch script? - stackoverflow](https://stackoverflow.com/questions/445167/how-can-i-get-the-value-of-a-registry-key-from-within-a-batch-script)







## Remote System Discovery
-------------------------------
* [Remote System Discovery](https://attack.mitre.org/wiki/Technique/T1018)
	* Adversaries will likely attempt to get a listing of other systems by IP address, hostname, or other logical identifier on a network that may be used for Lateral Movement from the current system. Functionality could exist within remote access tools to enable this, but utilities available on the operating system could also be used. 

#### Linux
* MITRE
	*  Utilities such as `"ping"` and others can be used to gather information about remote systems.
* `ping`, `arp`, etc.

#### OS X
* Specific to Mac, the bonjour protocol to discover additional Mac-based systems within the same broadcast domain. Utilities such as `"ping"` and others can be used to gather information about remote systems. 

#### Windows
* MITRE
 * Examples of tools and commands that acquire this information include `"ping"` or `"net view"` using Net. 

#### Windows
* Check .hosts file for mappings ; C:\Windows\System32\Drivers\etc\hosts
* [arp](https://technet.microsoft.com/en-us/library/cc940107.aspx)
* [Port scan subnets with PSnmap for PowerShell](http://www.powershelladmin.com/wiki/Port_scan_subnets_with_PSnmap_for_PowerShell)
* [PowerView](https://github.com/PowerShellMafia/PowerSploit/tree/master/Recon)
	* PowerView is a PowerShell tool to gain network situational awareness on Windows domains. It contains a set of pure-PowerShell replacements for various windows ".net * "" commands, which utilize PowerShell AD hooks and underlying Win32 API functions to perform useful Windows domain functionality.
* [Invoke-HostEnum.ps1](https://github.com/minisllc/red-team-scripts/blob/master/Invoke-HostEnum.ps1)
	* Performs local host and/or domain enumeration for situational awareness
* [Network Situational Awareness with Empire](http://www.powershellempire.com/?page_id=289)






## Security Software Discovery
-------------------------------
* [Security Software Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1063)
	* Adversaries may attempt to get a listing of security software, configurations, defensive tools, and sensors that are installed on the system. This may include things such as local firewall rules, anti-virus, and virtualization. These checks may be built into early-stage remote access tools. 

#### OS X
* MITRE
	* It's becoming more common to see macOS malware perform checks for LittleSnitch and KnockKnock software.

#### Windows
* MITRE
	* Example commands that can be used to obtain security software information are netsh, `reg query` with Reg, `dir` with cmd, and Tasklist, but other indicators of discovery behavior may be more specific to the type of software or security system the adversary is looking for. 
* [Use Powershell to quickly find installed Software](https://blogs.technet.microsoft.com/heyscriptingguy/2011/11/13/use-powershell-to-quickly-find-installed-software/)
* [Netsh AdvFirewall Firewall Commands - technet](https://technet.microsoft.com/en-us/library/dd734783(v=ws.10).aspx)
	* netsh advfirewall monitor show firewall rule name=all dir=in
* [Information about installed antivirus software on local or remote machines - gallery.technet](https://gallery.technet.microsoft.com/scriptcenter/Information-about-bf8b201f)
	* Script is checking status of installed avtivirus software on local or remote machine(s).Script is using WMI query to get information of installed antivirus products.At the moment there is support for Windows XP SP3, Vista SP2, 7, 8, 8.1 and 10.
* [Powershell : How to get Antivirus product details - stackoverflow](https://stackoverflow.com/questions/33649043/powershell-how-to-get-antivirus-product-details)
* [Getting the installed Antivirus, AntiSpyware and Firewall software using Delphi and the WMI - 2011](https://theroadtodelphi.com/2011/02/18/getting-the-installed-antivirus-antispyware-and-firewall-software-using-delphi-and-the-wmi/)
* [Listing Windows Firewall Rules Using Microsoft PowerShell](http://carlwebster.com/listing-windows-firewall-rules-using-microsoft-powershell/)
* [Get-NetFirewallRule - technet](https://technet.microsoft.com/en-us/library/jj554860(v=wps.630).aspx)
	* Retrieves firewall rules from the target computer.







## System Information Discovery
-------------------------------
* [System Information Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1082)
	* An adversary may attempt to get detailed information about the operating system and hardware, including version, patches, hotfixes, service packs, and architecture. 

#### Linux

#### OS X
* MITRE
	*  On Mac, the systemsetup command gives a detailed breakdown of the system, but it requires administrative privileges. Additionally, the `system_profiler` gives a very detailed breakdown of configurations, firewall rules, mounted volumes, hardware, and many other things without needing elevated permissions.
* [Get OS X System Info from the Command Line](http://teczd.com/2015/09/23/osx-get-system-info-from-command-line/)
* [Using System Profiler in Terminal](http://macstuff.beachdogs.org/blog/?p=21)
* [Orchard](https://github.com/its-a-feature/Orchard)
	* Live off the land for macOS. This program allows users to do Active Directory enumeration via macOS' JXA (JavaScript for Automation) code. This is the newest version of AppleScript, and thus has very poor documentation on the web.


#### Windows
* MITRE
	* Example commands and utilities that obtain this information include `ver`, `Systeminfo`, and `dir` within cmd for identifying information based on present files and directories. 
* [Systeminfo - technet](https://technet.microsoft.com/en-us/library/bb491007.aspx)
	* Displays detailed configuration information about a computer and its operating system, including operating system configuration, security information, product ID, and hardware properties, such as RAM, disk space, and network cards.
* [GetSystemInfo function - msdn](https://msdn.microsoft.com/en-us/library/windows/desktop/ms724381(v=vs.85).aspx)
	* Retrieves information about the current system.
* [Use PowerShell to Quickly Find Installed Software - technet](https://blogs.technet.microsoft.com/heyscriptingguy/2011/11/13/use-powershell-to-quickly-find-installed-software/)
* [How to use System Information (MSINFO32) command-line tool switches - ms support](https://support.microsoft.com/en-us/help/300887/how-to-use-system-information-msinfo32-command-line-tool-switches)
* [How to view all your installed programs with one mighty PowerShell command](http://www.fixedbyvonnie.com/2014/07/view-installed-programs-one-powershell-command/)











## System Network Configuration Discovery
-------------------------------
* [System Network Configuration Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1016)
	* Adversaries will likely look for details about the network configuration and settings of systems they access or through information discovery of remote systems. Several operating system administration utilities exist that can be used to gather this information. Examples include Arp, ipconfig/ifconfig, nbtstat, and route. 

#### Linux

#### OS X
* [systemsetup - SS64](https://ss64.com/osx/systemsetup.html)

#### Windows
* [Netstat - technet](https://technet.microsoft.com/en-us/library/bb490947.aspx)
	* Displays active TCP connections, ports on which the computer is listening, Ethernet statistics, the IP routing table, IPv4 statistics (for the IP, ICMP, TCP, and UDP protocols), and IPv6 statistics (for the IPv6, ICMPv6, TCP over IPv6, and UDP over IPv6 protocols). Used without parameters, netstat displays active TCP connections.
* [Listing Windows Firewall Rules Using Microsoft PowerShell](http://carlwebster.com/listing-windows-firewall-rules-using-microsoft-powershell/)
* [Arp - technet](https://technet.microsoft.com/en-us/library/cc940107.aspx)
	* Arp allows you to view and modify the ARP cache. 
* [Route - technet](https://technet.microsoft.com/en-us/library/bb490991.aspx)
	* Displays and modifies the entries in the local IP routing table. Used without parameters, route displays help.
* [NetBIOS over TCP/IP - Wikipedia](https://en.wikipedia.org/wiki/NetBIOS_over_TCP/IP)
* [Nbtstat - technet](https://technet.microsoft.com/en-us/library/cc940106.aspx)
	* Nbtstat is designed to help troubleshoot NetBIOS name resolution problems. When a network is functioning normally, NetBIOS over TCP/IP (NetBT) resolves NetBIOS names to IP addresses. It does this through several options for NetBIOS name resolution, including local cache lookup, WINS server query, broadcast, LMHOSTS lookup, Hosts lookup, and DNS server query.
* [Ipconfig](https://technet.microsoft.com/en-us/library/cc940124.aspx)
	* IPConfig is a command-line tool that displays the current configuration of the installed IP stack on a networked computer.









## System Network Connections Discovery
-------------------------------
* [System Network Connections Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1049)
	* Adversaries may attempt to get a listing of network connections to or from the compromised system they are currently accessing or from remote systems by querying for information over the network. 

#### Linux
* MITRE
	* In Mac and Linux, `netstat` and `lsof` can be used to list current connections. `who -a` and `w` can be used to show which users are currently logged in, similar to "net session".
#### OS X
* `lsof -i`
* [How to find the currently connected network service from the command line? - StackOverflow](https://apple.stackexchange.com/questions/191879/how-to-find-the-currently-connected-network-service-from-the-command-line)

#### Windows
* MITRE
	* Utilities and commands that acquire this information include netstat, "net use," and "net session" with Net. 
* [Netstat - technet](https://technet.microsoft.com/en-us/library/bb490947.aspx)
	* Displays active TCP connections, ports on which the computer is listening, Ethernet statistics, the IP routing table, IPv4 statistics (for the IP, ICMP, TCP, and UDP protocols), and IPv6 statistics (for the IPv6, ICMPv6, TCP over IPv6, and UDP over IPv6 protocols). Used without parameters, netstat displays active TCP connections.
* [netstat - Wikipedia](https://en.wikipedia.org/wiki/Netstat)








## System Owner/User Discovery
-------------------------------
* [System Owner/User Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1033)
	* Adversaries may attempt to identify the primary user, currently logged in user, set of users that commonly uses a system, or whether a user is actively using the system. They may do this, for example, by retrieving account usernames or by using Credential Dumping. The information may be collected in a number of different ways using other Discovery techniques, because user and username details are prevalent throughout a system and include running process ownership, file/directory ownership, session information, and system logs. 

##### Linux
* MITRE
	* On Linux, the currently logged in user can be identified with w and who.

#### OS X
* MITRE
	* On Mac, the currently logged in user can be identified with ***users***,***w***, and ****who****. 

##### Windows
* MITRE
	* Adversaries may attempt to identify the primary user, currently logged in user, set of users that commonly uses a system, or whether a user is actively using the system. They may do this, for example, by retrieving account usernames or by using Credential Dumping. The information may be collected in a number of different ways using other Discovery techniques, because user and username details are prevalent throughout a system and include running process ownership, file/directory ownership, session information, and system logs. 
* [List All User Accounts on a Windows System via Command Line](https://superuser.com/questions/608931/list-all-user-accounts-on-a-windows-system-via-command-line)
* [WINDOWS ENUMERATION: USERINFO AND USERDUMP - old](http://www.carnal0wnage.com/papers/userinfouserdump.pdf)
* [How To Accurately Enumerate Windows User Profiles With PowerShell](https://blog.ipswitch.com/how-to-accurately-enumerate-windows-user-profiles-with-powershell)




## System Service Discovery
-------------------------------
* [System Service Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1007)
	* Adversaries may try to get information about registered services. Commands that may obtain information about services using operating system utilities are "sc," "tasklist /svc" using Tasklist, and "net start" using Net, but adversaries may also use other tools as well. 

#### Linux
* [Red Hat / CentOS: Check / List Running Services](https://www.cyberciti.biz/faq/check-running-services-in-rhel-redhat-fedora-centoslinux/)
* Ubuntu/Debian-based - `services --status-all`

#### OS X
#### Windows
* [Net Commands On Windows Operating Systems - support ms](https://support.microsoft.com/en-us/help/556003)
* [NET.exe - ss64](https://ss64.com/nt/net-service.html)
* [SC - technet](https://technet.microsoft.com/en-us/library/bb490995.aspx)
	* Communicates with the Service Controller and installed services. SC.exe retrieves and sets control information about services. You can use SC.exe for testing and debugging service programs. Service properties stored in the registry can be set to control how service applications are started at boot time and run as background processes. SC.exe parameters can configure a specific service, retrieve the current status of a service, as well as stop and start a service. You can create batch files that call various SC.exe commands to automate the startup or shutdown sequence of services. SC.exe provides capabilities similar to Services in the Administrative Tools item in Control Panel. 
* [Tasklist](https://technet.microsoft.com/en-us/library/bb491010.aspx)
	* Displays a list of applications and services with their Process ID (PID) for all tasks running on either a local or a remote computer.



## System Time Discovery
------------------------------
* [System Time Discovery - ATT&CK](https://attack.mitre.org/wiki/Technique/T1124)
	* The system time is set and stored by the Windows Time Service within a domain to maintain time synchronization between systems and services in an enterprise network.MSDN System TimeTechnet Windows Time Service An adversary may gather the system time and/or time zone from a local or remote system. This information may be gathered in a number of ways, such as with Net on Windows by performing `net time \\hostname` to gather the system time on a remote system. The victim's time zone may also be inferred from the current system time or gathered by using `w32tm /tz`. Time Service The information could be useful for performing other techniques, such as executing a file with a Scheduled TaskRSA EU12 They're Inside, or to discover locality information based on time zone to assist in victim targeting.

#### Linux
* `date` command

#### OS X

#### Windows
* [W32tm - technet](https://technet.microsoft.com/en-us/library/bb491016.aspx)
	* A tool used to diagnose problems occurring with Windows Time
* [W32tm](https://technet.microsoft.com/en-us/library/ff799054(v=ws.11).aspx)
	* W32tm command reference










