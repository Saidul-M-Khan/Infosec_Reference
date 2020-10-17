# Building a Lab

-------------------------
## Table of Contents
- [General Info](#general)
	- [101](#101)
- [Virtual Machines](#vm)
- [Vulnerable Web Applications](#webapp)
	- [OWASP](#owasp)
	- [General](#general)
	- [Specific](#specific)
		- [API](#sapi)
		- [Django](#sdj)
		- [HTTP Smuggling](#shtt)
		- [JSP](#sjsp)
		- [Node.js](#sno)
		- [Ruby](#sruby)
		- [SSRF](#ssrf)
		- [SSO](#ssso)
		- [Web Cache Poisoning](#swcp)
- [Installing/Configuring Active Directory](#AD)
	- [Official Documentation](#adoc)
	- [Guides](#guides)
	- [Lab Generation](#alabgen)
	- [Domain Generation](#adg)
	- [Forest Generation](#afg)
	- [User Generation](#aug)
	- [User Activity Simulation](#aus)
- [Building a Pentest Lab](#pentest)
	- [Talks & Presentations](#bltalks)
	- [Tools](#bltools)
	- [In the Cloud](#clouds)
- [Building a Defensive Lab](#defense)
- [Other Labs](#other)
	- [Access Methods](#oam)
	- [Containers/Related](#ocr)
- [Infrastructure Automation](#infra)
	- [101](#i101)
	- [Tooling](#infrauto)



* **To Do**
	* Building a defensive Lab
	* Infra Automation
-------------------------
### <a name="general"></a> General
* **101**<a name="101"></a>
	* This page is supposed to be a collection of resources for building a lab for performing various security related tasks. Generally, the idea is that you setup a local VM hypervisor software(VMware, Virtualbox) and then install a virtual machine to perform testing and analysis without any impact to your "physical" machine.
* **Useful links**
	* [Warming Up. Using ATT&CK for Self Advancement - 	Adam Swan](https://socprime.com/en/blog/warming-up-using-attck-for-self-advancement/)
* **Building a Dropbox**
	* **Articles/Blogposts/Writeups**
		* [DigiDucky - How to setup a Digispark like a rubber ducky](http://www.redteamr.com/2016/08/digiducky/)
		* [How to Build Your Own Penetration Testing Drop Box - BHIS](https://www.blackhillsinfosec.com/?p=5156&)
	* **Talks/Presentations/Videos**
	* **Tools**
		* [ubuntu.autossh](https://github.com/Monadical-SAS/ubuntu.autossh)
			* Autossh reverse tunnel to central server.
		* [P4wnP1](https://github.com/mame82/P4wnP1)
			* P4wnP1 is a highly customizable USB attack platform, based on a low cost Raspberry Pi Zero or Raspberry Pi Zero W.
* **Utilities**
	* **FFSend**
		* [Deployment](https://github.com/mozilla/send/blob/master/docs/deployment.md)
			* This document describes how to do a full deployment of Firefox Send on your own Linux server.
		* [ffsend](https://github.com/timvisee/ffsend)
			* Easily and securely share files from the command line. A fully featured Firefox Send client. 





















-------------------------
### <a name="vm"></a> Virtual Labs/Machines
* **101**
	* [Virtual Machine - Wikipedia](https://en.wikipedia.org/wiki/Virtual_machine)
* **VM Hypervisor Software**
	* **Desktop**
		* [Oracle VirtualBox - free](https://www.virtualbox.org/)
		* [VMware Workstation - paid](https://www.vmware.com/products/workstation-pro.html)
	* **Server**
		* [Proxmox - free](https://www.proxmox.com/en/)
		* [VMware vSphere - free](https://www.vmware.com/products/vsphere-hypervisor.html)
		* [Xen - free](https://www.xenproject.org/)
* **VirtualBox
* **VMware(Workstation/vSphere/ESXi)**
	* **VM Snapshots**
		* [Understanding VM snapshots in ESXi (1015180) - vmware.com](https://kb.vmware.com/s/article/1015180)
		* [How to Manage VMware Snapshots - Vladan Seget](https://blog.netwrix.com/2019/12/23/how-to-manage-vmware-snapshots/)
		* [Deep Dive – The Ultimate Guide to Master VMware Snapshot - Mohammed Rafic](http://www.vmwarearena.com/deep-dive-the-ultimate-guide-to-master-vmware-snapshot/)
* **Xen**
* **Obtaining VMs**
	* [Internet Explorer Windows Vista through 10 Virtual Machines](https://github.com/mikescott/ie-virtual-machines/blob/master/README.md)
	* [Windows Server Evaluation ISOs](https://www.microsoft.com/en-us/evalcenter/)
	* [Vulnhub](https://www.Vulnhub.com)
		* Vulnhub is a website dedicated to cataloging various vulnerable VMs from across the web. It also has a healthy community that creates and submits new VMs on a regular basis. As I write this now, I believe there is around 100 or so different VMs on Vulnhub, so you have a bit of variation.
	* [macOS-Simple-KVM](https://github.com/foxlet/macOS-Simple-KVM)
		* Documentation to set up a simple macOS VM in QEMU, accelerated by KVM.
	* [unlocker](https://github.com/DrDonk/unlocker)
		* VMware Workstation macOS
	* [Running macOS Catalina Beta on VirtualBox Linux - Astr0baby](https://astr0baby.wordpress.com/2019/07/04/running-macos-catalina-beta-on-virtualbox-linux/)
	* [macos-virtualbox](https://github.com/myspaghetti/macos-virtualbox)
		* macos-guest-virtualbox.sh is a Bash script that creates a macOS virtual machine guest on VirtualBox with unmodified macOS installation files downloaded directly from Apple servers. Tested on Cygwin. Works on macOS, Windows Subsystem for Linux, and centOS 7. Should work on most modern Linux distros.
	* [How to create a macOS virtual machine in VmWare Fusion on Mac without a CD, USB drive or recovery partition - Oleksii Chekulaiev(2017)](https://medium.com/@achekulaev/how-to-create-a-macos-virtual-machine-in-vmware-fusion-on-mac-without-a-cd-usb-drive-or-a-recovery-cb942d821654)
* **Automated Lab/Machine Creation Tools**
	* **Talks/Videos**
		* [Windows Server 2016 AutoLab Setup - Jason Helmick(2016)](https://www.youtube.com/watch?v=fIXHvbgxEDk&feature=youtu.be)
			* Join Pluralsight author Jason Helmick as he walks through his automated lab setup for use in our Windows Server 2016 content. Check out how to build your lab environment so you can follow along with our authors as you learn the ins and outs of Windows Server 2016.
	* **General**
		* Security Scenario Generator (SecGen)](https://github.com/cliffe/SecGen)
			* SecGen creates vulnerable virtual machines so students can learn security penetration testing techniques. Boxes like Metasploitable2 are always the same, this project uses Vagrant, Puppet, and Ruby to create randomly vulnerable virtual machines that can be used for learning or for hosting CTF events.
	* **Malware**
		* [Set up your own malware analysis lab with VirtualBox, INetSim and Burp - Christophe Tafani-Dereeper](https://blog.christophetd.fr/malware-analysis-lab-with-virtualbox-inetsim-and-burp/)
		* [CyRIS: Cyber Range Instantiation System](https://github.com/crond-jaist/cyris)
			* CyRIS is a tool for facilitating cybersecurity training by automating the creation and management of the corresponding training environments (a.k.a, cyber ranges) based on a description in YAML format. CyRIS is being developed by the Cyber Range Organization and Design (CROND) NEC-endowed chair at the Japan Advanced Institute of Science and Technology (JAIST).
		* [DockerSecurityPlayground](https://github.com/giper45/DockerSecurityPlayground)
			* A Microservices-based framework for the study of Network Security and Penetration Test techniques
	* **Windows**
		* [PSAutoLab](https://github.com/pluralsight/PS-AutoLab-Env)
			* This project serves as a set of "wrapper" commands that utilize the Lability module which is a terrific tool for creating a lab environment of Windows based systems. The downside is that it is a difficult module for less experienced PowerShell users. The configurations and control commands for the Hyper-V virtual machines are written in PowerShell using Desired State Configuration (DSC) and deployed via Lability.
		* [Lability](https://github.com/VirtualEngine/Lability)
			* The Lability module enables simple provisioning of Windows Hyper-V development and testing environments. It uses a declarative document for machine configuration. However, rather than defining configurations in an external custom domain-specific language (DSL) document, Lability extends existing PowerShell Desired State Configuration (DSC) configuration (.psd1) documents with metadata that can be interpreted by the module. By using this approach, it allows the use of a single configuration document to describe all properties for provisioning Windows-centric development and/or test environments.
		* [Detection Lab](https://github.com/clong/DetectionLab)
			* Vagrant & Packer scripts to build a lab environment complete with security tooling and logging best practices. This lab has been designed with defenders in mind. Its primary purpose is to allow the user to quickly build a Windows domain that comes pre-loaded with security tooling and some best practices when it comes to system logging configurations. It can easily be modified to fit most needs or expanded to include additional hosts.
		* [DetectionLabELK](https://github.com/cyberdefenders/DetectionLabELK)
			* DetectionLabELK is a fork from DetectionLab with ELK stack instead of Splunk. 
* **VMs/Apps Designed to be Attacked**
	* [List of VMs that are preconfigured virtual machines](http://www.amanhardikar.com/mindmaps/PracticeUrls.html)
	* [The Hacker Games - Hack the VM before it hacks you](http://www.scriptjunkie.us/2012/04/the-hacker-games/)
		* I have talked about counterattacks here before, and this system has implemented a number of aggressive anti-hacker measures.  In fact, this VM is downright evil. I am probably legally obligated to tell you that it will try to hack you. So if a calculator or message declaring your pwnedness pops up or shows up on your desktop, you asked for it. But don’t worry, it won’t steal your docs or rm you, it will just demonstrate compromise for the game.  To save precious bandwidth, this has been implemented in a minimal tinycore-based VM, and will require VirtualBox to run.
	* **Android**
		* [EVABS (Extremely Vulnerable Android Labs)](https://github.com/abhi-r3v0/EVABS)
			* An open source Android application that is intentionally vulnerable so as to act as a learning platform for Android application security beginners. The effort is to introduce beginners with very limited or zero knowledge to some of the major and commonly found real-world based Android application vulnerabilities in a story-based, interactive model. EVABS follows a level-wise difficulty approach and in each level, the player learns a new concept. This project is still under progress and aims at incorporating as many levels as possible.
	* **AWS**
		* [AWS Well-Architected Security Labs - Amazon(Official)](https://www.wellarchitectedlabs.com/Security/README.html)
			* This repository contains documentation and code in the format of hands-on labs to help you learn, measure, and build using architectural best practices. The labs are categorized into levels, where 100 is introductory, 200/300 is intermediate and 400 is advanced.
		* [CloudGoat](https://github.com/RhinoSecurityLabs/cloudgoat)
			* CloudGoat is Rhino Security Labs' "Vulnerable by Design" AWS deployment tool. It allows you to hone your cloud cybersecurity skills by creating and completing several "capture-the-flag" style scenarios. Each scenario is composed of AWS resources arranged together to create a structured learning experience. Some scenarios are easy, some are hard, and many offer multiple paths to victory. As the attacker, it is your mission to explore the environment, identify vulnerabilities, and exploit your way to the scenario's goal(s).
		* [CloudGoat 2: The New & Improved “Vulnerable by Design” AWS Deployment Tool - Jeffrey Anderson](https://rhinosecuritylabs.com/aws/introducing-cloudgoat-2/)
		* [CloudGoat 2 Walkthrough - Part One - thetestlabs.io](https://thetestlabs.io/post/cloudgoat-2-walkthrough-part-one/)
		* [Damn Vulnerable Cloud Application](https://github.com/m6a-UdS/dvca)
			* This is a demonstration project to show how to do privilege escalation on AWS. DO NOT deploy this on an AWS account unless you know very well what you are doing!
		* **Lambda**
			* [lambhack](https://github.com/wickett/lambhack)
				* A vulnerable serverless lambda application. This is certainly a bad idea to base any coding patterns of what you see here. lambhack allows you to take advantage of our tried and true application security problems, namely arbitrary code execution, XSS, injection attacks aand more. This first release only contains arbitrary code execution through the query string. Please feel free to contribute new vulnerabilities.
	* **Docker**
		* [Down by the Docker](https://www.notsosecure.com/vulnerable-docker-vm/)
			* Ever fantasized about playing with docker misconfigurations, privilege escalation, etc. within a container? Download this VM, pull out your pentest hats and get started 
		* [Vulhub - Some Docker-Compose files for vulnerabilities environment](https://github.com/vulhub/vulhub)
		* [Vulnerable Docker VM - notsosecure](https://www.notsosecure.com/vulnerable-docker-vm/)
	* **Exploit Development**
		* [exploit_me](https://github.com/bkerler/exploit_me)
			* Very vulnerable ARM application (CTF style exploitation tutorial for ARM, but portable to other platforms)
	* **Git Repo**
		* [Leaky Repo](https://github.com/digininja/leakyrepo)
	* **Router**
		* [iv-wrt](https://github.com/iv-wrt/iv-wrt)
			* An Intentionally Vulnerable Router Firmware Distribution
	* **'Serverless'**
		* [ServerlessGoat](https://github.com/OWASP/Serverless-Goat)
			* This serverless application demonstrates common serverless security flaws as described in the Serverless Security Top 10 Weaknesses guide https://github.com/puresec/sas-top-10. 
	* **Terraform**
		* [TerraGoat](https://github.com/bridgecrewio/terragoat)
			* TerraGoat is Bridgecrew's "Vulnerable by Design" Terraform repository. TerraGoat is a learning and training project that demonstrates how common configuration errors can find their way into production cloud environments.
	* **Thick Client**
		* [Damn Vulnerable Thick Client Application - Part 1 - Setup - Parsia's Den](https://parsiya.net/blog/2018-07-15-damn-vulnerable-thick-client-application---part-1---setup/)



























-----
### Web Applications <a name="webapp"></a>
* **OWASP**<a name="owasp"></a>
	* [OWASP Vulnerable Web Applications Directory Project/Pages/Offline](https://www.owasp.org/index.php/OWASP_Vulnerable_Web_Applications_Directory_Project/Pages/Offline)
	* [OWASP Broken Web Applications Project](https://www.owasp.org/index.php/OWASP_Broken_Web_Applications_Project)
		* OWASP Broken Web Applications Project is a collection of vulnerable web applications that is distributed on a Virtual Machine.
	* [OWASP Juiceshop](https://www.owasp.org/index.php/OWASP_Juice_Shop_Project)
		* [OWASP Juice Shop(Github)](https://github.com/bkimminich/juice-shop)
		* OWASP Juice Shop is an intentionally insecure web application written entirely in Javascript which encompasses the entire range of OWASP Top Ten and other severe security flaws.
		* [OWASP JuiceShop Gitbook walkthrough](https://www.gitbook.com/book/bkimminich/pwning-owasp-juice-shop/details)
		* [Video Walk through by Sunny Wear](https://www.youtube.com/watch?v=zi3yDovd0RY&list=PL-giMT7sGCVI9T4rKhuiTG4EDmUz-arBo)
		* [Pwning OWASP Juice Shop](https://leanpub.com/juice-shop)
	* [OWASP Damn Vulnerable Web Sockets](https://github.com/interference-security/DVWS)
		* OWASP Damn Vulnerable Web Sockets (DVWS) is a vulnerable web application which works on web sockets for client-server communication. The flow of the application is similar to DVWA. You will find more vulnerabilities than the ones listed in the application.
	* [NodeGoat](https://github.com/OWASP/NodeGoat)
		* Being lightweight, fast, and scalable, Node.js is becoming a widely adopted platform for developing web applications. This project provides an environment to learn how OWASP Top 10 security risks apply to web applications developed using Node.js and how to effectively address them.
	* [OWASP DevSlop Project](https://www.owasp.org/index.php/OWASP_DevSlop_Project)
		* collection of DevOps-driven applications, specifically designed to showcase security catastrophes and vulnerabilities for use in security testing, software testing, learning and teaching for both developers and security professionals.
	* [OWASP Mutillidae II](https://sourceforge.net/projects/mutillidae/)
		* OWASP Mutillidae II is a free, open source, deliberately vulnerable web-application providing a target for web-security enthusiast. Mutillidae can be installed on Linux and Windows using LAMP, WAMP, and XAMMP. It is pre-installed on SamuraiWTF and OWASP BWA. The existing version can be updated on these platforms. With dozens of vulnerabilities and hints to help the user; this is an easy-to-use web hacking environment designed for labs, security enthusiast, classrooms, CTF, and vulnerability assessment tool targets. Mutillidae has been used in graduate security courses, corporate web sec training courses, and as an "assess the assessor" target for vulnerability assessment software.
* **General**<a name="wgen"></a>
	* [Damn Vulnerable Web App](https://github.com/ethicalhack3r/DVWA)
		* Damn Vulnerable Web Application (DVWA) is a PHP/MySQL web application that is damn vulnerable. Its main goal is to be an aid for security professionals to test their skills and tools in a legal environment, help web developers better understand the processes of securing web applications and to aid both students & teachers to learn about web application security in a controlled class room environment.
	* [Damn Small Vulnerable Web](https://github.com/stamparm/DSVW)
		* Damn Small Vulnerable Web (DSVW) is a deliberately vulnerable web application written in under 100 lines of code, created for educational purposes. It supports majority of (most popular) web application vulnerabilities together with appropriate attacks.
	* [File scanner web app (Part 1 of 5): Stand-up and webserver](http://0xdabbad00.com/2013/09/02/file-scanner-web-app-part-1-of-5-stand-up-and-webserver/)
	* [Xtreme Vulnerable Web Application (XVWA)](https://github.com/s4n7h0/xvwa)
		* XVWA is a badly coded web application written in PHP/MySQL that helps security enthusiasts to learn application security. It’s not advisable to host this application online as it is designed to be “Xtremely Vulnerable”. We recommend hosting this application in local/controlled environment and sharpening your application security ninja skills with any tools of your own choice.
	* [Hackazon](https://github.com/rapid7/hackazon)
		* Hackazon is a free, vulnerable test site that is an online storefront built with the same technologies used in today’s rich client and mobile applications. Hackazon has an AJAX interface, strict workflows and RESTful API’s used by a companion mobile app providing uniquely-effective training and testing ground for IT security professionals. And, it’s full of your favorite vulnerabilities like SQL Injection, cross-site scripting and so on.
	* [Vulnerable Web applications Generator](https://github.com/qazbnm456/VWGen)
		* This is the Git repo of the VWGen, which stands for Vulnerable Web applications Generator.
	* [secDevLabs](https://github.com/globocom/secDevLabs)
		* By provisioning local environments via docker-compose, you will learn how the most critical web application security risks are exploited and how these vulnerable codes can be fixed to mitigate them. woman_technologist
	* [LKWA](https://github.com/weev3/LKWA)
		* Lesser Known Web Attack Lab is for intermediate pentester that can test and practice lesser known web attacks such as Object Injection, XSSI, PHAR Deserialization, variables variable ..etc.
	* [One Random Insecure Wep Application Please (ORIWAP) - Nancy Snoke(NolaCon2019)](https://www.irongeek.com/i.php?page=videos/nolacon2019/nolacon-2019-c-00-one-random-insecure-wep-application-please-oriwap-nancy-snoke)
		* You may need an insecure web application as part of yearly developer compliance training. You may need an insecure web application for a companywide contest for cyber security awareness month. Perhaps you just like playing with insecure web applications on the weekend. There are a variety of insecure web applications out there. If you have specific needs -- maybe XSS in VBScript as opposed to JavaScript --, or regular use-case where you want something similar to showcase the OWASP top 10 yet different topics and look every time. Then what is out there may not work for you. This talk introduces a new tool -- ORIWAP (One Random Insecure Web Application Please), which can randomly generate an insecure web application (the security features, visual style, and data -- users, passwords, forum postings, about page). If you don't like randomness you can specify some or all of the settings and an application will be generated. The talk will demo creating several new applications, and show the variety of options for creating the perfect insecure web application for you. This talk will also discuss how the code works for each area: security features, visual style, and data.
	* [Damn Small Vulnerable Web in Docker](https://blog.appsecco.com/damn-small-vulnerable-web-in-docker-fd850ee129d5)
* **Specific**<a name="specific"></a>
	* **API**<a name="sapi"></a>
		* [vulnerable-api](https://github.com/mattvaldes/vulnerable-api)
		* [How to configure Json.NET to create a vulnerable web API](https://www.alphabot.com/security/blog/2017/net/How-to-configure-Json.NET-to-create-a-vulnerable-web-API.html)
	* **Django**<a name="sdj"></a>
		* [django.nV](https://github.com/nVisium/django.nV)
			* django.nV is a purposefully vulnerable Django application provided by nVisium.
	* **HTTP Smuggling**<a name="shtt"></a>
		* [HTTP-Smuggling-Lab](https://github.com/ZeddYu/HTTP-Smuggling-Lab)
			* Use HTTP Smuggling Lab to learn HTTP Smuggling.
	* **JSP**<a name="sjsp"></a>
		* [MoneyX](https://github.com/nVisium/MoneyX)
			* MoneyX is an intentionally vulnerable JSP application used for training developers in application security concepts.
	* **Node.js**<a name="sno"></a>
		* [node.nV](https://github.com/nVisium/node.nV)
			* Intentionally Vulnerable node.js application
		* [goat.js](https://github.com/nVisium/goat.js)
			* Tutorial for Node.js security
		* [Damn Vulnerable NodeJS Application(DVNA)](https://github.com/appsecco/dvna)
			* Damn Vulnerable NodeJS Application (DVNA) is a simple NodeJS application to demonstrate OWASP Top 10 Vulnerabilities and guide on fixing and avoiding these vulnerabilities. The fixes branch will contain fixes for the vulnerabilities. Fixes for vunerabilities OWASP Top 10 2017 vulnerabilities at fixes-2017 branch.
	* **Ruby**<a name="sruby"></a>
		* [grails_nV](https://github.com/nVisium/grails-nV)
			* grails_nV is a vulnerable jobs listing website.
		* [RailsGoat](https://github.com/OWASP/railsgoat)
			* RailsGoat is a vulnerable version of the Ruby on Rails Framework from versions 3 to 5. It includes vulnerabilities from the OWASP Top 10, as well as some "extras" that the initial project contributors felt worthwhile to share. This project is designed to educate both developers, as well as security professionals.
	* **SSRF**<a name="ssrf"></a>
		* [SSRF Vulnerable Lab](https://github.com/incredibleindishell/SSRF_Vulnerable_Lab)
			* This repository contain PHP codes which are vulnerable to Server-Side Request Forgery (SSRF) attack.
	* **SSO**<a name="ssso"></a>
		* [Vulnerable SSO](https://github.com/dogangcr/vulnerable-sso)
			* Vulnerable SSo is focused on single sign on related vulnerabilities. If you want to learn, you should check this and contribute this project. VulnSSO tool is focused on sso attacks. Nowadays most of the company uses their own implementation for sso solutions. Some of the bug hunters found really good vulnerability on the big company. There are some tools(dvwa and others .. ) that contains vulnerability. They don't have any support for sso vulnerability. Our focus is only sso related bugs. VulnSSO is training tool.It will contain redirect uri vulnerability , XXE on saml request and many others.
	* **Web Cache Poisoning**<a name="swcp"></a>
		* [Web Cache Poisoning Lab](https://poison.digi.ninja)
			* Welcome to the Cache Poisoning Lab. In this lab you will have the opportunity to experiment with some of the vulnerabilities presented in the brilliant paper Practical Web Cache Poisoning by James Kettle.
* **Making One**
	* [clicker-service](https://gitlab.com/r00k/clicker-service)
		* Docker container that intakes post with the following form data and then "clicks" the link. Intentionally vulnerable. To be used with vulnerable by design web apps to realistically simulate XSS and XSRF (CSRF). Service runs flask to receive the post requests, and runs on the default port of 5000.


























-------------------------
### <a name="AD"></a> Setting up ActiveDirectory Focused Labs
* **Official Documentation**<a name="adoc"></a>
	* [Install AD DS using Powerhsell](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/deploy/install-active-directory-domain-services--level-100-#BKMK_PS)
	* [Active Directory Domain Services Overview](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)
	* [Understanding Active Directory - docs.ms](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2003/cc781408(v=ws.10))
	* [Windows Server 2016: Build a Windows Domain Lab at Home for Free - social.technet](https://social.technet.microsoft.com/wiki/contents/articles/36438.windows-server-2016-build-a-windows-domain-lab-at-home-for-free.aspx#Download)
	* [Integrate macOS with Microsoft Active Directory - support.apple](https://support.apple.com/guide/deployment-reference-macos/integrate-macos-with-active-directory-iorbeda89d1d/1/web/1)
* **Guides**<a name="aguides"></a>
	* **Active Directory Locally**
		* [Building an Effective Active Directory Lab Environment for Testing - adsecurity.org](https://adsecurity.org/?p=2653)
		* [Step-By-Step: Setting up Active Directory in Windows Server 2016 - blogs.technet](https://blogs.technet.microsoft.com/canitpro/2017/02/22/step-by-step-setting-up-active-directory-in-windows-server-2016/)
		* [Pentest Home Lab - 0x2 - Building Your AD Lab on Premises-SethSec](https://sethsec.blogspot.com/2017/06/pentest-home-lab-0x2-building-your-ad.html)
		* [Building and Attacking an Active Directory lab with PowerShell - 1337red](https://1337red.wordpress.com/building-and-attacking-an-active-directory-lab-with-powershell/)
		* [DarthSidious](https://github.com/chryzsh/DarthSidious)
			* Building an Active Directory domain and hacking it
		* [Creating a SCCM Lab: Part 1 - Setting up AD](https://www.youtube.com/watch?v=4zwQsQEtrwY&feature=share)
		* [Build a new Windows Domain with a (semi) easy button - Craig Bowser](http://shadowtrackers.net/blog/build-a-new-windows-domain-with-a-semi-easy-button)
		* [Introducing the Active Directory Learning Lab - @jckhmr_t](https://github.com/jckhmr/adlab)
			* I'm a big fan of automation with tools such as Ansible, Vagrant and Terrorm now being put to regular use by me. Also, as a Red Team Operator I spend a lot of time modelling attacks up, trying new ideas out and generally keeping myself 'sharp'. I wanted to create something that help me to scratch all of these itches. The research and development culminated in my [BSides Belfast 2019 presentation: Offensive Ansible for Red Teams (Attack, Build, Learn)](https://github.com/jckhmr/presentations/blob/master/BSidesBelfast2019_Final_Optimized.pptx?raw=true).
		* [How to Build an Active Directory Hacking Lab - TheCyberMentor](https://www.youtube.com/watch?v=xftEuVQ7kY0)
		* [PAW deployment guide - Jian Yan(2018)](https://blogs.technet.microsoft.com/datacentersecurity/2018/04/30/paw-deployment-guide/)
		* This blogpost only focusses on one aspect, which is the PAW deployment, including the backend servers. 
		* [Step-by-Step Guide to install Active Directory in Windows Server 2019 (PowerShell Guide) - Disham M. Francis(2018)](http://www.rebeladmin.com/2018/10/step-step-guide-install-active-directory-windows-server-2019-powershell-guide/)
	* **AWS**
		* [Active Directory Domain Services on the AWS Cloud: Quick Start Reference Deployment - docs.aws](https://docs.aws.amazon.com/quickstart/latest/active-directory-ds/welcome.html)
		* [Active Directory Domain Services on AWS](https://aws.amazon.com/quickstart/architecture/active-directory-ds/)
			* This Quick Start deploys Microsoft Active Directory Domain Services (AD DS) on the AWS Cloud. AD DS and Domain Name Server (DNS) are core Windows services that provide the foundation for many Microsoft-based solutions for the enterprise, including Microsoft SharePoint, Microsoft Exchange, and .NET Framework applications.
	* **Azure**
		* **Articles/Blogposts/Writeups**
			* [Automating the provisioning of Active Directory labs in Azure - Christophe Tafani-Dereeper](https://blog.christophetd.fr/automating-the-provisioning-of-active-directory-labs-in-azure/)
		* **Tools**
			* [Disruption](https://github.com/xFreed0m/Disruption/)
				* Disruption is a code for Terraform to deploy a small AD domain-based environment in Azure. The environment contains two domain controllers (Windows Server 2012), Fileserver + Web server (Windows Server 2019), Windows 7 client, Windows 10 client, and kali Linux machine. They are connected to the same subnet. Each windows machine has some packages being installing during deployment (the list can be viewed and modified here: chocolist). All the needed configurations (Domain creation, DC promotion, joining the machines to the domain and more are automated and part of the deployment. However, there are more improvments to be added (creating OUs, Users, and stuff like that. I'll might get to it in the future, or, you will submit a pull request :))
* **Lab Generation**<a name="alabgen">
	* **Tools**
		* [WSLab - Official Microsoft Stuff](https://github.com/microsoft/WSLab)
			* Windows Server rapid lab deployment scripts
		* [AutomatedLab](https://github.com/AutomatedLab/AutomatedLab)
			* AutomatedLab is a provisioning solution and framework that lets you deploy complex labs on HyperV and Azure with simple PowerShell scripts. It supports all Windows operating systems from 2008 R2 to 2016 including Nano Server and various products like AD, Exchange, PKI, IIS, etc.	
		* [Automated-AD-Setup](https://github.com/OneLogicalMyth/Automated-AD-Setup)
			* A PowerShell script that aims to have a fully configured domain built in under 10 minutes, but also apply security configuration and hardening.
		* [Invoke-ADLabDeployer](https://github.com/outflanknl/Invoke-ADLabDeployer)
			* Automated deployment of Windows and Active Directory test lab networks. Useful for red and blue teams.
			* [Blogpost](https://outflank.nl/blog/2018/03/30/automated-ad-and-windows-test-lab-deployments-with-invoke-adlabdeployer/))
* **Domain Generator**<a name="adg"></a>
	* **Tools**
		* [BadBlood](https://github.com/davidprowe/BadBlood)
			* BadBlood by Secframe fills a Microsoft Active Directory Domain with a structure and thousands of objects. The output of the tool is a domain similar to a domain in the real world. After BadBlood is ran on a domain, security analysts and engineers can practice using tools to gain an understanding and prescribe to securing Active Directory. Each time this tool runs, it produces different results. The domain, users, groups, computers and permissions are different. Every. Single. Time.
* **Forest Generation**<a name="afg"></a>
	* **Talks/Presentations/Videos**
		* [How To Create An Active Directory Forest With PowerShell - Adam Bertram(2018)](https://www.youtube.com/watch?v=bWF1-rhPh5E)
			* In this video, Adam will cover how the various parameters that are required to run the Install-ADDSForest command and will go over some gotchas that you should know about when building a new forest. Prerequisites include: (2) Windows Server 2016 VMs on the same network (soon-to-be domain controllers)
	* **Tools**
		* [Use PowerShell to Create a New Active Directory Forest on Windows 2019 Server Core Installation (no-GUI) - Mike F Robbins](https://mikefrobbins.com/2018/11/29/use-powershell-to-create-a-new-active-directory-forest-on-windows-2019-server-core-installation-no-gui/)
* **User Generation**<a name="aug"></a>
	* **Articles/Blogposts/Writeups**
		* [Create Bulk Users in Active Directory (Step-By-Step Guide) - Robert Allen(2018)](https://activedirectorypro.com/create-bulk-users-active-directory/)
		* [New-ADUser: Creating Active Directory Users with PowerShell - Kevin Sapp(2019)](https://adamtheautomator.com/new-aduser/)
	* **Tools**
		* [ADImporter](https://github.com/curi0usJack/ADImporter)
			* When you need to simulate a real Active Directory with thousands of users you quickly find that creating realistic test accounts is not trivial. Sure enough, you can whip up a quick PowerShell one-liner that creates any number of accounts, but what if you need real first and last names? Real (existing) addresses? Postal codes matching phone area codes? I could go on. The point is that you need two things: input files with names, addresses etc. And script logic that creates user accounts from that data. This blog post provides both.
		* [youzer](https://github.com/SpiderLabs/youzer)
			* Fake User Generator for Active Directory Environments
* **User Simulation**<a name="aus"></a>
	* **Tools**
		* [sheepl](https://github.com/SpiderLabs/sheepl)
			* sheepl is a tool that aims to bridge the gap by emulating the behaviour that people normally undertake within a network environment. Using Python3 and AutoIT3 the output can be compiled into a standalone executable without any other dependancies that when executed on an Windows endpoint, executes a set of tasks randomly over a chosen time frame.






























-------------------------
### <a name="pentest"></a> Building a Pentest lab
* **Building a Lab Basics**<a name="blb"></a>
	* **Articles/Blogposts/Writeups**
		* [DarthSidious](https://chryzsh.gitbooks.io/darthsidious/content/)
			* To share my modest knowledge about hacking Windows systems. This is commonly refered to as red team exercises. This book however, is also very concerned with the blue team; the defenders. That is, helping those who are working as defenders, analysts and security experts to build secure Active Directory environments and monitor them for malicious activity.
		* [Home Lab with pfSense & VMware Workstation - sysadmin perspective](http://itpro.outsidesys.com/2015/02/19/home-lab-with-pfsense-workstation/)
			* I wanted to build a virtual lab environment at home that would emulate an office environment.  My requirements were to have separate network segments for Clients & Servers, and two DMZ networks.  I also wanted my home network, which is external to the virtual lab environment, to emulate the Internet, even though it really isn’t. The following is how I created multiple “named” LAN segments within VMware Workstation, and routed between them using a VM running pfSense, which is an open source firewall.
		* [Setting Up a Pentest/Hacking Lab with Hyper-V](http://cyberthreathunt.com/2017/04/01/setting-up-a-pentest-lab-with-hyper-v/)
		* [Setting up a Windows Lab Environment](http://thehackerplaybook.com/Windows_Domain.htm)
		* [Setting Up A Penetration Testing Lab - Rapid7](https://kb.help.rapid7.com/docs/setting-up-a-penetration-testing-lab)
		* [Building a Pentest Lab - stan.gr](http://www.stan.gr/2013/03/building-pentest-lab.html)
		* [Privilege-Escalation](https://github.com/Ignitetechnologies/Privilege-Escalation)
			* Collection of VMs aimed at teaching different privilege escalation techniques with Vulnhub machines used for examples.
		* [Emulating ARM Router Firmware - Azeria](https://azeria-labs.com/emulating-arm-firmware/)

		* [Offensive Development with GitHub Actions - MDSec](https://www.mdsec.co.uk/2020/03/offensive-development-with-github-actions/)
* **Offensive Monitoring**
	* **Articles/Blogposts/Writeups**
		* [Automating a RedELK Deployment Using Ansible - Jason Lang(2020)](https://www.trustedsec.com/blog/automating-a-redelk-deployment-using-ansible/)
* **Talks/Presentations/Videos**<a name="bltalk"></a>
	* [SANS Webcast: Building Your Own Super Duper Home Lab](https://www.youtube.com/watch?v=uzqwoufhwyk&app=desktop)
	* [Hack Yourself: Building a Test Lab - David Boyd](https://www.youtube.com/watch?v=rgdX-hn0xXU)
	* [Hack-Yourself: Building a pentesting lab for fun & profit](https://www.slideshare.net/DavidBoydCISSP/hack-yourself-building-a-pentesting-lab-for-fun-and-profit)
* **Tools**<a name="bltools"></a>
	* [DumpsterFire](https://github.com/TryCatchHCF/DumpsterFire)
		* [Slides](https://github.com/TryCatchHCF/DumpsterFire/raw/master/CactusCon_2017_Presentation/DumpsterFire_CactusCon_2017_Slides.pdf)
		* The DumpsterFire Toolset is a modular, menu-driven, cross-platform tool for building repeatable, time-delayed, distributed security events. Easily create custom event chains for Blue Team drills and sensor / alert mapping. Red Teams can create decoy incidents, distractions, and lures to support and scale their operations. Turn paper tabletop exercises into controlled "live fire" range events. Build event sequences ("narratives") to simulate realistic scenarios and generate corresponding network and filesystem artifacts.
	* [Pentest Environment Deployer](https://github.com/Sliim/pentest-env)
		* This repo provides an easy way to deploy a clean and customized pentesting environment with Kali linux using vagrant and virtualbox.
	* [Capsulecorp Pentest](https://github.com/R3dy/capsulecorp-pentest)
		* "The Capsulecorp Pentest is a small virtual network managed by vagrant and ansible. It contains five virtual machines, including one Linux attacking system running xubuntu and 4 Windows 2019 servers configured with various vulnerable services. This project can be used to learn network penetration testing as a stand-alone environment but is ultimatly designed to compliment my book The Art of Network Penetration Testing"
	* [Sadcloud](https://github.com/nccgroup/sadcloud)
		* sadcloud is a tool for spinning up insecure AWS infrastructure with Terraform. It supports approx. 84 misconfigurations across 22 AWS Services. The inital set of misconfigurations were drawn from ScoutSuite, NCCGroup's Multi-cloud auditing tool. sadcloud was created to easily allow security researchers to misconfigure AWS for training purposes, or to use to asses AWS security tools - including built-ins and third-party.
	* [Offensive ELK: Elasticsearch for Offensive Security](https://github.com/marco-lancini/docker_offensive_elk)
		* Offensive ELK is a custom Elasticsearch setup, aiming to show how traditional “defensive” tools can be effectively used for offensive security data analysis, helping your team collaborate and triage scan results. In particular, Elasticsearch offers the chance to aggregate a multitude of disparate data sources, query them with a unified interface, with the aim of extracting actionable knowledge from a huge amount of unclassified data.
		* [Blogpost](https://www.marcolancini.it/2018/blog-elk-for-nmap/)
	* [RedELK](https://github.com/outflanknl/RedELK)
		* Red Team's SIEM - tool for Red Teams used for tracking and alarming about Blue Team activities as well as better usability for the Red Team in long term operations.
* **In the Clouds**<a name="clouds"></a>
	* **AWS**
		* **Official Documentation**
			* [Getting Started with AWS Managed Microsoft AD - docs.aws](https://docs.aws.amazon.com/directoryservice/latest/admin-guide/ms_ad_getting_started.html)
			* [Active Directory Domain Services on the AWS Cloud: Quick Start Reference Deployment](https://docs.aws.amazon.com/quickstart/latest/active-directory-ds/welcome.html)
		* **Un-Official**
			* [Building A Lab on AWS - 0x1 SethSec](https://sethsec.blogspot.com/2017/05/pentest-home-lab-0x1-building-your-ad.html)
			* [Pentesting In The Cloud - primalsecurity](http://www.primalsecurity.net/pentesting-in-the-cloud/)
			* [Designing The Adversary Simulation Lab - Adam Chester(2020)](https://www.mdsec.co.uk/2020/04/designing-the-adversary-simulation-lab/)
	* **Azure**
		* [Building a security lab in Azure - blogs.technet](https://blogs.technet.microsoft.com/motiba/2018/05/11/building-a-security-lab-in-azure/)
	* **GCP**























-------------------------
### <a name="defense"></a> Building a Defensive Lab
* **Guides**<a name="guides"></a>
	* **Articles/Blogposts/Writeups**
		* [DIY Single Sign-On for SSH - Carl Tashian(2020)](https://smallstep.com/blog/diy-single-sign-on-for-ssh/)
			* TL;DR In this post we're going to set up Google single sign-on for SSH. Behind the scenes, we'll use OpenID Connect (OIDC), short-lived SSH certificates, a couple of clever SSH configuration tweaks, and Smallstep's open-source step-ca and step packages. We will set up an SSH Certificate Authority, and use it to bootstrap a new host and a new user in our system. While this approach requires more up-front work than a typical SSH public/private key setup, it comes with a lot of benefits beyond single sign-on. It eliminates the need for gathering and shipping and managing authorized_keys files.
	* **Talks/Presentations/Videos**
* **Talks/Presentations/Videos**
	* [Webcast: Group Policies That Kill Kill Chains - BHIS(2019)](https://www.blackhillsinfosec.com/webcast-group-policies-that-kill-kill-chains/)
	* [Getting Started With Sysmon - John Strand(2019)](https://www.blackhillsinfosec.com/getting-started-with-sysmon/)
	* [Webcast: Implementing Sysmon and Applocker - BHIS(2019)](https://www.blackhillsinfosec.com/webcast-implementing-sysmon-and-applocker/)
	* [Webcast: Windows logging, Sysmon, and ELK - BHIS(2019)](https://www.blackhillsinfosec.com/webcast-windows-logging-sysmon-and-elk/)
	* [Webcast: Let’s Talk About ELK Baby, Let’s Talk About You and AD - BHIS(2020)](https://www.blackhillsinfosec.com/webcast-lets-talk-about-elk-baby-lets-talk-about-you-and-ad/)
		* This webcast is going to demonstrate an integration between our ongoing Windows baseline best practices configuration and improving your endpoint optics. But first, we’re going to summarize some previous webcasts, their content, and the order in which they should be reviewed to tie all of these things together. Then, with all the baseline content and configuration options summarized, we are going to help you put a bow on all that, just in time for the Holidays. 
* **Application Whitelisting**
* **Elastic Search + Log Forwarder/Parser + Kibana**<a name="elk"></a>
	* **101**
	* **Articles/Blogposts/Writeups**
		* [Installing ELK 7 (Elasticsearch, Logstash and Kibana) – Windows Server 2016 (Part I) - Rob Willis(2019)](http://robwillis.info/2019/05/installing-elk-7-elasticsearch-logstash-and-kibana-windows-server-2016/)
		* [Using the ELK Stack and Python in Penetration Testing Workflow - Adam Vanderbush](https://qbox.io/blog/elk-penetration-testing-workflow-elasticsearch-python?utm_source=qbox.io&utm_medium=article&utm_campaign=elk-penetration-testing-workflow-elasticsearch-python)
		* [The Complete Guide to the ELK Stack - Daniel Berman(2019)](https://logz.io/learn/complete-guide-elk-stack/)
	* **Tools**
		* [Elastic stack (ELK) on Docker](https://github.com/deviantony/docker-elk)
			* Run the latest version of the Elastic stack with Docker and Docker Compose.
* **FW Log Visualization**
	* [pfELK](https://github.com/3ilson/pfelk)
		* pfELK was created in 2016 after spending hours researching firewall visualization. After stumbling across Elasticstack (formerly known as ELK stack) with weeks of troubleshooting and research. The process was refined and shared to aid others in leveraging the awesome power of Elasticsearch through the visualization of firewall events. pfELK is comprised of Java, Elasticstack, and a number of dependencies. Your firewall logs are parsed through various patterns simplifying firewall log analysis. Currently, pfSense and OPNsense are supported with extensive testing.
* **Network Access Controls**
	* [PacketFence](https://packetfence.org/)
	    * PacketFence is a fully supported, trusted, Free and Open Source network access control (NAC) solution. Boasting an impressive feature set including a captive-portal for registration and remediation, centralized wired, wireless and VPN management, industry-leading BYOD capabilities, 802.1X and RBAC support, integrated network anomaly detection with layer-2 isolation of problematic devices; PacketFence can be used to effectively secure small to very large heterogeneous networks.
* **Individual Machines**
	* **Linux**
		* **Articles/Blogposts/Writeups**
		* **Talks/Presentations/Videos**
	* **Windows**
		* **Articles/Blogposts/Writeups**
			* [Windows 10 is ‘mine’…, Part 1 - Hexacorn](http://www.hexacorn.com/blog/2020/05/05/windows-10-is-mine-part-1/)
				* Hexacorn walking through setting up a Win10 VM to his standards.
		* **Talks/Presentations/Videos**
* **Monitoring & Threat Hunting**<a name="monitoring"></a>
	* **Articles/Blogposts/Writeups**
		* [How To Do Endpoint Monitoring on a Shoestring Budget – Webcast Write-Up - Joff Thyer, Derek Banks](https://www.blackhillsinfosec.com/endpoint-monitoring-shoestring-budget-webcast-write/)	
		* [Azure Sentinel To-Go: Sentinel Lab w/ Prerecorded Data 😈 & a Custom Logs Pipe via ARM Templates 🚀 - Cyb3rWard0g](https://techcommunity.microsoft.com/t5/azure-sentinel/azure-sentinel-to-go-sentinel-lab-w-prerecorded-data-amp-a/ba-p/1260191)
	* **Talks/Presentations/Videos**
		* [Build your own threat hunting based on open-source tools - Teymur Kheirkhabarov(PHDays2018)](https://speakerdeck.com/heirhabarov/phdays-2018-threat-hunting-hands-on-lab)
		* [Building a Home Network Configured to Collect Artifacts for Supporting Network Forensic Incident Response](https://www.sans.org/reading-room/whitepapers/forensics/building-home-network-configured-collect-artifacts-supporting-network-forensic-incident-response-37302)
	* **Tools**
		* [DetectionLab](https://github.com/clong/DetectionLab)
			* [...]to allow the user to quickly build a Windows domain that comes pre-loaded with security tooling and some best practices when it comes to system logging configurations. It can easily be modified to fit most needs or expanded to include additional hosts.
		* [ELK Detection Lab](https://github.com/thomaspatzke/elk-detection-lab)
			* An ELK environment loaded with the following datasets: Mordor from Roberto Rodriguez @Cyb3rWard0g and Jose Luis Rodriguez @Cyb3rPandaH; EVTX-ATTACK-SAMPLES from Samir Bousseaden SBousseaden; malware-traffic-analysis.net PCAPs from @malware_traffic processed with Suricata.
		* [SweetSecurity](https://github.com/TravisFSmith/SweetSecurity)
			* Scripts to setup and install Bro IDS, Elastic Search, Logstash, Kibana, and Critical Stack on a Raspberry Pi 3 device
		* [Response Operation Collections Kit Reference Build](https://github.com/rocknsm/rock)	
		* [Mordor](https://github.com/Cyb3rWard0g/mordor)
			* The Mordor project provides pre-recorded security events generated by simulated adversarial techniques in the form of JavaScript Object Notation (JSON) files for easy consumption. The pre-recorded data is categorized by platforms, adversary groups, tactics and techniques defined by the Mitre ATT&CK Framework. The pre-recorded data represents not only specific known malicious events but additional context/events that occur around it. This is done on purpose so that you can test creative correlations across diverse data sources, enhancing your detection strategy and potentially reducing the number of false positives in your own environment.
		* [RedELK](https://github.com/outflanknl/RedELK)
			* Red Team's SIEM - tool for Red Teams used for tracking and alarming about Blue Team activities as well as better usability for the Red Team in long term operations.
		* [Adaz: Active Directory Hunting Lab in Azure](https://github.com/christophetd/Adaz)
			* This project allows you to easily spin up Active Directory labs in Azure with domain-joined workstations, Windows Event Forwarding, Kibana, and Sysmon using Terraform/Ansible.
* **Windows Domain**<a name="bwd"></a>
	* **Articles/Blogposts/Writeups**
		* [Microsoft-Blue-Forest](https://github.com/rootsecdev/Microsoft-Blue-Forest)
			* A Blue Forest is centered around Blue Team operational security in domain networks. This repository serves as a living documentation on securing Windows domain networks running modern Microsoft operating systems.
	* **Talks/Presentations/Videos**
	* **Tools**
		* [Gathering Windows, PowerShell and Sysmon Events with Winlogbeat – ELK 7 – Windows Server 2016 (Part II)](http://robwillis.info/2019/05/gathering-windows-powershell-and-sysmon-events-with-winlogbeat-elk-7-windows-server-2016/)
		* [PowerShell Script To Reset The KrbTgt Account Password/Keys For Both RWDCs And RODCs - Jorge]https://jorgequestforknowledge.wordpress.com/2020/04/06/powershell-script-to-reset-the-krbtgt-account-password-keys-for-both-rwdcs-and-rodcs-update-5/)
* **In the Clouds**
	* [Securing Azure Infrastructure - Hands on Lab Guide - Adam Raffle, Tom Wilde](https://github.com/Araffe/azure-security-lab)
	* [Response Operation Collections Kit Reference Build](https://github.com/rocknsm/rock)

















-------------------------
### Other Labs <a name="other"></a>
* [DanderSpritz Lab](https://github.com/francisck/DanderSpritz_lab)
	* The goal of DanderSpritz lab is to allow researchers and defenders to quickly stand up a fully functional version of DanderSpritz - The Equation Group's Post exploitation tool-set and a Windows Server 2008 Domain and client as targets. The Windows target have some reverse engineering tools that I found useful while investigating DanderSpritz and it's capabilities.
* [deploy-your-own-saas](https://github.com/Atarity/deploy-your-own-saas)
	* 'List of "only yours" cloud services for everyday needs'
* **Access Methods**<a name="oam"></a>
	* **RDP**
		* [xrdp](https://github.com/neutrinolabs/xrdp)
			* xrdp provides a graphical login to remote machines using Microsoft Remote Desktop Protocol (RDP). xrdp accepts connections from a variety of RDP clients: FreeRDP, rdesktop, NeutrinoRDP and Microsoft Remote Desktop Client (for Windows, Mac OS, iOS and Android).
	* **SSH**
		* [ubuntu.autossh](https://github.com/Monadical-SAS/ubuntu.autossh)
			* Autossh reverse tunnel to central server.
	* **VPN**
		* **Wireguard**
			* [Wireguard - Wikipedia](https://en.wikipedia.org/wiki/Wireguard)
				* WireGuard is a free and open-source software application and communication protocol that implements virtual private network (VPN) techniques to create secure point-to-point connections in routed or bridged configurations. It is run as a module inside the Linux kernel, and aims for better performance and more power saving than the IPsec and OpenVPN tunneling protocols. It was written by Jason A. Donenfeld and is published under the GNU General Public License (GPL) version 2.
			* [wg-access-server](https://github.com/place1/wg-access-server/)
				* wg-access-server is a single binary that provides a WireGuard VPN server and device management web ui. We support user authentication, 1 click device registration that works with Mac, Linux, Windows, Ios and Android including QR codes. You can configure different network isolation modes for better control and more. This project aims to deliver a simple VPN solution for developers, homelab enthusiasts and anyone else feeling adventurous.
* **Containers/Related**<a name="ocr"></a>
	* **Docker**
		* **Articles/Blogposts/Writeups**	
			* [Docker Your Command & Control (C2) - obscuritylabs](https://blog.obscuritylabs.com/docker-command-controll-c2/)
			* [Create a Reusable Burner OS with Docker, Part 1: Making an Ubuntu Hacking Container - EvilToddler](https://null-byte.wonderhowto.com/how-to/create-reusable-burner-os-with-docker-part-1-making-ubuntu-hacking-container-0175328/)
				* [Part 2](https://null-byte.wonderhowto.com/how-to/create-reusable-burner-os-with-docker-part-2-customizing-our-hacking-container-0175353/)
		* **Tools**
			* [linuxkit](https://github.com/linuxkit/linuxkit)
				* A toolkit for building secure, portable and lean operating systems for containers
			* [Bad Dockerfile](https://github.com/ianmiell/bad-dockerfile)
				* A Dockerfile that creates an image with known vulnerabilities.
				* [Blogpost](https://www.stindustries.net/docker/bad-dockerfile/)
	* **Kubernetes**
		* **Instances**
			* [Simulator](https://github.com/kubernetes-simulator/simulator)
				* A distributed systems and infrastructure simulator for attacking and debugging Kubernetes: simulator creates a kuberntes cluster for you in your AWS account; runs scenarios which misconfigure it and/or leave it vulnerable to compromise and trains you in mitigating against these vulnerabilities.
			* [k3s](https://github.com/rancher/k3s)
				* Lightweight Kubernetes. Easy to install, half the memory, all in a binary less than 40mb.
			* [k3d](https://github.com/rancher/k3d)
				* Little helper to run Rancher Lab's k3s in Docker
			* [kube_security_lab](https://github.com/raesene/kube_security_lab)
				* The goal of this project is to make use of Docker and specifically kind to create a lab environment for testing Kubernetes exploits and security tools entirely locally on a single machine without any requirement for remote resources or Virtual Machines being spun up.
			* [kind](https://kind.sigs.k8s.io/)
				* kind is a tool for running local Kubernetes clusters using Docker container “nodes”. kind was primarily designed for testing Kubernetes itself, but may be used for local development or CI.
		* **Vulnerable**
			* [Bust-a-Kube](https://www.bustakube.com/download)
			* [Kubernetes Goat](https://github.com/madhuakula/kubernetes-goat)
				* The Kubernetes Goat designed to be intentionally vulnerable cluster environment to learn and practice Kubernetes security.
* **Development**
	* [Callback Catcher](https://bitbucket.org/gavinanders/callback-catcher/src/master/)
		* Callback Catcher is a multi-socket control tool designed to aid in pentest activities. It has a simple web application with an backend API that allows the user control what TCP and UDP sockets should be opened on the server. It records any and all data send to the exposed sockets and logs it to a database which can be easily accessed via it's backend API. Itís kind of intended to be like the love child of Burp Collaborator and Responder. Alternatively think of it like a low/medium interactive honeypot. Its been coded on top of the Django REST framework, which offers a number of benefits , primarily being able to create your own client scripts and tools and quickly searching and filtering of data. Opening of sockets is built on top of Python's ServerSocket library. Upon spinning up a socket a user is given the option to assign a handler to the socket, which is affectively user defined code that overwrites the handler function within the SocketServer.TCPServer and SocketServer.UDPServer classes. This code tells the socket how to handle the incoming data and what to respond with. Each connection to the socket is recorded to a database.
* **Mail Servers**
	* **Hosting**
	* **Local**
		* [Papercut](https://github.com/changemakerstudios/papercut)
			* Simple Desktop SMTP Server
* **Mobile Device Management**
	* **macOS**
		* [MicroMDM](https://micromdm.io/)
			* MicroMDM is a project which provides an open source Mobile Device Management server for Apple devices. Our goal is to create a performant and extensible device management solution for enterprise and education.











-------------------------------------------------------
### Infrastructure Automation <a name="infra"></a>
* **101**<a name="i101"></a>
	* [PhoenixServer - Martin Fowler](https://martinfowler.com/bliki/PhoenixServer.html)
	* [An Introduction to the /opt Directory - Nick Sweeting](https://docs.sweeting.me/s/an-intro-to-the-opt-directory#)
	* [An introduction to immutable infrastructure - Josh Stella(2015)](https://www.oreilly.com/radar/an-introduction-to-immutable-infrastructure/)
		* "Why you should stop managing infrastructure and start really programming it."
* **Articles/Blogposts**
	* [An Introduction to Configuration Management - Erika Heidi(2019)](https://www.digitalocean.com/community/tutorials/an-introduction-to-configuration-management)
	* [Automation Testing With Ansible, Molecule, And Vagrant - Mike Spitzer](https://www.trustedsec.com/blog/automation-testing-with-ansible-molecule-and-vagrant/)
	* [Building a scalable, highly available, and portable web server - Surya Dantuluri](https://blog.suryad.com/sd2/)
	* [Containerised Home Server With Docker Compose and Traefik - Kristian Glass](https://blog.doismellburning.co.uk/containerised-home-server-with-docker-compose-and-traefik/)
	* [Infrastructure as Code, Part One - Emily Woods](https://crate.io/a/infrastructure-as-code-part-one/)
	* [Automating a RedELK Deployment Using Ansible - Jason Lang](https://www.trustedsec.com/blog/automating-a-redelk-deployment-using-ansible/)
	* [Red Teaming Series: Part 1 : Setting the environment, Running the C2 server on Docker and Bypassing latest security controls. - ](https://br0h4ck3rs.blogspot.com/2020/03/red-teaming-series-part-1-setting_20.html)
	* [Designing The Adversary Simulation Lab - Adam Chester](https://www.mdsec.co.uk/2020/04/designing-the-adversary-simulation-lab/)
	* [Building, Modifying, and Packing with Azure DevOps - Adam Chester(2020)](https://blog.xpnsec.com/building-modifying-packing-devops/)
	* [Hitchhikers Guide to the PowerShell Module Pipeline - Michael Willis](https://xainey.github.io/2017/powershell-module-pipeline/)
		* The following article highlights both high and mid level concepts toward creating a simple release pipeline for PowerShell modules. The major focus will cover file structure, test practices, task runners, and portability between CI/CD systems. Additional topics include generated reports, design patterns for code consistency, and a Jenkins CI implementation. The supplementary project: Xainey/PSHitchhiker is available on Github to analyze alongside the project.
* **Infrastructure Automation Tools**<a name="infrauto"></a>
	* **Ansible**
		* **Articles/Blogposts**
			* [AWX](https://github.com/ansible/awx)
				* AWX provides a web-based user interface, REST API, and task engine built on top of Ansible. It is the upstream project for Tower, a commercial derivative of AWX.
	* **Chef**
	* **Salt**
	* **Puppet**
	* **Terraform**
		* [An Intro to Terraform with Azure, PFSense, and Windows 10 - FortyNorth Security](https://www.fortynorthsecurity.com/an-intro-to-terraform-with-azure-pfsense-and-windows-10/)
		* [Modern C2 Infrastructure with Terraform, DigitalOcean, Covenant and Cloudflare - Riccardo](https://riccardoancarani.github.io/2019-09-28-modern-c2-infra/)
		* [Infrastructure as Code: Setting up a web application penetration testing laboratory - avasdream](https://avasdream.engineer/terraform-hacking-lab)
		* [Automating Red Team Infrastructure with Terraform - @spottheplanet](https://ired.team/offensive-security/red-team-infrastructure/automating-red-team-infrastructure-with-terraform)
		* [Infrastructure as Code: Setting up a web application penetration testing laboratory - avasdream(2020)](https://avasdream.engineer/terraform-hacking-lab)
	* **Vagrant & Packer**
		* **101**
			* [Vagrant Documentation - vagrantup.com](https://www.vagrantup.com/docs/)
		* **Articles/Blogposts**
			* [Automating Red Team Homelabs: Part 1 – Kali Automation - Alex Rodriguez](https://blog.secureideas.com/2018/09/automating-red-team-homelabs-part-1-kali-automation.html)
			* [Automating Red Team Homelabs: Part 2 – Build, Pentest, Destroy, and Repeat - Alex Rodriguez](https://blog.secureideas.com/2019/05/automating-red-team-homelabs-part-2-build-pentest-destroy-and-repeat.html)
	* **Windows**
		* [Modern Windows Attacks and Defense Lab](https://github.com/jaredhaight/WindowsAttackAndDefenseLab/)
			* This is the lab configuration for the Modern Windows Attacks and Defense class that Sean Metcalf (@pyrotek3) and I(Jared Haight) teach.
		* [Self-Installing Windows OVA](https://github.com/brimstone/windows-ova)
			* This is an Virtual Machine in OVA format that will install Windows ontop of itself. I wrote this as an alternative to packer. This OVA basically downloads the evaluation version of the Windows version you select to one drive as installation media and then installs onto the primary drive. After this is done, the smaller secondary drive can be discarded to save disk space.
	* **Other Tools**
		* [axiom](https://github.com/pry0cc/axiom)
			* Project Axiom is a set of utilities for managing a small dynamic infrastructure setup for bug bounty and pentesting.
	* **Package Management**
		* [fpm](https://github.com/jordansissel/fpm)
			*  Effing package management! Build packages for multiple platforms (deb, rpm, etc) with great ease and sanity. 
* **Sort**
	* [Imaginary C2](https://github.com/felixweyne/imaginaryC2)
		* A python tool which aims to help in the behavioral (network) analysis of malware. Imaginary C2 hosts a HTTP server which captures HTTP requests towards selectively chosen domains/IPs. Additionally, the tool aims to make it easy to replay captured Command-and-Control responses/served payloads.
	* [EVABS (Extremely Vulnerable Android Labs)](https://github.com/abhi-r3v0/EVABS)
		* An open source Android application that is intentionally vulnerable so as to act as a learning platform for Android application security beginners. The effort is to introduce beginners with very limited or zero knowledge to some of the major and commonly found real-world based Android application vulnerabilities in a story-based, interactive model. EVABS follows a level-wise difficulty approach and in each level, the player learns a new concept. This project is still under progress and aims at incorporating as many levels as possible.

