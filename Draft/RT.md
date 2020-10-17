# Red Teaming/Adversary (Emu/)Simulation/Explicitly Pen testing stuff

---------------------------------------------------------------
## Table of Contents
- [General](#general)
	- [101](#101)
	- [Courses](#gcourses)
	- [General Informative Information](#gii)
	- [Building a Red Team](#bart)
	- [Generally Relevant/Useful Information](#grui)
	- [Facilitating a Red Team Engagement](#farte)
	- [Metrics & models](#gmm)
	- [Red Team Experiencs](#rte)
	- [Papers](#gpapers)
	- [Other](#rother)
- [Talks](#talks)
	- Interesting](#tint)
	- [Breaching the Perimeter](#btp)
	- [Building a Team](#bat)
	- [Educational](#vedu)
	- [Lessons Learned](#vll)
	- [Skills Improvement](#vskill)
- [Cobalt Strike](#cobalt)
	- [101](#cs101)
	- [Agressor Scripts](#csas)
	- [Beacon](#csbeacon)
	- [C2](#csc2)
	- [Documentation](#csdoc)
	- [General](#csg)
	- [Logging](#csl)
	- [Phishing](#csp)
	- [Redirector](#csr)
	- [Tool Extension/Integration](#cstei)
	- [Other](#cso)
- [Command, Control, Communicate (or just CnC, or C3)](#c2s)
	- [General stuff](#c2gs)
	- [C2 Development](#c2d)
	- [Other Frameworks besides Cobalt Strike and Empire](#c2o)
	- [Communication Channel Example PoCs](#c2cc)
	- [Papers](#c2papers)
- [Domains and Domain Related Things](#domains)
	- [General](#dg)
	- [Domain Fronting](#df)
	- [Tools](#dt)
	- [Domain reputation](#dr)
- [Egress & Exfiltration](#egress)
- [Empire](#empire)
	- [Articles](#articles)
	- [Customizing](#ecustom)
	- [Manual](#edoc)
	- [Modules & Additions/Extensions](#emods)
- [HW Related/Physical Devices](#hw)
	- [Access Methods/Tools](#access)
	- [Dropboxes](#dropboxes)
	- [Physical Implants](#implants)
- [Infrastructure](#infra)
	- [101](#i101)
	- [Articles/Blogposts/Writeups](#iarticles)
	- [HW/SW for Remote Testing](#remote-testing)
	- [Logging & Monitoring](#ilm)
	- [Web Server](#iws)
	- [Automation Tooling](#iat)
- [Payloads](#payload)
	- [Creation & Development](#pcd)
	- [Delivery & Staging](#pds)
	- [Examples & Samples](#pes)
- [Simulation Tools](#simtools)
	- [Articles/Blogposts/Writeups](#sta)
	- [Talks/Presentations/Videos](#stpv)
	- [Adversary Simulation Tools](#sast)
- [Pen Testing X](#unusual)
	- [AIX](#aix)
	- [Embedded](#embedded)
	- [Faxes, Printers, Other](#faxesprint)
	- [MainFrames](#main)
	- [SCADA/PLCs](#scada)
	- [Virtual Appliances](#va)
---------------------------------------------------------------


* **To Do**
	* APT Data
	* CSharp stuff


--------------------------------------------------------
### <a name="general"></a>General
* **101**<a name="101"></a>
	* [Red Team - Wikipedia](https://en.m.wikipedia.org/wiki/Red_team)
	* [Common Ground Part 1: Red Team History & Overview](https://www.sixdub.net/?p=705)
	* [Target Analysis - Wikipedia](https://en.wikipedia.org/wiki/Target_analysis)
	* [Center of Gravity Analysis - Dale C. Eikmeier](http://www.au.af.mil/au/awc/awcgate/milreview/eikmeier.pdf)
		* Center of Gravity: A system's source of power to act.
	* [A Tradecraft Primer: Structured Analytic Techniques for Improving Intelligence Analysis - USGov 2009](https://www.cia.gov/library/center-for-the-study-of-intelligence/csi-publications/books-and-monographs/Tradecraft%20Primer-apr09.pdf)
	* [The Black Team](http://www.penzba.co.uk/GreybeardStories/TheBlackTeam.html)
	* [IBM Black Team](http://www.t3.org/tangledwebs/07/tw0706.html)
	* [RedTeaming from Zero to One – Part 1 - Rashid Feroze](https://payatu.com/redteaming-from-zero-to-one-part-1)
		* [Part 2](https://payatu.com/redteaming-zero-one-part-2/)
* **Courses**<a name="gcourses"></a>
	* [Advanced Threat Tactics – Course and Notes - CobaltStrike](https://blog.cobaltstrike.com/2015/09/30/advanced-threat-tactics-course-and-notes/)
	* [Red v Blue Workshop - WOPR Summit - Taylor, Dan, Phil](https://github.com/ahhh/presentations/blob/master/Red%20V%20Blue%20Workshop.pdf)
* **General Informative Information**<a name="gii"></a>
	* **Articles/Blogposts/Writeups**
		* [Offensive Tool Design and the Weaponization Dilemma - Matt Graeber(2015)](http://www.exploit-monday.com/2015/12/offensive-tool-design-and-weaponization.html)
		* [The PowerSploit Manifesto - Matt Graeber(2015)](http://www.exploit-monday.com/2015/12/the-powersploit-manifesto.html)
		* [Fools of Golden Gate](https://blog.silentsignal.eu/2017/05/08/fools-of-golden-gate/)
			* How major vulnerabilities/large amounts of publicly vulnerable systems can exist without public recognition for long periods of time. (i.e. CVEs(10.0) exist, but no mapping in nessus/metasploit/etc)
		* [Red Teaming and the Adversarial Mindset: Have a Plan, Backup Plan and Escape Plan - ITS](https://www.itstactical.com/digicom/security/red-teaming-and-the-adversarial-mindset-have-a-plan-backup-plan-and-escape-plan/)
		* [Raphael’s Magic Quadrant - Mudge](https://blog.cobaltstrike.com/2015/08/03/raphaels-magic-quadrant/)
		* [RAT - Repurposing Adversarial Tradecraft - killswitch_GUI](https://speakerdeck.com/killswitch_gui/rat-repurposing-adversarial-tradecraft)
		* [Penetration Testing considered Harmful Today](http://blog.thinkst.com/p/penetration-testing-considered-harmful.html)
		* [Red Team Gut Check - Tim MalcomVetter](https://medium.com/@malcomvetter/red-team-gut-check-10b5976ffd19)
		* [Internal Red Teams and Insider Knowledge - Tim MalcomVetter](https://medium.com/@malcomvetter/internal-red-teams-and-insider-knowledge-8324555aaf40)
		* [Red Teaming: From the Military to Corporate Information Security Teams - 4n7m4n](https://medium.com/@antman1P_30185/red-teaming-from-the-military-to-corporate-information-security-teams-408c040bd87e)
		* [What I’ve Learned in Over a Decade of “Red Teaming” - Dominic Chell](https://medium.com/@dmchell/what-ive-learned-in-over-a-decade-of-red-teaming-5c0b685c67a2)
		* [The Future of Adversaries is Software Development - Tim Malcomvetter(2019)](https://medium.com/@malcomvetter/the-future-of-adversaries-is-software-development-f599c3da2a9f)		
		* [Low Hanging Fruit Often Abused By Red Teams - Cedric Owens(2018)](https://medium.com/red-teaming-with-a-blue-team-mentaility/low-hanging-fruit-often-abused-by-red-teams-b9a66026d89e)
		* [Google Calendar Event Injection with MailSniper](https://www.blackhillsinfosec.com/google-calendar-event-injection-mailsniper/)	
		* [RedTips](https://github.com/vysecurity/RedTips)
			* Red Team Tips as posted by @vysecurity on Twitter
	* **Talks/Presentations/Videos**
		* [Why I Love Offensive Work, Why I don't Love Offensive Work - Halvar Flake(OffensiveCon20)](https://www.youtube.com/watch?v=8QRnOpjmneo)
		* [Planning Effective Red Team Exercises - Sean T Malone - BSidesSF2016](https://www.youtube.com/watch?v=cD-jKBfSKP4)
			* An effective red team exercise is substantially different from a penetration test, and it should be chartered differently as well. The scenario, objective, scope, and rules of engagement all need to be positioned correctly at the beginning in order to most closely simulate a real adversary and provide maximum value to the client.In this presentation, we'll review best practices in each of these areas, distilled from conducting dozens of successful red team exercises - along with some war stories highlighting why each element matters. Those in offensive security will gain an understanding of how to manage the client's expectations for this process, and how to guide them towards an engagement that provides a realistic measurement of their ability to prevent, detect, and respond to real attacks. Those in enterprise security will gain a deeper understanding of this style of assessment, and how to work with a red team to drive real improvement in their security programs.
		* [Let's Create A Redteam Mission - Alex Kouzmine - BlackAlps 2018](https://www.youtube.com/watch?v=-kK8K-UVhWY)
	* **Resources**
		* [Red Team Infrastructure Wiki](https://github.com/bluscreenofjeff/Red-Team-Infrastructure-Wiki)
			* Wiki to collect Red Team infrastructure hardening resources
			* Accompanying Presentation: [Doomsday Preppers: Fortifying Your Red Team Infrastructure](https://speakerdeck.com/rvrsh3ll/doomsday-preppers-fortifying-your-red-team-infrastructure)
		* [Planning a Red Team exercise](https://github.com/magoo/redteam-plan)
		* [Red Teaming Quick Reference Sheet - Sandia Labs(USGov)](https://idart.sandia.gov/_assets/documents/2017-09-13_RT4PM_QRS-Paper-Size.pdf)
			* This quick reference sheet is a component of Sandia'sRed Teaming for Program Managers class.
		* [IDART Quick Reference Sheet - Sandia Labs(USGov)](https://idart.sandia.gov/_assets/documents/2017-09-13_IDART_QRS-Paper-Size.pdf)
* **Building a Red Team**<a name="bart"></a>
	* [Building A Successful Internal Adversarial Simulation Team - C. Gates & C. Nickerson - BruCON 0x08](https://www.youtube.com/watch?v=Q5Fu6AvXi_A&list=PLtb1FJdVWjUfCe1Vcj67PG5Px8u1VY3YD&index=1)
	* [Zero to Hero – Building a Red Team - Robert Neel & David Thompson](http://penconsultants.com/blog/presentation-zero-to-hero-building-a-red-team/)
	* [Some Lessons Learned from Building Red Agents in the RAND Strategy Assessment System (RSAS) - Paul K Davis(1989)](https://www.rand.org/content/dam/rand/pubs/notes/2007/N3003.pdf)
		* This Note contains the text of an oral presentation delivered to the third "Thinking Red in War Games" workshop held at the National Defense University in June 1988. The work underlying the presentation was accomplished in the RAND Strategy Assesment Center (RSAC), which the author directs.
* **Generally Relevant/Useful Information**<a name="grui"></a>
	* [The ‘Laws’ of Red Teaming - RedTeam Journal](https://redteamjournal.com/red-teaming-laws/)
		* Red teaming is governed by informal and wholly unscientific “laws” based largely on human nature. These laws are driven by paradox and, in many cases, a healthy dose of humor. We state some from a general perspective, some from the perspective of the customer or sponsor, and some from the perspective of the red team. Enjoy. We add to these as the mood strikes. (For an alternative list of rules, try the one at redteams.net.)
	* [Beyond Red Teaming Cards - ](https://www.reciprocalstrategies.com/resources/brt_cards/)
		* The Beyond Red Teaming (BRT) cards extend the Red Team Journal Red Teaming “Laws” and cards. The purpose of the BRT cards is to help security professionals consider and assess their own frames and narratives.
	* [Goodbye OODA Loop](http://armedforcesjournal.com/goodbye-ooda-loop/)
	* [Some Comments and Thoughts on Tradecraft](https://www.darkoperator.com/blog/2017/11/20/some-comments-and-thoughts-on-tradecraft)
	* [Terrorists and Technological Innovation - Daveed Gartenstein-Ross, Colin P. Clarke, Matt Shear](https://www.lawfareblog.com/terrorists-and-technological-innovation)
	* [The Duality of Attackers - Or Why Bad Guys are a Good Thing™ - carnal0wnage(2020)](https://carnal0wnage.attackresearch.com/2020/04/the-duality-of-attackers-or-why-bad.html)
* **Facilitating a Red Team Engagement**<a name="farte"></a>
	* **Defining Rules of Engagement**
		* [Sanremo Handbook on Rules of Engagement - iihl.org](http://iihl.org/sanremo-handbook-rules-engagement/)
			* The Sanremo Handbook on the Rules of Engagement (RoE), published in November 2009, represents the only work of this type which sets out to explain in a practical way the complex procedures and methodology governing the development and implementation of Rules of Engagement. It has been translated into the 6 official languages of the United Nations as well as Bosnian, Hungarian and Thai.
	* **Frameworks**
		* [TIBER-EU Framework - How to implement the European framework for Threat Intelligence-based Ethical Red Teaming](https://www.ecb.europa.eu/pub/pdf/other/ecb.tiber_eu_framework.en.pdf)
		* [TIBER - NL Guide - How to conduct the TIBER-NL test](https://www.dnb.nl/binaries/TIBER-NL%20Guide%20Second%20Test%20Round%20final_tcm46-365448.pdf)
		* [TIBER-EU Framework: Services Procurement Guide(European Central Bank)](https://www.ecb.europa.eu/pub/pdf/other/ecb.1808tiber_eu_framework.en.pdf)
		* [CREST Penetration Testing Procurement Guide v1.0](https://www.crest-approved.org/wp-content/uploads/PenTest-Procurement-Guide.pdf)
		* [CBEST Intelligence-Led Testing: CBEST Implementation Guide v2.0 - Bank of England](https://www.bankofengland.co.uk/-/media/boe/files/financial-stability/financial-sector-continuity/cbest-implementation-guide)
	* **Articles/Blogposts/Writeups**
		* [Cyber Exercise  Playbook - MITRE](https://www.mitre.org/sites/default/files/publications/pr_14-3929-cyber-exercise-playbook.pdf)
		* [Planning a Red Team exercise](https://github.com/magoo/redteam-plan)
		* [So You Want to Run a Red Team Operation](https://medium.com/@prsecurity_/how-to-build-an-internal-red-team-7957ec644695)
		* [Red Team Development and Operations: A Practical Guide](https://redteam.guide)
			* [Supporting Documents](https://redteam.guide/docs/)
		* [Red Team Tradecraft and TTP Guidance - Threatexpress](http://threatexpress.com/redteaming/redteamplanning/tradecraft/)
		* [High Value Adversary Emulations via In Person Purple Team Exercises - Jorge Orchilles(2020)](https://www.youtube.com/watch?v=Ard7c-79X84)
			* [Slides](https://www.slideshare.net/jorgeorchilles/purple-team-work-it-out-organizing-effective-adversary-emulation-exercises)
		* [Purple Team - Work it out: Organizing Effective Adversary Emulation Exercises - Jorge Orchilles(2020)](https://www.slideshare.net/jorgeorchilles/purple-team-work-it-out-organizing-effective-adversary-emulation-exercises)
	* **Assumed Breach**
		* [Assumed Breach:A Better Model for Pen Testing - Mike Saunders(2019)](https://www.redsiege.com/wp-content/uploads/2019/12/AssumedBreach-ABMv1.1-1.pdf)
* **Metrics & Models**<a name="gmm"></a>
	* **Reference**
		* [A Red Team Maturity Model - redteams.fyi](https://redteams.fyi/)
			* A model to reference when gauging Red Team maturity, as well as set goals and provide guidance when building internal Red Teams.
	* **Articles/Blogposts/Writeups**
		* [Measuring a red team or penetration test. - Ryan McGeehan(2018)](https://medium.com/starting-up-security/measuring-a-red-team-or-penetration-test-44ea373e5089)
		* [Helpful Red Team Operation Metrics - Cedric Owens(2020)](https://medium.com/red-teaming-with-a-blue-team-mentaility/helpful-red-team-operation-metrics-fabe5e74c4ac)
* **Red Team Experiences**<a name="rte"></a>
	* **Articles/Blogposts/Writeups**
		* [Red Teaming Tips - Vincent Yiu](https://threatintel.eu/2017/06/03/red-teaming-tips-by-vincent-yiu/)
		* [Red Team Tips as posted by @vysecurity on Twitter](https://github.com/vysec/RedTips)
		* [Red Teams - Facebook Experiences Writeup - Ryan McGeehan](https://medium.com/starting-up-security/red-teams-6faa8d95f602)
		* [Reflections from a Red Team Leader - Susan Craig](http://usacac.army.mil/CAC2/MilitaryReview/Archives/English/MilitaryReview_20070430_art011.pdf)
		* [Red Teaming: Using Cutting-Edge Threat Simulation to Harden the Microsoft Enterprise Cloud](https://azure.microsoft.com/en-us/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/)
		* [10 Red Teaming Lessons Learned over 20 Years](https://redteamjournal.com/2015/10/10-red-teaming-lessons-learned-over-20-years/)
		* [Red team versus blue team: How to run an effective simulation - CSOonline](https://www.csoonline.com/article/2122440/disaster-recovery/emergency-preparedness-red-team-versus-blue-team-how-to-run-an-effective-simulation.html)
		* [Red Teaming for Pacific Rim CCDC 2017](https://bluescreenofjeff.com/2017-05-02-red-teaming-for-pacific-rim-ccdc-2017/)
		* [How I Prepared to Red Team at PRCCDC 2015](https://bluescreenofjeff.com/2015-04-15-how-i-prepared-to-red-team-at-prccdc-2015/)
		* [Red Teaming for Pacific Rim CCDC 2016](https://bluescreenofjeff.com/2016-05-24-pacific-rim-ccdc_2016/)
		* [Defenders, Bring Your 'A' Game](https://winterspite.com/security/defenders-bring-your-a-game/)
		* [Responsible Red Teams - Tim MaclomVetter](https://medium.com/@malcomvetter/responsible-red-teams-1c6209fd43cc)
			* [Response by John Strand](https://medium.com/@john_43488/there-was-a-very-well-thought-out-article-on-responsible-red-teaming-by-tim-malcomvetter-7131faa17047)
		* [RedTeaming from Zero to One – Part 1 - payatu.com](https://payatu.com/redteaming-from-zero-to-one-part-1/)
		* [RedTeaming from Zero to One – Part 2 - payatu.com](https://payatu.com/redteaming-zero-one-part-2/)
		* [Red Team Tales 0x01: From MSSQL to RCE - Pablo Martinez](https://www.tarlogic.com/en/blog/red-team-tales-0x01/)
			* In a Red Team operation, a perimeter asset vulnerable to SQL Injection was identified. Through this vulnerability it was possible to execute commands on the server, requiring an unusual tactic to achieve the exfiltration of the output of the commands. In this article we will explain the approach that was followed to successfully compromise this first perimeter element that was later used to pivot the internal network.
		* [There is a shell in your lunch-box - Rotimi Akinyele](https://hakin9.org/shell-lunch-box-rotimi-akinyele/)
		* [Old Skool Red Team - DiabloHorn](https://diablohorn.com/2019/12/28/old-skool-red-team/)
		* [Black Team War Stories: Which company are you a contractor with? - Mark Frost(2019)](https://www.nccgroup.com/uk/about-us/newsroom-and-events/blogs/2019/july/black-team-war-stories-which-company-are-you-a-contractor-with/)
	* **External to Internal**
		* **Articles/Blogposts/Writeups**
			* [From OSINT to Internal: Gaining Domain Admin from Outside the Perimeter - Esteban Rodriguez](https://www.coalfire.com/The-Coalfire-Blog/Sept-2018/From-OSINT-to-Internal-Gaining-Domain-Admin)
			* [From OSINT to Internal – Gaining Access from outside the perimeter - n00py](https://www.n00py.io/2017/03/from-osint-to-internal-gaining-access-from-the-outside-the-perimeter/)
		* **Tools that I couldn't decide where else to put**
			* [intrigue-core](https://github.com/intrigueio/intrigue-core)
				* Intrigue-core is a framework for external attack surface discovery and automated OSINT.
			* [DeviceDetector.NET](https://github.com/totpero/DeviceDetector.NET)
				* The Universal Device Detection library will parse any User Agent and detect the browser, operating system, device used (desktop, tablet, mobile, tv, cars, console, etc.), brand and model.
* **Papers**<a name="gpapers"></a>
	* [Red teaming - A Short Introduction (1.0) June 2009 - Mark Mateski](https://redteamjournal.com/papers/A%20Short%20Introduction%20to%20Red%20Teaming%20(1dot0).pdf)
	* [Red Teaming Guide - UK Ministry of Defense](https://www.gov.uk/government/uploads/system/uploads/attachment_data/file/142533/20130301_red_teaming_ed2.pdf)
	* [Red Team Handbook(2012) - University of Foreign Military And Cultural studies](http://www.au.af.mil/au/awc/awcgate/army/ufmcs_red_team_handbook_apr2012.pdf)
	* [Red Teaming of Advanced Information Assurance Concepts - Bradley Wood, Ruth Duggan](http://cs.uccs.edu/~gsc/pub/master/sjelinek/doc/research/red.pdf)
	* [A Guide To Red Teaming - NATO](http://www.act.nato.int/images/stories/events/2011/cde/rr_ukdcdc.pdf)
	* [Modeling and Simulation of Red Teaming - Part 1: Why Red Team M&S? - Michael J Skroch](https://redteamjournal.com/wp-content/uploads/2009/12/msrt0.3-2nov2009-sand2009-7215J.pdf)
	* [Moving Forward with Computational Red Teaming - Scott Wheeler - Australian DoD](http://www.dtic.mil/dtic/tr/fulltext/u2/a569437.pdf)
	* [Cyber Red Teaming  Organisational, technical and legal implications in a military context - NATO](https://ccdcoe.org/sites/default/files/multimedia/pdf/Cyber_Red_Team.pdf)
	* [Traditions In Military-Strategic Thought In Germany And The Problem Of Deterrence - 1989 - Detlef Bald](http://www.mgfa.de/html/einsatzunterstuetzung/downloads/ap018englisch.pdf?PHPSESSID=931748af0e86616800373655acaf2902)
	* [Force Protection and Suicide Bombers: The Necessity for Two Types of Canadian Military Red Teams](http://www.journal.forces.gc.ca/vol12/no4/page35-eng.asp)
	* [The Applied Critical Thinking Handbook(2015) - University of Foreign Military And Cultural studies](http://usacac.army.mil/sites/default/files/documents/ufmcs/The_Applied_Critical_Thinking_Handbook_v7.0.pdf)
	* [Preparing for the War of the Future in the Wake of Defeat: The Evolution of German Strategic Thought, 1919 - 1935 - Mark Shannon](https://www.ciaonet.org/attachments/25573/uploads)
	* [Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains](https://www.lockheedmartin.com/content/dam/lockheed/data/corporate/documents/LM-White-Paper-Intel-Driven-Defense.pdf)		
	* [Ananalysis of the Metasploit Framework relative to the Penetration Testing Execution Standard(PTES) guidance(2011) - Brandon Perry](http://www.nothink.org/metasploit/documentation/metasploit_msf_analysis_ptes.pdf)
	* [Microsoft Cloud Red Teaming(2016) - gallery.technet](https://gallery.technet.microsoft.com/Cloud-Red-Teaming-b837392e)
		* This whitepaper discusses Microsoft’s strategy and execution of Red Teaming and live site penetration testing against Microsoft managed cloud infrastructure, services and applications. You will learn how Microsoft simulates real-world breaches, conducts continuous security monitoring and practices security incident response to validate and improve the security of Microsoft Azure and Office 365. In addition, you will gain visibility into procedures that customers should consider when deploying and managing cloud-based assets in a secure manner.
* **Other**<a name="gother"></a>
	* [The Definition of a Green Team: A proposed definition for Green Team, and how it differs from a Red Team - Daniel Messler](https://danielmiessler.com/blog/the-definition-green-team-how-different-red-team/)
* **Misc**
	* [Red_Team](https://github.com/BankSecurity/Red_Team)
		* Some scripts useful for red team activities
	* [Penetration-Testing-Tools - mgeeky](https://github.com/mgeeky/Penetration-Testing-Tools)
		*  A collection of more than a 140+ tools, scripts, cheatsheets and other loots that I have developed over years for Penetration Testing and IT Security audits purposes. Most of them came handy at least once during my real-world engagements. 
	* [PenTesting-Scripts - killswitch-GUI](https://github.com/killswitch-GUI/PenTesting-Scripts)
	* [Red Teaming/Adversary Simulation Toolkit - infosecn1nja](https://github.com/infosecn1nja/Red-Teaming-Toolkit)
	* [Red Team Powershell Scripts - Mr-Un1k0d3r](https://github.com/Mr-Un1k0d3r/RedTeamPowershellScripts)














--------------------------------------------------------
### <a name="aptdata"></a> Advanced Persistent Threat Actors & Data
* **101**
	* [APTnotes](https://github.com/aptnotes/data)
		* APTnotes is a repository of publicly-available papers and blogs (sorted by year) related to malicious campaigns/activity/software that have been associated with vendor-defined APT (Advanced Persistent Threat) groups and/or tool-sets.
* **Articles/Blogposts/Writeups**
* **Talks/Presentations/Videos**
	* [DanderSpritz: How the Equation Group's 2013 tools pwn in 2018 - Francisco Donoso(THOTCON9)](https://speakerdeck.com/francisck/thotcon-9-danderspritz-how-the-equation-groups-2013-tools-pwn-in-2018)
	* [Killsuit the equation group's swiss army knife for persistence - Francisco J Donoso, Randori(BlueHatv18)](https://www.youtube.com/watch?v=R5mgAsd2VBM)
		* [Slides](https://www.slideshare.net/MSbluehat/bluehat-v18-killsuit-the-equation-groups-swiss-army-knife-for-persistence-evasion-and-data-exfil)
* **Specific Groups/Operations**
* **APT Emu/Simu-lation**
	* **Data Sources/Reports**
	* **Examples of**
		* [Unit42 Playbook Viewer](https://pan-unit42.github.io/playbook_viewer/)
		* [Introducing the Adversary Playbook: First up, OilRig - Ryan Olson](https://unit42.paloaltonetworks.com/unit42-introducing-the-adversary-playbook-first-up-oilrig/)


















		* [Stupid RedTeamer Tricks - Laurent Desaulniers](https://www.youtube.com/watch?v=2g_8oHM0nwA&list=PLuUtcRxSUZUpv2An-RNhjuZSJ5fjY7ghe&index=11)
		* [Full Contact Recon int0x80 of Dual Core savant - Derbycon7](https://www.youtube.com/watch?v=XBqmvpzrNfs)
		* [Abusing Webhooks for Command and Control - Dimitry Snezhkov](https://www.youtube.com/watch?v=1d3QCA2cR8o&list=PLuUtcRxSUZUpv2An-RNhjuZSJ5fjY7ghe&index=12)
		* [Looping Surveillance Cameras through Live Editing - Van Albert and Banks - Defcon23](https://www.youtube.com/watch?v=RoOqznZUClI)
			* This project consists of the hardware and software necessary to hijack wired network communications. The hardware allows an attacker to splice into live network cabling without ever breaking the physical connection. This allows the traffic on the line to be passively tapped and examined. Once the attacker has gained enough knowledge about the data being sent, the device switches to an active tap topology, where data in both directions can be modified on the fly. Through our custom implementation of the network stack, we can accurately mimic the two devices across almost all OSI layers. We have developed several applications for this technology. Most notable is the editing of live video streams to produce a “camera loop,” that is, hijacking the feed from an Ethernet surveillance camera so that the same footage repeats over and over again. More advanced video transformations can be applied if necessary. This attack can be executed and activated with practically no interruption in service, and when deactivated, is completely transparent.
		* [Sniffing Sunlight - Erik Kamerling - ANYCON2017](http://www.irongeek.com/i.php?page=videos/anycon2017/102-sniffing-sunlight-erik-kamerling)
			* Laser listening devices (laser microphones) are a well understood technology. They have historically been used in the surreptitious surveillance of protected spaces. Using such a device, an attacker bounces an infrared laser off of a reflective surface, and receives the ricocheted beam with a photoreceptor. If the beam is reflected from a surface that is vibrating due to sound (his a typical background target), that sound is subsequently modulated into the beam and can be demodulated at the receptor. This is a known attack method and will be briefly discussed. However, does this principle also hold for non-amplified or naturally concentrated light sources? Can one retrieve modulated audio from reflected sunlight? The idea of modulating voice with sunlight was pioneered by Alexander Graham Bell in 1880 with an invention called the Photophone. A Photophone uses the audio modulation concept now used in laser microphones, but relied on a concentrated beam of sunlight rather than a laser to communicate at distance. Considering that Bell proved that intentionally concentrated sunlight can be used to modulate voice, we will explore under what natural conditions modulated audio can be found in reflected ambient light. Using off the shelf solar-cells and handmade amplifiers, Erik will demonstrate the use of the receiver side of a historic Photophone to identify instances of modulated audio in reflected light under common conditions.
		* [Red Teaming Back and Forth 5ever - Fuzzynop(DerbyconIV)](https://www.youtube.com/watch?v=FTiBwFJQg64)
			* Whether you are on the red team, the blue team, or aspiring to either, you probably know that when it comes to penetrating a network, the scope of the engagement is non existent. I'm talking no-holds-barred penetration. No rules, no time limits, no prisoners. This talk discusses what happens when blue team meets red team and the tools, techniques, and methodology used when you don't have to play by the rules. Additional topics include 'why is red team?' and 'how many does 5ever take?'
		* [Advanced Red Teaming: All Your Badges Are Belong To Us - DEF CON 22 - Eric Smith and Josh Perrymon](https://www.youtube.com/watch?v=EEGxifOAk48)
		* [Operating in the Shadows Carlos Perez - Derbycon5](https://www.youtube.com/watch?v=NXTr4bomAxk)
		* [88MPH Digital tricks to bypass Physical security - ZaCon4 - Andrew MacPherson](https://vimeo.com/52865794)
		* [Attacking EvilCorp: Anatomy of a Corporate Hack](http://www.irongeek.com/i.php?page=videos/derbycon6/111-attacking-evilcorp-anatomy-of-a-corporate-hack-sean-metcalf-will-schroeder)
		* [Detect Me If You Can Ben Ten - Derbycon7](https://www.youtube.com/watch?v=AF3arWoKfKg&index=23&list=PLNhlcxQZJSm-PKUZTYe1C94ymf0omysM3)
		* [Modern Evasion Techniques Jason Lang - Derbycon7](https://www.irongeek.com/i.php?page=videos/derbycon7/t110-modern-evasion-techniques-jason-lang)
			* As pentesters, we are often in need of working around security controls. In this talk, we will reveal ways that we bypass in-line network defenses, spam filters (in line and cloud based), as well as current endpoint solutions. Some techniques are old, some are new, but all work in helping to get a foothold established. Defenders: might want to come to this one.
		* [Red Team Techniques for Evading, Bypassing, and Disabling MS Advanced Threat Protection and Advanced Threat Analytics - Chris Thompson](https://www.youtube.com/watch?v=2HNuzUuVyv0&app=desktop)
		* [Slides](https://www.blackhat.com/docs/eu-17/materials/eu-17-Thompson-Red-Team-Techniques-For-Evading-Bypassing-And-Disabling-MS-Advanced-Threat-Protection-And-Advanced-Threat-Analytics.pdf)
			* Windows Defender Advanced Threat Protection is now available for all Blue Teams to utilize within Windows 10 Enterprise and Server 2012/16, which includes detection of post breach tools, tactics and techniques commonly used by Red Teams, as well as behavior analytics.

--------------
### <a name="talks"></a> Presentations/Talks/Videos
* **Interesting**<a name="tint"></a>
	* [Victor or Victim Strategies for Avoiding an InfoSec Cold War - Jason Lang, Stuart McIntosh(Derbycon 2018)](https://www.youtube.com/watch?v=9_cZ5xn-huc)
	* [Hacks Lies Nation States - Mario DiNatale](https://www.youtube.com/watch?v=nyh_ORq1Qwk)
	* [You’re Probably Not Red Teaming... And Usually I’m Not, Either [SANS ICS 2018] - Deviant Ollam](https://www.youtube.com/watch?v=mj2iSdBw4-0&feature=youtu.be)
* **Breaching the Perimeter**<a name="btp"></a>
	* [Cracking The Perimeter: How Red Teams Penetrate - Dominic Chell(BSidesMCR 2018)](https://www.youtube.com/watch?v=u-MHX9-O890)
	* [Hacking Corporate Em@il Systems - Nate Power](http://www.irongeek.com/i.php?page=videos/bsidescolumbus2016/offense04-hacking-corporate-emil-systems-nate-power)
		* In this talk we will discuss current email system attack vectors and how these systems can be abused and leveraged to break into corporate networks. A penetration testing methodology will be discussed and technical demonstrations of attacks will be shown. Phases of this methodology include information gathering, network mapping, vulnerability identification, penetration, privilege escalation, and maintaining access. Methods for organizations to better protect systems will also be discussed.
	* [Traversing The Kill-Chain: The New Shiny In 2018 - Vincent Yiu - HITBGSEC 2018](https://www.youtube.com/watch?v=w1fNGOKkeSg&feature=youtu.be)
		* Long gone are the days of easy command shells through PowerShell. Defenders are catching more than ever, forcing red teamers to up their game in new and innovative ways. This presentation will explore several new OSINT sources, techniques, and tools developed to accelerate and assist in target asset discovery and profiling. We will discover how some new advances in EDR has changed the general landscape of more mature organisations, and how red team tactics and procedures have been modified to bypass certain obstacles faced. Relevant techniques will be revised, modified and made great again.
* **Building a Team**<a name="bat"></a>
	* [Building and Leading Corporate Red Teams - Dale Pearson(x33fcon 2018)](https://www.youtube.com/watch?v=2kWMIffjNXI)
		* Red Teaming often means different things to different people, so in this talk Dale shares with you what he believes to be Red Teaming in the Corporate world, what to be the foundational elements of establishing the support and buy in to put together an effective adversarial emulation capability, and how to lead it to success and evolve the capability over time.
* **Educational**<a name="vedu"></a>
	* [Adversary Emulation and Red Team Exercises - Jorge Orchilles(2020)](https://www.youtube.com/watch?v=LOv7D384CiI)
		* [Slides](https://www.slideshare.net/jorgeorchilles/adversary-emulation-and-red-team-exercises-educause/)
	* [The Impact of Dark Knowledge and Secrets on Security and Intelligence Professionals - Richard Thieme](https://www.youtube.com/watch?v=0MzcPBAj88A&list=PLuUtcRxSUZUpv2An-RNhjuZSJ5fjY7ghe)
		* Dismissing or laughing off concerns about what it does to a person to know critical secrets does not lessen the impact on life, work, and relationships of building a different map of reality than “normal people” use. One has to calibrate narratives to what another believes. One has to live defensively, warily. This causes at the least cognitive dissonance which some manage by denial. But refusing to feel the pain does not make it go away. It just intensifies the consequences when they erupt. Philip K. Dick said, reality is that which, when you no longer believe in it, does not go away. When cognitive dissonance evolves into symptoms of traumatic stress, one ignores those symptoms at one’s peril. But the very constraints of one’s work often make it impossible to speak aloud about those symptoms, because that might threaten one’s clearances, work, and career. And whistle blower protection is often non-existent.
	* [Tactical Exploiation - H.D. Moore, Valsmith(Defcon15)](https://www.youtube.com/watch?v=DPwY5FylZfQ)
	* [Red Team Methodology A Naked Look Jason Lang(Derbycon2019)](https://www.youtube.com/watch?v=kf829-tm0VM)
		* [Slides](https://www.slideshare.net/JasonLang1/red-team-methodology-a-naked-look-169879355)
	* [How to Start a Cyber War: Lessons from Brussels - Chris Kubecka(BSides Charm 2019)](http://www.irongeek.com/i.php?page=videos/bsidescharm2019/1-06-how-to-start-a-cyber-war-lessons-from-brussels-chris-kubecka)
		* A sanitized peek behind the diplomatic curtain, revealing challenges, decisions & tools at their disposal. The Vanguard cyber warfare exercises in Brussels involving EU & NATO member states. Nation-states leveraging software, hardware and human vulnerabilities into digital warfare, with devastating consequences. Embassy threats, leaked Intel agency tools, hacking back & mass casualties.
	* [Game On! Using Red Team to Rapidly Evolve Your Defenses - Joff Thyer, Pete Petersen](https://www.irongeek.com/i.php?page=videos/derbycon7/t315-game-on-using-red-team-to-rapidly-evolve-your-defenses-joff-thyer-pete-petersen)
		* This talk will be an enjoyable conversation with good beer, great bourbon, and terrific friends who are reliving the journey of infosec maturity from the perspective of both a penetration testing company and their client over a three year period. Details of various engagements will be discussed along with post-mortem analysis, lessons learned, as well as resulting mitigation tactics and defensive strategies. We will discuss the outcomes at each stage of rendered service and how both client and vendor adjusted their approach to re-engage again and again. The engagement culminates in Red Team exercises that clearly demonstrate the infosec evolution of the client. The talk will leave the defensive audience with a sense of hope, a list of achievable goals, and several tactics. The red team with get a glimpse into the maw of the blue future and the value of their tradecraft. Special brief guest appearances and commentary are expected from others in the community that assisted the client along the way as well.
	* [Using blue team techniques in red team ops - Mark Bergman & Marc Smeets(BruCON 0x0A)](https://www.youtube.com/watch?v=OjtftdPts4g)
		* When performing multi-month, multi-C2teamserver and multi-scenario red team operations, you are working with an infrastructure that becomes very large quickly. This makes it harder to keep track of what is happening on it. Coupled with the ever-increasing maturity of blue teams, this makes it more likely the blue team is somewhere analysing parts of your infra and/or artefacts. In this presentation we’ll show you how you can use that to your advantage. We’ll present different ways to keep track of the blue team’s analyses and detections, and to dynamically adjust your infra to fool the blue team. We will first set the scene by explaining common and lesser known components of red teaming infrastructures, e.g. dynamic redirectors, domain fronting revisited, decoy websites, html-smuggling, etc. Secondly, we’ll show how to centralize all your infrastructure’s and ops’ information to an ELK stack, leaving it open for intelligent querying across the entire infrastructure and operation. This will also help with better feedback to the blue team at the end of the engagement. Lastly, we’ll dive into novel ways of detecting a blue team’s investigation and we’ll give examples on how to react to these actions, for example by creating honeypots for the blue team.
	* [Attack Tactics 5: Zero to Hero Attack - Jordan Drysdale, Kent Ickler, John Strand(BHIS)](https://www.youtube.com/watch?v=kiMD0JFFheI)
		* Ever want to see a full attack from no access on the outside to domain takeover? Ever want to see that in under an hour?; OWA? Password Sprays? Yup!; VPNs? Remote account takeover? Yup!; Fully documented command and tool usage? Yup!; MailSniper? Absolutely!; Nmap? Obviously!; Crackmapexec? Definitely!; Cobalt Strike HTA phishing? This is the one I am most worried about :D - but we'll try anyway. So what? What's different about this webcast? We'll cover the zero (external, no access) to hero (internal, domain admin).
	* [RF for Red Team - David Switzer(BSides Tampa2020)](https://www.irongeek.com/i.php?page=videos/bsidestampa2020/track-b-03-rf-for-red-team-david-switzer)
		* "This would be an overview of RF related detections / monitoring and attacks. This would go over current Wifi attacks (both attacking clients and networks), as well as wireless attacks on mice/keyboards (both the old ""mousejack"" and more modern "Logitacker" style attacks), as well as monitoring other systems for physical attacks, such as IoT/smart devices, alarm systems and power meters. - Wifi - General overview - Network attacks - Client attacks - PMKID cracking - Mousejacking and derivatives - IoT / Smart devices - Popular Comm - Cell - Pagers - Misc - Alarm systems - Power meters" 
	* [Passing the Torch: Old School Red Teaming, New School Tactics?](https://www.slideshare.net/harmj0y/derbycon-passing-the-torch)
	* [Red Teaming Windows: Building a better Windows by hacking it - MS Ignite2017](https://www.youtube.com/watch?v=CClpjtgaJVI)
	* [Breaking Red - Understanding Threats through Red Teaming - SANS Webcast](https://www.youtube.com/watch?v=QPmgV1SRTJY)
	* ['Red Team: How to Succeed By Thinking Like the Enemy' - Council on Foreign Relations - Micah Zenko](https://www.youtube.com/watch?v=BM2wYbu4EFY)
* **Lessons Learned**<a name="vll"></a>
	* [Hillbilly Storytime - Pentest Fails - Adam Compton](https://www.youtube.com/watch?v=GSbKeTPv2TU)
		* Whether or not you are just starting in InfoSec, it is always important to remember that mistakes happen, even to the best and most seasoned of analysts. The key is to learn from your mistakes and keep going. So, if you have a few minutes and want to talk a load off for a bit, come and join in as a hillbilly spins a yarn about a group unfortunate pentesters and their misadventures. All stories and events are true (but the names have been be changed to prevent embarrassment).
	* [The hidden horrors that 3 years of global red-teaming, Jos van der Peet](https://www.youtube.com/watch?v=7z63HrEiQUY&index=10&list=PLwZycuzv10iLBFwRIWNAR-s4iuuUMRuEB)
		* My last 3 years of global reteaming in small and large organisations has shown me that there still are a lot of misconceptions about security. We all know the ‘onion’ model for layered security. While useful for the ‘defence in depth’ principle, this talk will show that in reality, rather than an onion, security is more like a pyramid. The basis is the hardware people work on (laptops etc.) and the top your business applications. In between is everything else. Operating system, network components, proxies, shares, servers and their software stack. Like any hi-rise structure, the top cannot be secure if the base is not secure. Defence in depth matters, but it can be quite trivial for attackers to sidestep certain controls to get to the data they want. Just securing your ‘crown-jewels’ is insufficient. This talk will revolve around how we have defeated security controls on various levels, ranging from the systems your end-users work on, all the way through to 2FA and 4-eye principles on critical business assets. It will talk about common misconceptions which lull companies into a false sense of security, while making life far too easy for attackers. For example the fallacy of focussing security efforts only/mostly on ‘crown jewels’ and how misunderstanding of why certain controls are put in place jeopardize corporate and client data. The talk will be supported by real-life examples
	* [Purple Team FAIL! - Jason Morrow - Derbycon2017](https://www.irongeek.com/i.php?page=videos/derbycon7/s16-purple-team-fail-jason-morrow)
		* What went wrong with the introduction of a red team discipline into fortune 1 and how the teams came together to course correct. The result has been a successful purple team that has driven the security posture forward at the world's leading retailer. This will cover some basic do's and don'ts along with new rules of engagement when integrating blue and red. 
	* [A  Year In The Red by Dominic Chell and Vincent Yiu - BSides Manchester2017](https://www.youtube.com/watch?v=-FQgWGktYtw&list=PLcgqQkap1lNrOBNCXqpPqpPAqckxv0XhP&index=23)
	* [Tips, Tricks, and Cheats Gathered from Red vs. Blue Team-Based Training - Ed Skoudis, Joshua Wright](https://www.sans.org/webcasts/tips-tricks-cheats-gathered-red-vs-blue-team-based-training-111505/success)
	* [Liar, Liar: a first-timer "red-teaming" under unusual restrictions. - Mike Loss(Kawaiicon2019)](https://www.youtube.com/watch?v=ASSjkkr4OCg)
	* [One Hundred Red Team Operations A Year - Ryan O'Horo](https://www.youtube.com/watch?v=44LMdSFmmJw&list=PLEJJRQNh3v_PF6cecq0ES2w25JtoG631g&index=6&t=0s)
	* [Adversarial Emulation - Bryson Bort(WWHF19)](https://www.youtube.com/watch?v=3lQTvQlBddw&list=PLXF21PFPPXTNXEgkUEBbRgvraxWP3c4Hr&index=4)
	* [Common Assessment Mistakes Pen Testers and Clients Should Avoid - Brent White, Tim Roberts](https://www.irongeek.com/i.php?page=videos/derbycon7/t211-common-assessment-mistakes-pen-testers-and-clients-should-avoid-brent-white-tim-roberts)
		* Penetration assessments can be a stressful time for those involved. It’s a moment where the network admins find out if the network they manage, or maybe even helped to build, holds up against simulated attacks. Or, it’s a moment as a pen tester where you can help the client and strengthen their security posture, or screw things up by making a mistake - potentially losing a client and giving your company a black eye. However, this shouldn’t be a stressful time. As a client, it is important to understand why the test is taking place and how this helps. As a pentester it is important that you know what you are doing, need to ask for and aren’t just going in blind or throwing the kitchen sink at the network. This talk is to highlight common issues that we’ve either encountered or have have been vented to about from both the penetration tester’s side of the assessment as well as the client’s side. We’d like to bring these issues to light to hopefully help ensure a more smooth assessment “experience” for all parties involved.
* **Skills Improvement**<a name="vskill"></a>
	* [Baselining Behavior Tradecraft through Simulations - Dave Kennedy(WWHF19)](https://www.youtube.com/watch?v=DgxZ8ssuI_o)
		* With the adoption of endpoint detection and response tools as well as a higher focus on behavior detection within organizations, when simulating an adversary it's important to understand the systems you are targeting. This talk will focus on the next evolution of red teaming and how defeating defenders will take more work and effort. This is a good thing! It's also proof that working together (red and blue) collectively, we can make our security programs more robust in defending against attacks. This talk will dive into actual simulations where defenders have caught us as well as ways that we have circumvented even some of the best detection programs out there today. Let's dive into baselining behavior and refining our tradecraft to evade detection and how we can use that to make blue better.
	* [Finding Diamonds in the Rough- Parsing for Pentesters](https://bluescreenofjeff.com/2016-07-26-finding-diamonds-in-the-rough-parsing-for-pentesters/)
	* [Skills for a Red Teamer - Brent White & Tim Roberts - NolaCon 2018](https://www.youtube.com/watch?reload=9&v=Abr4HgSV9pc)
		* Want to incorporate hybrid security assessments into your testing methodology? What does going above and beyond look like for these types of assessments? How do you provide the best value with the resources and scope provided? What do some of these toolkits encompass? If you’re interested in what skills are needed for a Red-Teamer, or taking your red teaming assessments to the next level, here’s the basic info to get you started. We’ll discuss items of importance, methodology, gear, stories and even some tactics used to help give you an edge.
	* [Rethink, Repurpose, Reuse... Rain Hell - Michael Zupo](https://www.irongeek.com/i.php?page=videos/bsideslasvegas2015/cg10-rethink-repurpose-reuse-rain-hell-michael-zupo)
		* What Hacker doesn’t like james bond type gadgets? Like the all in one, one in all tool that can get you out of (or into) all sorts of jams, and is just plain cool to tinker with. Like Glitch from reboot! Well chances are you have several already at your fingertips, there are countless out there with more powerful ones arriving daily. The pace at which new wireless devices are released is blistering fast, leaving many perfectly good “legacy” devices around for testing. This talk will walk you through and further the discussion of modding these devices with readily available tools to quickly turn them into mobile hack platforms. Think PwnPad but without the $900 price tag. Going into whats worth your time and what's not. The possibilities are there if you so choose! Need all the power of your desktop or maybe just a few specific tools? Whatever your aim, this talk will point it further in the right direction
	* [Cons and Conjurers Lessons for Infiltration - Paul Blonsky(BSides Cleveland2016)](https://www.youtube.com/watch?v=jRgOVCBg_Q4)
		*  I will examine how the techniques of con artists and magicians are relevant to physical penetration testing, social engineering and infiltration. Focus is on some classic cons and basics of stage magic deception. 
	* [Red vs Blue: The Untold Chapter - Aaron Herndon, Thomas Somerville(GRRCon2018)](http://www.irongeek.com/i.php?page=videos/grrcon2018/grrcon-2018-lovelace10-red-vs-blue-the-untold-chapter-aaron-herndon-thomas-somerville)
		* This talk focuses on a single attack chain within a simulated network, jumping back and forth between teh thought process ofa  Red Teamer (Aaron) and the Blue Teamer (Tom).
	* [Red Teaming in the EDR age - Will Burgess - WWF HackFest 2018](https://www.youtube.com/watch?v=l8nkXCOYQC4)
	* [Red Team Operating in a Modern Environment: Learning to Live Off the Land - Und3rf10w](https://owasp.org/www-pdf-archive/Red_Team_Operating_in_a_Modern_Environment.pdf)
	* [Red Team Operating in a Modern Environment: Learning to Live Off the Land - und3rf10w](https://owasp.org/www-pdf-archive/Red_Team_Operating_in_a_Modern_Environment.pdf)


















--------------------------------------------------------
### <a name="cobaltstrike"></a>Cobalt Strike
* **101**<a name="cs101"></a>
	* [Cobalt Strike 101 - @spottheplanet](https://ired.team/offensive-security/red-team-infrastructure/cobalt-strike-101-installation-and-interesting-commands)
* **Agressor Scripts**<a name="csas"></a>
	* [Aggressor Script - cs](https://www.cobaltstrike.com/aggressor-script/index.html)
	* [CS Aggressor Scripts - ramen0x3f](https://github.com/ramen0x3f/AggressorScripts#utilscna)
	* [aggressor_scripts_collection - invokethreatguy](https://github.com/invokethreatguy/aggressor_scripts_collection)
		* Collection of various Aggressor Scripts for Cobalt Strike from awesome people. Will be sure to update this repo with credit to each person.
	* [Aggressor Scripts - oldb00t](https://github.com/oldb00t/AggressorScripts)
	* [aggressor_scripts_collection - invokethreatguy](https://github.com/invokethreatguy/aggressor_scripts_collection)
		* Collection of various aggressor scripts for Cobalt Strike from awesome people. Will be sure to update this repo with credit to each person.
	* [AggressorScripts - bluescreenofjeff](https://github.com/bluscreenofjeff/AggressorScripts)
		* Aggressor scripts for use with Cobalt Strike 3.0+
	* [Agressor Script - rasta-mouse](https://github.com/rasta-mouse/Aggressor-Script)
		* Collection of Aggressor Scripts for Cobalt Strike
	* [CVE-2018-4878](https://github.com/vysec/CVE-2018-4878)
		* Aggressor Script to launch IE driveby for CVE-2018-4878
	* [Aggressor 101: Unleashing Cobalt Strike for Fun and Profit](https://medium.com/@001SPARTaN/aggressor-101-unleashing-cobalt-strike-for-fun-and-profit-879bf22cea31)
	* [UACBypass Aggressor Script](https://github.com/RhinoSecurityLabs/Aggressor-Scripts/tree/master/UACBypass)
		* This aggressor script adds three UAC bypass techniques to Cobalt Strike's interface + beacon console.
	* [MoveKit](https://github.com/0xthirteen/MoveKit)
		* Movekit is an extension of built in Cobalt Strike lateral movement by leveraging the execute_assembly function with the SharpMove and SharpRDP .NET assemblies. The aggressor script handles payload creation by reading the template files for a specific execution type.
	* [StayKit](https://github.com/0xthirteen/StayKit)
		* StayKit is an extension for Cobalt Strike persistence by leveraging the execute_assembly function with the SharpStay .NET assembly. The aggressor script handles payload creation by reading the template files for a specific execution type.
	* [The Return of Aggressor - RastaMouse](https://rastamouse.me/2019/06/the-return-of-aggressor/)
		* I’ve previously blogged about how to combine MSBuild and TikiSpawn to execute a Cobalt Strike agent, circumventing AppLocker and Defender on Windows 10 1903. Inspired by Forty North’s Aggressor implemention I thought it would be fun to knock something similar up to leverage TikiSpawn for lateral movement via MSBuild and WMI, and this will hopefully mark the beginning of more Aggressor for common/popular TikiTorch use cases.
		* [Code](https://github.com/rasta-mouse/TikiTorch/tree/master/Aggressor)
	* [RemoteProcessInjection](https://github.com/Mr-Un1k0d3r/RemoteProcessInjection)
		* C# remote process injection utility for Cobalt Strike. The idea is to perform process injection without spawning Powershell and also use a custom obfuscated shellcode payload.
	* [SharpCompile](https://github.com/SpiderLabs/SharpCompile)
		* SharpCompile is an aggressor script for Cobalt Strike which allows you to compile and execute C# in realtime. This is a more slick approach than manually compiling an .NET assembly and loading it into Cobalt Strike. The project aims to make it easier to move away from adhoc PowerShell execution instead creating a temporary assembly and executing using beacon's 'execute-assembly' in seconds.
* **Beacon**<a name="csbeacon"></a>
	* **101**
		* [Beacon Object Files - cs.com](https://www.cobaltstrike.com/help-beacon-object-files)
			* A Beacon Object File (BOF) is a compiled C program, written to a convention that allows it to execute within a Beacon process and use internal Beacon APIs. BOFs are a way to rapidly extend the Beacon agent with new post-exploitation features.
		* [Beacon Object Files - Luser Demo](https://www.youtube.com/watch?v=gfYswA_Ronw)
		* [A Developer’s Introduction to Beacon Object Files - Christopher Paschen(2020)](https://www.trustedsec.com/blog/a-developers-introduction-to-beacon-object-files/)
	* **Tools**
		* [beacon-object-file](https://github.com/realoriginal/beacon-object-file)
			* Template Project Conforming to Beacon's Object File Format ( BOF ) Using Makefile, and Mingw-w64 compilers 
		* [bof-NetworkServiceEscalate](https://github.com/realoriginal/bof-NetworkServiceEscalate)
			* A sample "Beacon Object File" (COFF, really) created with the Mingw-W64 compiler (partially cause I mostly work from a Unix based environment) to escalate from NetworkService or lower privilege to SYSTEM by abusing the issue described by the brilliant James Forshaw here.
* **C2**<a name="csc2"></a>
	* [Cobalt Strike External C2 Paper](https://www.cobaltstrike.com/downloads/externalc2spec.pdf)
	* [External C2 - cs](https://github.com/outflanknl/external_c2)
		* POC for Cobalt Strike external C2
	* [Cobalt Strike over external C2 – beacon home in the most obscure ways](https://outflank.nl/blog/2017/09/17/blogpost-cobalt-strike-over-external-c2-beacon-home-in-the-most-obscure-ways/)
	* [OPSEC Considerations for Beacon Commands - CobaltStrike](https://blog.cobaltstrike.com/2017/06/23/opsec-considerations-for-beacon-commands/)
	* [Valid SSL Certificates with SSL Beacon - cs](https://www.cobaltstrike.com/help-malleable-c2#validssl)
	* [Randomized Malleable C2 Profiles Made Easy](https://bluescreenofjeff.com/2017-08-30-randomized-malleable-c2-profiles-made-easy/)
	* [OPSEC Considerations for beacon commands](https://blog.cobaltstrike.com/2017/06/23/opsec-considerations-for-beacon-commands/)
	* [Agentless Post Exploitation](https://blog.cobaltstrike.com/2016/11/03/agentless-post-exploitation/)
	* [Malleable-C2-Profiles](https://github.com/rsmudge/Malleable-C2-Profiles)
		* Malleable C2 is a domain specific language to redefine indicators in Beacon's communication. This repository is a collection of Malleable C2 profiles that you may use. These profiles work with Cobalt Strike 3.x.
	* [“Tasking” Office 365 for Cobalt Strike C2 - William Knowles](https://labs.f-secure.com/archive/tasking-office-365-for-cobalt-strike-c2/)
		* To explore the potential that Cobalt Strike's newly added “External C2” extension offers offensive teams, MWR have developed a customized C2 channel that uses Office 365 as the communications path.  The key objectives of this post are as follows: Demonstration of a Cobalt Strike C2 channel through Office 365 using “tasks” within Outlook.; Insight into some of the challenges of designing a customized Cobalt Strike C2 channel and one way in which they were addressed.
* **Documentation**<a name="csdoc"></a>
	* [Malleable C2 Documenation - cs](https://www.cobaltstrike.com/help-malleable-c2)
	* [stagelessweb.cna](https://gist.github.com/rsmudge/629bd4ddce3bbbca1f8c16378a6a419c#file-stagelessweb-cna-L6)
		* A stageless variant of the PowerShell Web Delivery attack. This script demonstrates the new scripting APIs in Cobalt Strike 3.7 (generate stageless artifacts, host content on Cobalt Strike's web server, build dialogs, etc.)
	* [In-memory Evasion (2018) - Raphael Mudge](https://www.youtube.com/playlist?list=PL9HO6M_MU2nc5Q31qd2CwpZ8J4KFMhgnK)
		* In-memory Evasion is a four-part mini course on the cat and mouse game related to memory detections. This course is for red teams that want to update their tradecraft in this area. It’s also for blue teams that want to understand the red perspective on these techniques. Why do they work in some situations? How is it possible to work around these heuristics in other cases?
	* [Red Team Operations with Cobalt Strike (2019) Playlist - Raphael Mudge](https://www.youtube.com/playlist?list=PL9HO6M_MU2nfQ4kHSCzAQMqxQxH47d1no)
	* [CSFM - Cobal Strike Field Manual](https://github.com/001SPARTaN/csfm)
		* Cobalt Strike Field Manual - A quick reference for Windows commands that can be accessed in a beacon console.
* **General**<a name="csg"></a>
	* [Fighting the Toolset - Mudge](https://www.youtube.com/watch?v=RoqVunX_sqA)
		* This talk explores offense design decisions, default workflows, and how to adapt when your advantages are your weaknesses.
	* [OPSEC Considerations for Beacon Commands](https://blog.cobaltstrike.com/2017/06/23/opsec-considerations-for-beacon-commands/)
	* [Modern Defenses and YOU!](https://blog.cobaltstrike.com/2017/10/25/modern-defenses-and-you/)
* **Logging**<a name="csl"></a>
	* [cslogwatch](https://github.com/attactics/cslogwatch)
		* cslogwatch is python-based application that implements log watching, parsing, and storage functionality. It is capable of state tracking any cobalt strike log directory and monitoring for any file creations, modifications, or deletions. Once cslogwatch identifies a new log file creation or existing file modification, the log files are automatically parsed and the results are stored in an sqlite database.
		* [cslogwatch: Cobalt Strike Log Tracking, Parsing & Storage - attactick.org(2019)](https://attactics.org/2019/07/cslogwatch-cobalt-strike-tracking-parsing-storage/)
* **Phishing**<a name="csp"></a>
	* [Cobalt Strike - Spear Phishing documentation](https://www.cobaltstrike.com/help-spear-phish)
	* [Spear phishing with Cobalt Strike - Raphael Mudge](https://www.youtube.com/watch?v=V7UJjVcq2Ao)
	* [Cobalt Strike Blog - What's the go-to phishing technique or exploit?](https://blog.cobaltstrike.com/2014/12/17/whats-the-go-to-phishing-technique-or-exploit/)
* **Redirectors**<a name="csr"></a>
	* [Convert Cobalt Strike profiles to Apache mod_rewrite .htaccess files to support HTTP C2 Redirection](https://github.com/threatexpress/cs2modrewrite)
		* This is a quick script that converts a Cobalt Strike profile to a functional mod_rewrite .htaccess file to support HTTP proxy redirection from Apache to a CobaltStrike teamserver.
	* [redi](https://github.com/taherio/redi)
		* Automated redirector setup compatible with HTTP RATs (CobaltStrike Beacon, meterpreter, etc), and CobaltStrike DNS Beacon. The script can either set up nginx reverse proxy, or DNS proxy/forwarder using dnsmasq. If HTTPS was selected, it will automatically setup letsencrypt certbot and obtain valid letsencrypt SSL certificates for your redirector domain name, and start nginx using the generated configuration.
* **Tool Extension/Integration**<a name="cstei"></a>
	* [ANGRYPUPPY](https://github.com/vysec/ANGRYPUPPY)
		* Bloodhound Attack Path Execution for Cobalt Strike
	* [HAMMERTHROW: Rotate my domain - Vincent Yiu](https://vincentyiu.com/red-team/domain-fronting/hammerthrow-rotate-my-domain)
		* HAMMERTHROW is an aggressor script for CobaltStrike that rotates your command and control domains automatically.
		* [Code link](https://github.com/vysecurity/Aggressor-VYSEC/blob/master/HAMMERTHROW.cna)
	* [DDEAutoCS](https://github.com/p292/DDEAutoCS)
		* A cobaltstrike script that integrates DDEAuto Attacks (launches a staged powershell CS beacon). This is not massively stealthy as far as CS scripts go anything like that at the moment, more of a proof of concept, and for having a play. Customise as you see fit to your needs.
	* [ADSearch](https://github.com/tomcarver16/ADSearch)
		* A tool written for cobalt-strike's execute-assembly command that allows for more efficent querying of AD.
	* [CrossC2](https://github.com/gloxec/CrossC2)
		* generate CobaltStrike's cross-platform payload 
	* [SharpAllTheThings](https://github.com/N7WEra/SharpAllTheThings)
		* The idea is to collect all the C# projects that are Sharp{Word} that can be used in Cobalt Strike as execute assembly command.
	* [SharpeningCobaltStrike](https://github.com/cube0x0/SharpeningCobaltStrike)
		* In realtime compiling of dotnet v35/v40 exe/dll binaries + obfuscation with ConfuserEx on your linux cobalt strike server.
* **Other**<a name="cso"></a>
	* [Modern Defense and You - CS](https://blog.cobaltstrike.com/2017/10/25/modern-defenses-and-you/)
	* [User Driven Attacks - cs](https://blog.cobaltstrike.com/2014/10/01/user-driven-attacks/)
	* [Cobalt Strike Visualizations - SPARTan](https://medium.com/@001SPARTaN/cobalt-strike-visualizations-e6a6e841e16b)
	* [Move faster, Stay longer - Steven F](https://posts.specterops.io/move-faster-stay-longer-6b4efab9c644)













































--------------
### <a name="c2"></a>Command, Control, Communicate (or just CnC, or C3)
* **General Stuff**<a name="c2gs"></a>
	* **Articles/Blogposts/Writeups**
		* [The C2 Matrix](https://www.thec2matrix.com)
		* [Reviving MuddyC3 Used by MuddyWater (IRAN) APT - Ahmed Khlief(2020)](https://shells.systems/reviving-leaked-muddyc3-used-by-muddywater-apt/)
	* **Talks/Presentations/Videos**
		* [Adversary Emulation and the C2 Matrix - Jorge Orchilles(2020)](https://www.youtube.com/watch?v=PDkn_v7gomU)
		* [Abusing "Accepted Risk" With 3rd Party C2 - HackMiamiCon5](https://www.slideshare.net/sixdub/abusing-accepted-risk-with-3rd-party-c2-hackmiamicon5)
* **C2 Development**<a name="c2d"></a>
	* See [Offensive Development](#offdevelop)
	* **Articles/Blogposts/Writeups**
		* [How to Build a 404 page not found C2](https://www.blackhillsinfosec.com/?p=5134)
		* [My Journey Writing A Post Exploitation Tool for macOS - Cedric Owens(2019)](https://medium.com/red-teaming-with-a-blue-team-mentaility/my-journey-writing-a-post-exploitation-tool-for-macos-d8293d51244f)
		* [Command and Control via TCP Handshake - thesw4rm(2019)](https://thesw4rm.gitlab.io/nfqueue_c2/2019/09/15/Command-and-Control-via-TCP-Handshake/)
		* [Building a Basic C2 - 0xRick](https://0xrick.github.io/misc/c2/)	
			* [Code](https://github.com/0xRick/c2)
	* **Talks/Presentations/Videos**
		* [C3CM: Defeating the Command - Control - and Communications of Digital Assailants](http://www.irongeek.com/i.php?page=videos/derbycon4/t206-c3cm-defeating-the-command-control-and-communications-of-digital-assailants-russ-mcree)
			* C3CM: the acronym for command- control- and communi - cations countermeasures. Ripe for use in the information security realm, C3CM takes us past C2 analysis and to the next level. Initially, C3CM was most often intended to wreck the command and control of enemy air defense networks, a very specific military mission. We-ll apply that mindset in the context of combating bots and other evil. Our version of C3CM therefore is to identify, interrupt, and counter the command, control, and communications capabilities of our digital assailants. The three phases of C3CM will utilize: Nfsight with Nfdump, Nfsen, and fprobe to conduct our identification phase, Bro with Logstash and Kibana for the interruption phase, and ADHD for the counter phase. Converge these on one useful platform and you too might have a chance deter those who would do you harm. We-ll discuss each of these three phases (identify, interrupt, and counter) with tooling and tactics, complete with demonstrations and methodology attendees can put to use in their environments. Based on the three part ISSA Journal Toolsmith series: http://holisticinfosec.blogspot.com/search?q=c3cm&max-results=20&by-date=true
		* [Flying a False Flag: Advanced C2, Trust Conflicts, and Domain Takeover - Nick Landers(BHUSA2019)](https://www.youtube.com/watch?v=2BEwqbCbQuM&feature=youtu.be)
			* This talk will discuss the methodology, selection process, and challenges of modern C2. It will cover the details of recent HTTP/S advancements and tooling for new cloud service primitives such as SQS, AppSpot, S3, and CloudFront. We will demonstrate how trust can be abused for stealthy C2 techniques via internal mail servers, defensive platforms, and trusted domains. We will also cover the various options for domain takeover, and release tooling for exploiting domain takeover scenarios in Amazon Web Services (AWS), Azure, and Google Cloud Platform (GCP).
			* [Code](https://github.com/monoxgas/FlyingAFalseFlag)
	* **Tools**	
		* [Callback Catcher](https://bitbucket.org/gavinanders/callback-catcher/src/master/)
			* Callback Catcher is a multi-socket control tool designed to aid in pentest activities. It has a simple web application with an backend API that allows the user control what TCP and UDP sockets should be opened on the server. It records any and all data send to the exposed sockets and logs it to a database which can be easily accessed via it's backend API. Itís kind of intended to be like the love child of Burp Collaborator and Responder. Alternatively think of it like a low/medium interactive honeypot. Its been coded on top of the Django REST framework, which offers a number of benefits , primarily being able to create your own client scripts and tools and quickly searching and filtering of data. Opening of sockets is built on top of Python's ServerSocket library. Upon spinning up a socket a user is given the option to assign a handler to the socket, which is affectively user defined code that overwrites the handler function within the SocketServer.TCPServer and SocketServer.UDPServer classes. This code tells the socket how to handle the incoming data and what to respond with. Each connection to the socket is recorded to a database.
		* [CheckPlease](https://github.com/Arvanaghi/CheckPlease)
			* Implant-Security modules written in PowerShell, Python, Go, Ruby, C, C#, Perl, and Rust. 
		* [emptynest](https://github.com/empty-nest/emptynest)
			* Emptynest is a plugin based C2 server framework. The goal of this project is not to replace robust tools such as Empire, Metasploit, or Cobalt Strike. Instead, the goal is to create a supporting framework for quickly creating small, purpose built handlers for custom agents. No agent is provided. Users of Emptynest should create their own agents that implement minimal functionality and can be used to evade detection and establish a more robust channel. An example of an agent might support Unhooking, DLL Unloading, and code execution. Due to the simple nature of this project, it is recommended that agents be kept private.
		* [RemoteRecon](https://github.com/xorrior/RemoteRecon)
			* RemoteRecon provides the ability to execute post-exploitation capabilities against a remote host, without having to expose your complete toolkit/agent. Often times as operator's we need to compromise a host, just so we can keylog or screenshot (or some other miniscule task) against a person/host of interest. Why should you have to push over beacon, empire, innuendo, meterpreter, or a custom RAT to the target? This increases the footprint that you have in the target environment, exposes functionality in your agent, and most likely your C2 infrastructure. An alternative would be to deploy a secondary agent to targets of interest and collect intelligence. Then store this data for retrieval at your discretion. If these compromised endpoints are discovered by IR teams, you lose those endpoints and the information you've collected, but nothing more.
		* [Nuages](https://github.com/p3nt4/Nuages)
			* Nuages aims at being a C2 framework in which back end elements are open source, whilst implants and handlers must be developed ad hoc by users. As a result, it does not provide a way to generate implants, but an open source framework to develop and manage compatible implants that can leverage all the back end resources already developed.
			* [Tutorial: Creating a custom full featured implant(Nuages)](https://github.com/p3nt4/Nuages/wiki/Tutorial:-Creating-a-custom-full-featured-implant)
	* **C3**
		* **101**
			* [C3 - Custom Command and Control - FSecure Labs](https://labs.f-secure.com/tools/c3/)
			* [C3](https://github.com/FSecureLABS/C3)
				* C3 (Custom Command and Control) is a tool that allows Red Teams to rapidly develop and utilise esoteric command and control channels (C2). It's a framework that extends other red team tooling, such as the commercial Cobalt Strike (CS) product via ExternalC2, which is supported at release. It allows the Red Team to concern themselves only with the C2 they want to implement; relying on the robustness of C3 and the CS tooling to take care of the rest. This efficiency and reliability enable Red Teams to operate safely in critical client environments (by assuring a professional level of stability and security); whilst allowing for safe experimentation and rapid deployment of customised Tactics, Techniques and Procedures (TTPs). Thus, empowering Red Teams to emulate and simulate an adaptive real-world attacker.
		* **Articles/Blogposts/Writeups**
			* [Making Donuts Explode – Updates to the C3 Framework - Tim Carrington](https://labs.f-secure.com/blog/making-donuts-explode-updates-to-the-c3-framework/)
* **Other Frameworks besides Cobalt Strike and Empire**<a name="c2o"></a>
	* **Appfell**
		* [Appfell](https://github.com/its-a-feature/Apfell)
			* A cross-platform, post-exploit, red teaming framework built with python3, docker, docker-compose, and a web browser UI. It's designed to provide a collaborative and user friendly interface for operators, managers, and reporting throughout mac and linux based red teaming.
		* [Poseidon](https://github.com/xorrior/poseidon)
			* Golang Apfell Agent
	* **Covenant**
		* **101**
			* [Entering a Covenant: .NET Command and Control - Ryan Cobb](https://posts.specterops.io/entering-a-covenant-net-command-and-control-e11038bcf462)
			* [Covenant](https://github.com/cobbr/Covenant)
				* Covenant is a .NET command and control framework that aims to highlight the attack surface of .NET, make the use of offensive .NET tradecraft easier, and serve as a collaborative command and control platform for red teamers. Covenant is an ASP.NET Core, cross-platform application that includes a web-based interface that allows for multi-user collaboration.
		* **Articles/Blogposts/Writeups**
			* [Covenant Tasks 101 - RastaMouse](https://rastamouse.me/2019/12/covenant-tasks-101/)
			* [Covenant, Donut, TikiTorch - RastaMouse](https://web.archive.org/web/20200408131145/https://rastamouse.me/2019/08/covenant-donut-tikitorch/)
			* [Red Teaming with Covenant and Donut - NaijaSecForce](https://blog.naijasecforce.com/red-teaming-with-covenant-and-donut/)
			* [Actually Using Covenant C2 and Not Just Installing It! - Ryan Villarreal(2020)](https://bestestredteam.com/2020/02/19/interacting-with-covenant-c2/)
			* [Covenant Task 101 — PPID Spoof Example - Onwukike Chinedu(2020)](https://medium.com/@chinedu.onwukike/covenant-task-101-ppid-spoof-example-c07ecb21007f)
	* **FudgeC2**
		* [FudgeC2](https://github.com/Ziconius/FudgeC2)
			* FudgeC2 is a Powershell command and control platform designed to facilitate team collaboration and campaign timelining. This aims to help clients better understand red team activities by presenting them with more granular detail of adversarial techniques. Built on Python3 with a web frontend, FudgeC2 aims to provide red teamers a simple interface in which to manage active implants across their campaigns.
	* **Koadic**
		* [Koadic](https://github.com/zerosum0x0/koadic)
			* Koadic, or COM Command & Control, is a Windows post-exploitation rootkit similar to other penetration testing tools such as Meterpreter and Powershell Empire. The major difference is that Koadic does most of its operations using Windows Script Host (a.k.a. JScript/VBScript), with compatibility in the core to support a default installation of Windows 2000 with no service packs (and potentially even versions of NT4) all the way through Windows 10.
		* [Post Exploitation with KOADIC - Ian Kings](https://www.prismacsi.com/en/post-exploitation-with-koadic/)
	* **Mouse**
		* [Mouse](https://github.com/entynetproject/mouse)
			* Mouse Framework is an iOS and macOS post-exploitation framework that gives you a command line session with extra functionality between you and a target machine using only a simple Mouse payload. Mouse gives you the power and convenience of uploading and downloading files, tab completion, taking pictures, location tracking, shell command executio… 
	* **NinjaC2**
		* [Ninja](https://github.com/ahmedkhlief/Ninja)
			* Ninja C2 is an Open source C2 server created by Purple Team to do stealthy computer and Active directoty enumeration without being detected by SIEM and AVs , Ninja still in beta version and when the stable version released it will contains many more stealthy techniques and anti-forensic to create a real challenge for blue team to make sure all the defenses configured correctly and they can detect sophisticated attacks. Ninja use python to server the payload and control the agents . the agents are based on C# and powershell which can bypass leading AVs . Ninja comunicate with the agents in secure channel encrpyted with AES-256 and the key is not hard coded but randomly generated on the campaign start , every agent connect to the C2 get the key and if the C2 restarted a new key will be used by all old agents and the new. Ninja also randomize the callback URLs for every campaign to bypass static detection.
			* [Introducing Ninja C2 : the C2 built for stealth red team Operations - Ahmed Khlief(2020)](https://shells.systems/introducing-ninja-c2-the-c2-built-for-stealth-red-team-operations/)
	* **Octopus**	
		* [Octopus](https://github.com/mhaskar/Octopus)
			* Octopus is an open source, pre-operation C2 server based on python which can control an Octopus powershell agent through HTTP/S.
			* [Unveiling Octopus: The pre-operation C2 for Red Teamers - Askar](https://shells.systems/unveiling-octopus-the-pre-operation-c2-for-red-teamers/)
			* [Automate Octopus C2 RedTeam Infrastructure Deployment - Askar(2020)](https://shells.systems/automate-octopus-c2-redteam-infrastructure-deployment/)
	* **Shadow**
		* [shad0w](https://github.com/bats3c/shad0w)
			* SHAD0W is a modular C2 framework designed to successfully operate on mature enviroments. It will use a range of methods to evade EDR and AV while allowing the operator to continue using tooling an tradecraft they are familiar with. Its powered by Python 3.8 and C, using Donut for payload generation. By using Donut along side the process injection capabilities of SHAD0W it gives the operator the ability to execute .NET assemblies, EXEs, DLLs, VBS, JS or XSLs fully inside memory. Dynamically resolved syscalls are heavily used to avoid userland API hooking, anti DLL injection to make it harder for EDR to load code into the beacons and offical microsoft mitigation methods to protect spawn processes.
			* [Blogpost](https://labs.jumpsec.com/2020/06/03/shad0w/)
	* **SharpC2**
		* [SharpC2](https://github.com/SharpC2/SharpC2)
			* .NET C2 Framework Proof of Concept 
		* [SharpC2 - RastaMouse](https://rastamouse.me/blog/sharpc2/)
	* **Silent Trinity**
		* [SILENTTRINITY](https://github.com/byt3bl33d3r/SILENTTRINITY)
			* SILENTTRINITY is modern, asynchronous, multiplayer & multiserver C2/post-exploitation framework powered by Python 3 and .NETs DLR. It's the culmination of an extensive amount of research into using embedded third-party .NET scripting languages to dynamically call .NET API's, a technique the author coined as BYOI (Bring Your Own Interpreter). The aim of this tool and the BYOI concept is to shift the paradigm back to PowerShell style like attacks (as it offers much more flexibility over traditional C# tradecraft) only without using PowerShell in anyway.
		* [Hunting for SILENTTRINITY - Wee-Jing Chung(2019)](https://blog.f-secure.com/hunting-for-silenttrinity/)
			* SILENTTRINITY (byt3bl33d3r, 2018) is a recently released post-exploitation agent powered by IronPython and C#. This blog post will delve into how it works and techniques for detection.
		* [SILENTTRINITY - DarthSidious](https://hunter2.gitbook.io/darthsidious/command-and-control/silenttrinity)
			* Using Kali as a C2 Server
		* [How to Use Silent Trinity - Bresaola 0.3.0dev - H4cklife!!](https://h4cklife.org/posts/how-to-use-silent-trinity/)
	* **Sliver**
		* [Sliver](https://github.com/BishopFox/sliver)
			* Sliver is a general purpose cross-platform implant framework that supports C2 over Mutual-TLS, HTTP(S), and DNS. Implants are dynamically compiled with unique X.509 certificates signed by a per-instance certificate authority generated when you first run the binary. The server, client, and implant all support MacOS, Windows, and Linux (and possibly every Golang compiler target but we've not tested them all).
* **Communication Channel Example PoCs**
	* **404**
		* [How to Build a 404 page not found C2](https://www.blackhillsinfosec.com/?p=5134)
		* [404 File not found C2 PoC](https://github.com/theG3ist/404)
	* **ActiveDirectory Features**
		* [Command and Control Using Active Directory](http://www.harmj0y.net/blog/powershell/command-and-control-using-active-directory/)
	* **ARP**
		* [Zarp](https://github.com/hatRiot/zarp)
			* Zarp is a network attack tool centered around the exploitation of local networks. This does not include system exploitation, but rather abusing networking protocols and stacks to take over, infiltrate, and knock out. Sessions can be managed to quickly poison and sniff multiple systems at once, dumping sensitive information automatically or to the attacker directly. Various sniffers are included to automatically parse usernames and passwords from various protocols, as well as view HTTP traffic and more. DoS attacks are included to knock out various systems and applications.
	* **BITS**
		* [LOLBITS](https://github.com/Kudaes/LOLBITS)
			* LOLBITS is a C# reverse shell that uses Microsoft's Background Intelligent Transfer Service (BITS) to communicate with the Command and Control backend. The Command and Control backend is hidden behind an apparently harmless flask web application and it's only accesible when the HTTP requests received by the app contain a valid authentication header.
	* **Browser**
		* [Browser-C2](https://github.com/0x09AL/Browser-C2)
			* Post Exploitation agent which uses a browser to do C2 operations.
		* [Using Firefox webextensions as c2 client - Matheus Bernardes](https://mthbernardes.github.io/persistence/2019/03/07/using-firefox-webextensions-as-c2-client.html)
	* **Cobalt Strike**
		* [External C2](https://github.com/ryhanson/ExternalC2)
			* A library for integrating communication channels with the Cobalt Strike External C2 server
	* **DNS-based**
		* [C2 with DNS](https://pentestlab.blog/2017/09/06/command-and-control-dns/)
		* [dnscat2-powershell](https://github.com/lukebaggett/dnscat2-powershell)
			* A Powershell client for dnscat2, an encrypted DNS command and control tool
		* [DNS-Persist](https://github.com/0x09AL/DNS-Persist)
			* DNS-Persist is a post-exploitation agent which uses DNS for command and control. The server-side code is in Python and the agent is coded in C++.
	* **Email**
		* [DicerosBicornis](https://github.com/maldevel/dicerosbicornis)
			* A stealthy Python based Windows backdoor that uses email as a command and control server.
	* **Google Translate**
		* [GTRS - Google Translator Reverse Shell](https://github.com/mthbernardes/GTRS/blob/master/README.md)
			* This tools uses Google Translator as a proxy to send arbitrary commands to an infected machine.
	* **HTTP/S-based**
		* [PoshC2 v3 with SOCKS Proxy (SharpSocks)](https://labs.nettitude.com/blog/poshc2-v3-with-socks-proxy-sharpsocks/)
		* [PoshC2](https://github.com/nettitude/PoshC2)
			* Powershell C2 Server and Implants
		* [Galvatron](https://github.com/khr0x40sh/Galvatron)
			* Powershell fork of Monohard by Carlos Ganoza P. This botnet/backdoor was designed to egress over unecrypted web using very little, but effective obfuscation. Egress over ICMP and DNS are planned as features. Lastly, the server code is designed to setup the C2 on a LAMP-esque server. The default creds are admin/admin.
		* [C2 with https](https://pentestlab.blog/2017/10/04/command-and-control-https/)
		* [C2 over TLS Certs - Casey Smith](https://gist.github.com/caseysmithrc/a4c4748160ff9c782d8a86723dbc7334?t=1&cn=ZmxleGlibGVfcmVjcw%3D%3D&refsrc=email&iid=6e15d70104f847a8ae7723921067fe1d&fl=4&uid=150127534&nid=244+285282312)
		* [ThunderShell](https://github.com/Mr-Un1k0d3r/ThunderShell)
			* ThunderShell is a Powershell based RAT that rely on HTTP request to communicate. All the network traffic is encrypted using a second layer of RC4 to avoid SSL interception and defeat network hooks.
		* [FruityC2](https://github.com/xtr4nge/FruityC2)
			* FruityC2 is a post-exploitation (and open source) framework based on the deployment of agents on compromised machines. Agents are managed from a web interface under the control of an operator.
		* [PlugBot-C2C](https://github.com/redteamsecurity/PlugBot-C2C)
			* This is the Command & Control component of the PlugBot project
		* [EggShell](https://github.com/neoneggplant/EggShell)
			* EggShell is an iOS and macOS post exploitation surveillance pentest tool written in Python. This tool creates 1 line multi stage payloads that give you a command line session with extra functionality. EggShell gives you the power and convenience of uploading/downloading files, taking pictures, location tracking, shell command execution, persistence, escalating privileges, password retrieval, and much more. Server communication features end to end encryption with 128 bit AES and the ability to handle multiple clients. This is a proof of concept pentest tool, intended for use on machines you own.
			* [EggShell Blogpost](http://lucasjackson.me/dWkKX/index.php/eggshell)
		* [A Guide to Configuring Throwback](https://silentbreaksecurity.com/throwback-thursday-a-guide-to-configuring-throwback/)
			* [Throwback - beacon](https://github.com/silentbreaksec/Throwback)
			* [Throwback Listener](https://github.com/silentbreaksec/ThrowbackLP)
	* **HTTP2**
		* [Merlin](https://github.com/Ne0nd0g/merlin)
			* Merlin is a cross-platform post-exploitation HTTP/2 Command & Control server and agent written in golang.
	* **ICMP**
		* [ICMP C2](https://pentestlab.blog/2017/07/28/command-and-control-icmp/)
		* [C2 with ICMP](https://pentestlab.blog/2017/07/28/command-and-control-icmp/)
	* **OCR**
		* [Implementing Proof-of-Concept C2 with Microsoft OCR - Adrian Denkiewicz(CQLabs2020)](https://cqureacademy.com/cqure-labs/implementing-proof-of-concept-c2-with-microsoft-ocr)
	* **Office365**
		* [Callidus](https://github.com/3xpl01tc0d3r/Callidus)
			* Latin word for “sneaky” is called “Callidus”. It is developed for learning and improving my knowledge about developing custom toolset in C# and learning how to leverage cloud services for the benefit of the user. It is developed using .net core framework in C# language. Allows operators to leverage O365 services for establishing command & control communication channel. It usages Microsoft Graph APIs for communicating with O365 services.
		* [Introduction to Callidus - 3xpl01tc0d3r(2020)](https://3xpl01tc0d3r.blogspot.com/2020/03/introduction-to-callidus.html)
	* **PAC**
		* [Pacdoor](https://github.com/SafeBreach-Labs/pacdoor)
			* Pacdoor is a proof-of-concept JavaScript malware implemented as a Proxy Auto-Configuration (PAC) File. Pacdoor includes a 2-way communication channel, ability to exfiltrate HTTPS URLs, disable access to cherry-picked URLs etc.
	* **SSH** 
		* [Spidernet](https://github.com/wandering-nomad/Spidernet)
			* Proof of Concept of SSH Botnet C&C Using Python 
	* **Social Media-based**
		* [JSBN](https://github.com/Plazmaz/JSBN)
			* JSBN is a bot client which interprets commands through Twitter, requiring no hosting of servers or infected hosts from the command issuer. It is written purely in javascript as a Proof-of-Concept for javascript's botnet potentials.
		* [C2 with twitter](https://pentestlab.blog/2017/09/26/command-and-control-twitter/)
		* [C2 with Telegram](https://github.com/graniet/gshark-framework)
		* [BrainDamage](https://github.com/mehulj94/BrainDamage)
			* A fully featured backdoor that uses Telegram as a C&C server
		* [twittor - twitter based backdoor](https://github.com/PaulSec/twittor)
			* A stealthy Python based backdoor that uses Twitter (Direct Messages) as a command and control server This project has been inspired by Gcat which does the same but using a Gmail account.
		* [Instegogram](https://github.com/endgameinc/instegogram)
		* [canisrufus](https://github.com/maldevel/canisrufus)
			* A stealthy Python based Windows backdoor that uses Github as a command and control server.
	* **SQL Server**
		* [Databases and Clouds: SQL Server as a C2 - Scott Sutherland](https://blog.netspi.com/databases-and-clouds-sql-server-as-a-c2/)
	* **Trello**
		* [TrelloC2](https://github.com/securemode/TrelloC2)
			* Simple C2 over the Trello API
	* **WebDAV**
		* [C2 with webdav](https://pentestlab.blog/2017/09/12/command-and-control-webdav/)
		* [Using WebDAV features as a covert channel](https://arno0x0x.wordpress.com/2017/09/07/using-webdav-features-as-a-covert-channel/)
	* **Web Services**
		* [C2 with Dropbox](https://pentestlab.blog/2017/08/29/command-and-control-dropbox/)
		* [DBC2](https://github.com/Arno0x/DBC2)
			* DBC2 (DropboxC2) is a modular post-exploitation tool, composed of an agent running on the victim's machine, a controler, running on any machine, powershell modules, and Dropbox servers as a means of communication.
		* [C2 with gmail](https://pentestlab.blog/2017/08/03/command-and-control-gmail/)	
		* [Simple domain fronting PoC with GAE C2 server](https://www.securityartwork.es/2017/01/31/simple-domain-fronting-poc-with-gae-c2-server/)
		* [google_socks](https://github.com/lukebaggett/google_socks)
			* A proof of concept demonstrating the use of Google Drive for command and control.
		* [Powershell Github Shell](https://github.com/zlocal/Powershell-Github-Shell)
		* [google_RAT](https://github.com/a-rey/google_RAT)
			* A remote access tool for Windows systems using google apps script as the middle man
	* **WebSockets**
		* [WSC2](https://github.com/Arno0x/WSC2)
			* WSC2 is a PoC of using the WebSockets and a browser process to serve as a C2 communication channel between an agent, running on the target system, and a controller acting as the actual C2 server.
		* [Using WebSockets and IE/Edge for C2 communications](https://arno0x0x.wordpress.com/2017/11/10/https://github.com/leoloobeek/GoG reen/blob/master/README.mdusing-websockets-and-ie-edge-for-c2-communications/)
		* [MurDock - Mutable Universal Relay Document Kit](https://github.com/themson/MurDocK)
			* The purpose of this tool is to provide a protocol independent framework that contains a base set of features that can piggyback on top of any collaborative web platform or service. The base docClient and docServer are meant to be extended upon with Buffer classes written for individual web services. These buffer classes can be plugged into the MurDock framework in order to create a unique shell infrastructure that will always contains a base set of features, as well as the ability to tunnel over any web application traffic for which a buffer class has been constructed. The framework can be extended to operate over lower level protocols if desired.
		* [PetaQ](https://github.com/fozavci/petaqc2)
			* PetaQ is a malware which is being developed in .NET Core/Framework to use websockets as Command & Control (C2) channels. It's designed to provide a Proof of Concept (PoC) websocket malware to the adversary simulation exercises (Red & Purple Team exercises).
	* **WMI-based**
		* [WMImplant](https://github.com/ChrisTruncer/WMImplant)
			* WMImplant is a PowerShell based tool that leverages WMI to both perform actions against targeted machines, but also as the C2 channel for issuing commands and receiving results. WMImplant will likely require local administrator permissions on the targeted machine.	
		* [WheresMyImplant](https://github.com/0xbadjuju/WheresMyImplant)
			* A Bring Your Own Land Toolkit that Doubles as a WMI Provider 
		* [PowerProvider](https://github.com/0xbadjuju/PowerProvider/)
			* PowerProvider: A toolkit to manipulate WMI. Used with WheresMyImplant
* **Papers**<a name="c2papers"></a>
	* [Command & Control: Understanding, Denying and Detecting - 2014 - Joseph Gardiner, Marco Cova, Shishir Nagaraja](https://arxiv.org/ftp/arxiv/papers/1408/1408.1136.pdf)





































---------------------------------	
### <a name="domains"></a>Domains and Domain Related Things
* **General**<a name="dg"></a>
	* **Articles/Writeups**
		* [Domain Dispute - don’t lose that great looking C2 domain - Matt “Rudy” Benton(2020)](https://medium.com/maverislabs/domain-dispute-dont-lose-that-great-looking-c2-domain-8472b6cc4c5b)
* **Domain Fronting**<a name="df"></a>
	* **101**
		* [Blocking-resistant communication through domain fronting](https://www.bamsoftware.com/talks/fronting-pets2015/)
		* [Camouflage at encryption layer: domain fronting](https://www.securityartwork.es/2017/01/24/camouflage-at-encryption-layer-domain-fronting/)
		* [Domain Fronting - Infosec Institute](http://resources.infosecinstitute.com/domain-fronting/)
		* [Continually Enhancing Domain Security on Amazon CloudFront - aws.amazon(2019)](https://aws.amazon.com/blogs/networking-and-content-delivery/continually-enhancing-domain-security-on-amazon-cloudfront/)
	* **Articles/Writeups**
		* [High-reputation Redirectors and Domain Fronting](https://blog.cobaltstrike.com/2017/02/06/high-reputation-redirectors-and-domain-fronting/)
		* [TOR Fronting – Utilising Hidden Services for Privacy](https://www.mdsec.co.uk/2017/02/tor-fronting-utilising-hidden-services-for-privacy/)
		* [Finding Domain frontable Azure domains - thoth / Fionnbharr (@a_profligate)](https://theobsidiantower.com/2017/07/24/d0a7cfceedc42bdf3a36f2926bd52863ef28befc.html)
		* [Domain Fronting Via Cloudfront Alternate Domains](https://www.mdsec.co.uk/2017/02/domain-fronting-via-cloudfront-alternate-domains/)
		* [TTP: Domain Fronting with Metasploit and Meterpreter - beyondbinary](https://beyondbinary.io/articles/domain-fronting-with-metasploit-and-meterpreter/)
		* [Alibaba CDN Domain Fronting - Vincent Yiu](https://medium.com/@vysec.private/alibaba-cdn-domain-fronting-1c0754fa0142)
		* [How I Identified 93k Domain-Frontable CloudFront Domains](https://www.peew.pw/blog/2018/2/22/how-i-identified-93k-domain-frontable-cloudfront-domains)
		* [Metasploit Domain Fronting With Microsoft Azure - chigstuff](https://chigstuff.com/blog/metasploit-domain-fronting-with-microsoft-azure/)
		* [Red Team Insights on HTTPS Domain Fronting Google Hosts Using Cobalt Strike](https://www.cyberark.com/threat-research-blog/red-team-insights-https-domain-fronting-google-hosts-using-cobalt-strike/)
		* [DomainFrontingLists](https://github.com/vysec/DomainFrontingLists)
			* A list of Domain Frontable Domains by CDN
		* [Metasploit Domain Fronting With Microsoft Azure - Chris Higgins](https://chigstuff.com/blog/metasploit-domain-fronting-with-microsoft-azure/)
		* [Being a Good Domain Shepherd - Christopher Maddalena](https://posts.specterops.io/being-a-good-domain-shepherd-57754edd955f?gi=2cadd2578045)
			* [Part 2](https://posts.specterops.io/being-a-good-domain-shepherd-part-2-5e8597c3fe63)
		* [Domain Fronting using StackPath CDN - Vincent Yiu](https://vincentyiu.com/red-team/domain-fronting/domain-fronting-using-stackpath-cdn)
			* A guide to setting up domain fronting, and exploring additional quirks that StackPath can provide.
		* [Hardening Your Azure Domain Front - Steve Borosh](https://medium.com/@rvrsh3ll/hardening-your-azure-domain-front-7423b5ab4f64)
	* **Talks & Videos**
		* [Domain Fronting is Dead, Long Live Domain Fronting Using TLS 1.3 - Erik Hunstad(DEF CON Safe Mode)](https://www.youtube.com/watch?v=TDg092qe50g&list=PL9fPq3eQfaaBk9DFnyJRpxPi8Lz1n7cFv&index=7)
			* Domain fronting, the technique of circumventing internet censorship and monitoring by obfuscating the domain of an HTTPS connection was killed by major cloud providers in April of 2018. However, with the arrival of TLS 1.3, new technologies enable a new kind of domain fronting. This time, network monitoring and internet censorship tools are able to be fooled on multiple levels. This talk will give an overview of what domain fronting is, how it used to work, how TLS 1.3 enables a new form of domain fronting, and what it looks like to network monitoring. You can circumvent censorship and monitoring today without modifying your tools using an open source TCP and UDP pluggable transport tool that will be released alongside this talk.
	* **Tools**
		* **Finding Vulnerable Domains**
			* [DomainFrontDiscover](https://github.com/peewpw/DomainFrontDiscover)
				* Scripts and results for finding domain frontable CloudFront domains
			* [FindFrontableDomains](https://github.com/rvrsh3ll/FindFrontableDomains)
				* Search for potential frontable domains
			* [Simple domain fronting PoC with GAE C2 server](https://www.securityartwork.es/2017/01/31/simple-domain-fronting-poc-with-gae-c2-server/)
				* In this entry we continue with domain fronting; on this occasion we will explore how to implement a simple PoC of a command and control and exfiltration server on Google App Engine (GAE), and we will see how to do the domain fronting from Windows, with a VBS or PowerShell script, to hide interactions with the C2 server.
			* [Finding Frontable Domain](https://github.com/rvrsh3ll/FindFrontableDomains)
* **Tools**<a name="dt"></a>
	* **Identifyin Useful Domains**
		* [Domain Hunter](https://github.com/minisllc/domainhunter)
			* Checks expired domains, bluecoat categorization, and Archive.org history to determine good candidates for phishing and C2 domain names
		* [AIRMASTER](https://github.com/t94j0/AIRMASTER)
			* Use ExpiredDomains.net and BlueCoat to find useful domains for red team.
	* **Domain Reputation/Identification**
		* [Chameleon](https://github.com/mdsecactivebreach/Chameleon)
			* Chameleon is a tool which assists red teams in categorising their infrastructure under arbitrary categories. Currently, the tool supports arbitrary categorisation for Bluecoat, McAfee Trustedsource and IBM X-Force. However, the tool is designed in such a way that additional proxies can be added with ease.
		* [CatMyFish](https://github.com/Mr-Un1k0d3r/CatMyFish)
			* Search for categorized domain that can be used during red teaming engagement. Perfect to setup whitelisted domain for your Cobalt Strike beacon C&C.  It relies on expireddomains.net to obtain a list of expired domains. The domain availability is validated using checkdomain.com
* **Domain Reputation Sites**<a name="dr"></a>
	* [Alien Vault](http://www.alienvault.com)
	* [Isithacked?](http://www.isithacked.com)
	* [Robtex](https://dns.robtex.com)
	* [Scan4You](http://scan4you.net/)
	* [Sucuri](http://sitecheck.sucuri.net/scanner/)
	* [Trustedsource](http://www.trustedsource.org/)
	* [urlQuery](http://urlquery.net/search.php)
	* [URLVoid](http://www.urlvoid.com/scan/)
	* [VirusTotal](https://www.virustotal.com/)
	* [WOT](http://www.mywot.com/en/scorecard)
	* [Zeltser BL](http://zeltser.com)



































-----------------------------------
### <a name="egress"></a>Egress/Exfiltration
* **See <a href="Exfiltration.md">Exfiltration.md</a>**





















--------------
### <a name="empire"></a>Empire
* **Articles**<a name="articles"></a>
	* [Powershell Empire 101 - @spottheplanet](https://ired.team/offensive-security/red-team-infrastructure/powershell-empire-101)
	* [Hunting Red Team Empire C2 Infrastructure](http://www.chokepoint.net/2017/04/hunting-red-team-empire-c2.html)
	* [Athena: The CIA’s RAT vs Empire](https://bneg.io/2017/05/22/athena-the-cias-rat-vs-empire/)
	* [Bringing the hashes home with reGeorg & Empire](https://sensepost.com/blog/2016/bringing-the-hashes-home-with-regeorg-empire/)
	* [Intercepting passwords with Empire and winning](https://sensepost.com/blog/2016/intercepting-passwords-with-empire-and-winning/)
	* [Advanced Weapons Training - for the Empire - Jeremy Johnson](https://www.slideshare.net/JeremyJohnson166/advanced-weapons-training-for-the-empire)
	* [Empire API Cheat Sheet](https://github.com/SadProcessor/Cheats/blob/master/EmpireAPI.md)
	* [Evading Anomaly-Based NIDS with Empire - Utku Sen blog](https://utkusen.com/blog/bypassing-anomaly-based-nids-with-empire.html)
	* [Empire & Tool Diversity: Integration is Key - sixdub](https://www.sixdub.net/?p=627)
	* [Empire Fails - harmj0y](http://www.harmj0y.net/blog/empire/empire-fails/)
	* [Empire Was Great Again…For a Week - CX01N(2020)](https://www.bc-security.org/post/microsoft-makes-empire-great-again)
* **Customizing**<a name="ecustom"></a>
	* [Using PowerShell Empire with a Trusted Certificate](https://www.blackhillsinfosec.com/using-powershell-empire-with-a-trusted-certificate/)
	* [How to Make Empire Communication profiles - bluescreenofjeff](https://github.com/bluscreenofjeff/bluscreenofjeff.github.io/blob/master/_posts/2017-03-01-how-to-make-communication-profiles-for-empire.md)
	* [Empire – Modifying Server C2 Indicators](http://threatexpress.com/2017/05/empire-modifying-server-c2-indicators/)
	* [Empire Domain Fronting](https://www.xorrior.com/Empire-Domain-Fronting/)
	* [Empire without powershell](https://bneg.io/2017/07/26/empire-without-powershell-exe/)
	* [Build Your Own: Plugins in Empire - strikersecurity](https://strikersecurity.com/blog/empire-plugins/)
	* [How to Make Communication Profiles for Empire - Jeff Dimmock](https://posts.specterops.io/how-to-make-communication-profiles-for-empire-46da8554338a)
	* [Reigning the Empire, evading detection - vanmieghem.io](https://vanmieghem.io/reigning-the-empire-evading-detection/)
		* tl;dr: Configure a (valid) certificate and add jitter to have Empire communications stay below the radar.
* **Manual**<a name="edoc"></a>
	* [RedTrooperFM - Empire Module Wiki](https://github.com/SadProcessor/Cheats/blob/master/RedTrooperFM.md)
		* A one page Wiki for all your Empire RTFM needs...
	* [Encrypted Key Exchange understanding - StackOverflow](https://stackoverflow.com/questions/15779392/encrypted-key-exchange-understanding)
* **Modules & Additions/Extensions**<a name="emods"></a>
	* [Empire-mod-Hackplayers](https://github.com/Hackplayers/Empire-mod-Hackplayers)
		* Collection of custom Empire Modules
	* [Sharpire - An implimentation of the Empire Agent in C#](https://github.com/0xbadjuju/Sharpire)
	* [Automated Empire Infrastructure - bneg.io](https://bneg.io/2017/11/06/automated-empire-infrastructure/)
	* [firstorder](https://github.com/tearsecurity/firstorder)
		* firstorder is designed to evade Empire's C2-Agent communication from anomaly-based intrusion detection systems. It takes a traffic capture file (pcap) of the network and tries to identify normal traffic profile. According to results, it creates an Empire HTTP listener with appropriate options.
	* [e2modrewrite](https://github.com/infosecn1nja/e2modrewrite)
		* Convert Empire profiles to Apache mod_rewrite scripts
	* [PrintDemon](https://github.com/BC-SECURITY/Invoke-PrintDemon)
		* This is an PowerShell Empire launcher PoC using PrintDemon and Faxhell. The module has the Faxhell dll already embedded which levages CVE-2020-1048 for privilege escalation. The vulnerability allows an unprivileged user to gain system-level privileges and is based on @ionescu007 PoC.
* **Multi-User GUI**
	* [StarKiller](https://github.com/BC-SECURITY/Starkiller)
		* Starkiller is a Frontend for Powershell Empire. It is an Electron application written in VueJS.
		* [An Introduction to Starkiller - CX01N](https://www.bc-security.org/post/an-introduction-to-starkiller)































--------------
##### <a name="hardware"></a>HW Related/Physical Devices
* **Access**<a name="access"></a>
	* **RDP**
		* [xrdp](https://github.com/neutrinolabs/xrdp)
			* xrdp provides a graphical login to remote machines using Microsoft Remote Desktop Protocol (RDP). xrdp accepts connections from a variety of RDP clients: FreeRDP, rdesktop, NeutrinoRDP and Microsoft Remote Desktop Client (for Windows, Mac OS, iOS and Android).
	* **SSH**
		* [ubuntu.autossh](https://github.com/Monadical-SAS/ubuntu.autossh)
			* Autossh reverse tunnel to central server.
	* **VPN**
		* [Penetration Testing Dropbox Part 2 - VPN Infrastructure - Casey Cammilleri](https://www.sprocketsecurity.com/blog/penetration-testing-dropbox-setup-part2)
		* **Wireguard**
			* [Wireguard - Wikipedia](https://en.wikipedia.org/wiki/Wireguard)
				* WireGuard is a free and open-source software application and communication protocol that implements virtual private network (VPN) techniques to create secure point-to-point connections in routed or bridged configurations. It is run as a module inside the Linux kernel, and aims for better performance and more power saving than the IPsec and OpenVPN tunneling protocols. It was written by Jason A. Donenfeld and is published under the GNU General Public License (GPL) version 2.
			* [wg-access-server](https://github.com/place1/wg-access-server/)
				* wg-access-server is a single binary that provides a WireGuard VPN server and device management web ui. We support user authentication, 1 click device registration that works with Mac, Linux, Windows, Ios and Android including QR codes. You can configure different network isolation modes for better control and more. This project aims to deliver a simple VPN solution for developers, homelab enthusiasts and anyone else feeling adventurous.
* **Dropboxes**<a name="dropboxes"></a>
	* **Articles/Blogpots/Writeups**
		* [A list of current UMPCs with physical keyboard - ciko.io(2019)](https://ciko.io/posts/umpc/)
		* [Making the Perfect Red Team Dropbox (Part 1) - Rogan Dawes(2020)](https://sensepost.com/blog/2020/making-the-perfect-red-team-dropbox-part-1/)
		* [How to Build a Pentest Dropbox - TheCyberMentor(2020)](https://www.youtube.com/watch?v=D2t4ADQnBEk)
		* [DigiDucky - How to setup a Digispark like a rubber ducky](http://www.redteamr.com/2016/08/digiducky/)
		* [Bash Bunny](https://hakshop.com/products/bash-bunny)
		* [How to Build Your Own Penetration Testing Drop Box - BHIS](https://www.blackhillsinfosec.com/?p=5156&)
	* **Talks/Presentations/Videos**
		* [Shells on Cells - Tj McClerain(ShellCon2018)](https://www.youtube.com/watch?v=tRytvE6WCyY&list=PL7D3STHEa66TbZwq9w3S2qWzoJeNo3YYN&index=4)
			* For my talk I'll be going into how to setup a Raspberry Pi Zero W with a Cellular modem to provide out of band persistence inside a target network for the purpose of using it as a pen test drop box. On the technical side of things I'll provide a hardware summary and demo along with code examples to get it all working.
	* **Tools**
		* [P4wnP1](https://github.com/mame82/P4wnP1)
			* P4wnP1 is a highly customizable USB attack platform, based on a low cost Raspberry Pi Zero or Raspberry Pi Zero W.
* **Physical Implants**<a name="implants"></a>
	* **Articles/Writeups**
		* [Implanting a Dropcam](https://www.defcon.org/images/defcon-22/dc-22-presentations/Moore-Wardle/DEFCON-22-Colby-Moore-Patrick-Wardle-Synack-DropCam-Updated.pdf)
	* **Papers**
		* [Stealthy Dopant-Level Hardware Trojans](Hardware level trojans http://sharps.org/wp-content/uploads/BECKER-CHES.pdf)
			* Abstract: In this paper we propose an extremely stealthy approach for implementing hardware Trojans below the gate level, and we evaluate their impact on the security of the target device. Instead of adding additional circuitry to the target design, we insert our hardware Trojans by changing the dopant polarity of existing transistors. Since the modied circuit ap- pears legitimate on all wiring layers (including all metal and polysilicon), our family of Trojans is resistant to most detection techniques, including negrain optical inspection and checking against \golden chips". We demonstrate the e ectiveness of our approach by inserting Trojans into two designs | a digital post-processing derived from Intel's cryptographically secure RNG design used in the Ivy Bridge processors and a side-channel resistant SBox implementation | and by exploring their detectability and their effects on security.
		* [Implementation and Implications of a Stealth Hard-Drive Backdoor](https://www.ibr.cs.tu-bs.de/users/kurmus/papers/acsac13.pdf) 
			* Modern workstations and servers implicitly trust hard disks to act as well-behaved block devices. This paper analyzes the catastrophic loss of security that occurs when hard disks are not trustworthy. First, we show that it is possible to compromise the firmware of a commercial ovt-the-shelf hard drive, by resorting only to public information and reverse engineering. Using such a compromised firmware, we present a stealth rootkit that replaces arbitrary blocks from the disk while they are written, providing a data replacement back- door . The measured performance overhead of the compromised disk drive is less than 1% compared with a normal, non-malicious disk drive. We then demonstrate that a re- mote attacker can even establish a communication channel with a compromised disk to infiltrate commands and to ex-filtrate data. In our example, this channel is established over the Internet to an unmodified web server that relies on the compromised drive for its storage, passing through the original webserver, database server, database storage engine, filesystem driver, and block device driver. Additional experiments, performed in an emulated disk-drive environment, could automatically extract sensitive data such as /etc/shadow (or a secret key le) in less than a minute. This paper claims that the diffculty of implementing such an at- tack is not limited to the area of government cyber-warfare; rather, it is well within the reach of moderately funded criminals, botnet herders and academic researchers.
		* [Inside a low budget consumer hardware espionage implant](https://ha.cking.ch/s8_data_line_locator/)
	* **HID**
		* [What are malicious usb keys and how to create a realistic one? - Elie Bursztein(2016)](https://elie.net/blog/security/what-are-malicious-usb-keys-and-how-to-create-a-realistic-one/)
		* **Teensy**
			* [USB teensy attack set OSX](http://samy.pl/usbdriveby/)
			* [Paensy](https://github.com/Ozuru/Paensy)
				* Paensy is a combination of the word payload and Teensy - Paensy is an attacker-oriented library written for the development of Teensy devices. Paensy simplifies mundane tasks and allows an easier platform for scripting.
				* [Blogpost](http://malware.cat/?p=89)
	* **Tooling**
		* * [USBSamurai — A Remotely Controlled Malicious USB HID Injecting Cable for less than 10$ - Luca Bongiorni](https://medium.com/@LucaBongiorni/usbsamurai-a-remotely-controlled-malicious-usb-hid-injecting-cable-for-less-than-10-ebf4b81e1d0b)
		* [USBsamurai For Dummies - Luca Bongiorni](https://medium.com/@LucaBongiorni/usbsamurai-for-dummies-4bd47abf8f87)
		* [whid-31337](https://github.com/whid-injector/whid-31337)
			* WHID Elite is a GSM-enabled Open-Source Multi-Purpose Offensive Device that allows a threat actor to remotely inject keystrokes, bypass air-gapped systems, conduct mousejacking attacks, do acoustic surveillance, RF replay attacks and much more.
		* [WiFiDuck](https://github.com/spacehuhn/WiFiDuck)
			* Wireless keystroke injection attack platform
		* [Caligo](https://github.com/secgroundzero/caligo)
			* Caligo is a simple C2 for hostile "dropbox" devices management used in physical security assessments. We have been using drop devices for a long time now but we never had an easy way to manage them especially when running multiple engagements at the same time with multiple devices for each. Caligo solves this problem by providing a client and server setup script which allows the user to control all of the devices from a web application.
	* [Blogpost](http://www.offensiveops.io/tools/project-caligo/)
* **Other**
	* [PentestHardware](https://github.com/unprovable/PentestHardware)
		* Kinda useful notes collated together publicly	
	* [PhanTap (Phantom Tap)](https://github.com/nccgroup/phantap)
		* PhanTap is an ‘invisible’ network tap aimed at red teams. With limited physical access to a target building, this tap can be installed inline between a network device and the corporate network. PhanTap is silent in the network and does not affect the victim’s traffic, even in networks having NAC (Network Access Control 802.1X - 2004). PhanTap will analyze traffic on the network and mask its traffic as the victim device. It can mount a tunnel back to a remote server, giving the user a foothold in the network for further analysis and pivoting. PhanTap is an OpenWrt package and should be compatible with any device. The physical device used for our testing is currently a small, inexpensive router, the GL.iNet GL-AR150. You can find a detailed blogpost describing PhanTap [here](https://www.nccgroup.trust/us/our-research/phantap/?research=Public+tools)






































--------------
### <a name="infra"></a>Infrastructure
* **101**<a name="i101"></a>
	* [Red Team Infrastructure Wiki](https://github.com/bluscreenofjeff/Red-Team-Infrastructure-Wiki)
		* Wiki to collect Red Team infrastructure hardening resources
		* Accompanying Presentation: [Doomsday Preppers: Fortifying Your Red Team Infrastructure](https://speakerdeck.com/rvrsh3ll/doomsday-preppers-fortifying-your-red-team-infrastructure)
	* [6 RED TEAM INFRASTRUCTURE TIPS](https://cybersyndicates.com/2016/11/top-red-team-tips/)
* **Articles & Writeups**<a name="iarticles"></a>
	* [Designing Effective Covert Red Team Attack Infrastructure - Jeff Dimmock](https://posts.specterops.io/designing-effective-covert-red-team-attack-infrastructure-767d4289af43)
	* [Building a Better Moat: Designing an Effective Covert Red Team Attack Infrastructure - @bluescreenofjeff](https://speakerdeck.com/bluscreenofjeff/building-a-better-moat-designing-an-effective-covert-red-team-attack-infrastructure)
	* [Infrastructure for Ongoing Red Team Operations](https://blog.cobaltstrike.com/2014/09/09/infrastructure-for-ongoing-red-team-operations/)
	* [How to Build a C2 Infrastructure with Digital Ocean – Part 1](https://www.blackhillsinfosec.com/build-c2-infrastructure-digital-ocean-part-1/)
	* [Automated Red Team Infrastructure Deployment with Terraform - Part 1](https://rastamouse.me/2017/08/automated-red-team-infrastructure-deployment-with-terraform---part-1/)
	* [Migrating Your infrastructure](https://blog.cobaltstrike.com/2015/10/21/migrating-your-infrastructure/)
	* [Route 53 as Pentest Infrastructure - Jared Perry](https://blog.stratumsecurity.com/2018/10/17/route-53-as-a-pentest-infrastructure/)
	* [Automating Red Team Infrastructure with Terraform - @spottheplanet](https://ired.team/offensive-security/red-team-infrastructure/automating-red-team-infrastructure-with-terraform)
	* [Modern C2 Infrastructure with Terraform, DigitalOcean, Covenant and Cloudflare - Riccardo](https://riccardoancarani.github.io/2019-09-28-modern-c2-infra/)
	* [Testing your RedTeam Infrastructure - Adam Chester(2020)](https://blog.xpnsec.com/testing-redteam-infra/)
		* In this post I'm going to start with a quick review of how RedTeam infrastructure is defined in code which would typically live in a Git repo somewhere. More importantly however, we will continue this by looking at ways in which our environments can be tested as they evolve and increase in complexity, finishing with a walkthrough of how we can introduce a CI pipeline into the mix to help automate this testing.
	* [Modern Red Team Infrastructure - Brady Bloxham(2019)](https://silentbreaksecurity.com/modern-red-team-infrastructure/)
	* [Praetorian's Approach to Red Team Infrastructure - Adam Crosser(2020)](https://www.praetorian.com/blog/praetorians-approach-to-red-team-infrastructure)
* **Talks/Presentations/Videos**
	* [Offensive Development: How To DevOps Your Red Team - Dominic Chell(BSidesMCR2019)](https://www.youtube.com/watch?v=n5_V61NI0tA)
		* During this talk we will explore how DevOps principles can be applied to red teaming, focusing on the implementation of a custom CI/CD pipeline to automatically consume, build and deploy existing and custom tooling to an environment in a manner agnostic to any command and control framework.   We will explain how this approach can not only significantly reduce indicators of compromise, but also introduce the capability to programmatically and automatically protect all your tools from DFIR. Following the talk, we will release redpipe, a custom CI/CD pipeline developed by MDSec for use during red team engagements. The future of red teaming is offensive development.
* **HW/SW for Remote Testing**<a name="remote-testing"></a>
	* [Trusted Attack Platform - TrustedSec](https://github.com/trustedsec/tap)
		* TAP is a remote penetration testing platform builder. For folks in the security industry, traveling often times becomes a burden and adds a ton of cost to the customer. TAP was designed to make the deployment of these boxes super simple and create a self-healing and stable platform to deploy remote penetration testing platforms. Essentially the concept is simple, you pre-configure a brand new box and run the TAP setup file. This will install a service on Linux that will be configured the way you want. What it will do is establish a reverse SSH tunnel back to a machine thats exposed on the Internet for you. From there you can access the box locally from the server it connects back to. TAP automatically detects when an SSH connection has gone stale and will automatically rebuild it for you.
	* [Red Team Laptop & Infrastructure (pt 1: Architecture) - hon1nbo](https://hackingand.coffee/2018/02/assessment-laptop-architecture/)
* **Logging & Monitoring**<a name="ilm"></a>
	 **101**
		* [Red Team Telemetry Part 1 - Zach Grace](https://zachgrace.com/posts/red-team-telemetry-part-1/)
		* [Attack Infrastructure Log Aggregation and Monitoring](https://posts.specterops.io/attack-infrastructure-log-aggregation-and-monitoring-345e4173044e)
	* **Talks/Presentations/Videos**
		* [How do I detect technique X in Windows?? Applied Methodology to Definitively Answer this Question - Matt Graeber(Derbycon 2019)](http://www.irongeek.com/i.php?page=videos/derbycon9/1-05-how-do-i-detect-technique-x-in-windows-applied-methodology-to-definitively-answer-this-question-matt-graeber)
			* Traditionally, the answer to this question has been to execute an attack technique in a controlled environment and to observe relevant events that surface. While this approach may suffice in some cases, ask yourself the following questions: ?Will this scale? Will this detect current/future variants of the technique? Is this resilient to bypass?? If your confidence level in answering these questions is not high, it?s time to consider a more mature methodology for identifying detection data sources. With a little bit of reverse engineering, a defender can unlock a multitude of otherwise unknown telemetry. This talk will establish a methodology for identifying detection data sources and will cover concepts including Event Tracing for Windows, WPP, TraceLogging, and security product analysis.
	 	* [Who watches the watchmen? Adventures in red team infrastructure herding and blue team OPSEC failures - Mark Bergman, Marc Smeets(HIP19)](https://www.youtube.com/watch?v=ZezBCAUax6c)
			* In this talk we explain our approach for red team infrastructure herding and using that to bust OPSEC failures of blue teams. We discuss our latest research on this topic and present a new version of our opensource tooling RedELK. 
	 	* [Using blue team techniques in red team ops - Mark Bergman & Marc Smeets(BruCON 0x0A)](https://www.youtube.com/watch?v=OjtftdPts4g)
			* When performing multi-month, multi-C2teamserver and multi-scenario red team operations, you are working with an infrastructure that becomes very large quickly. This makes it harder to keep track of what is happening on it. Coupled with the ever-increasing maturity of blue teams, this makes it more likely the blue team is somewhere analysing parts of your infra and/or artefacts. In this presentation we’ll show you how you can use that to your advantage. We’ll present different ways to keep track of the blue team’s analyses and detections, and to dynamically adjust your infra to fool the blue team. We will first set the scene by explaining common and lesser known components of red teaming infrastructures, e.g. dynamic redirectors, domain fronting revisited, decoy websites, html-smuggling, etc. Secondly, we’ll show how to centralize all your infrastructure’s and ops’ information to an ELK stack, leaving it open for intelligent querying across the entire infrastructure and operation. This will also help with better feedback to the blue team at the end of the engagement. Lastly, we’ll dive into novel ways of detecting a blue team’s investigation and we’ll give examples on how to react to these actions, for example by creating honeypots for the blue team.
	 * **Tools**
	 	* [unindexed](https://github.com/mroth/unindexed/blob/master/README.md)
			* The site is constantly searching for itself in Google, over and over and over, 24 hours a day. The instant it finds itself in Google search results, the site will instantaneously and irrevocably securely delete itself. Visitors can contribute to the public content of the site, these contributions will also be destroyed when the site deletes itself.
	 * **RedELK**
		* [RedELK](https://github.com/outflanknl/RedELK)
			* Red Team's SIEM - tool for Red Teams used for tracking and alarming about Blue Team activities as well as better usability for the Red Team in long term operations.
		* [Introducing RedELK – Part 1: why we need it - Marc Smeets(2019)](https://outflank.nl/blog/2019/02/14/introducing-redelk-part-1-why-we-need-it/)
			* [Part 2 – getting you up and running - Marc Smeets(2020)](https://outflank.nl/blog/2020/02/28/redelk-part-2-getting-you-up-and-running/)
			* [Part 3 – Achieving operational oversight - Marc Smeets(2020)](https://outflank.nl/blog/2020/04/07/redelk-part-3-achieving-operational-oversight/)
		* [Automating a RedELK Deployment Using Ansible - Jason Lang(2020)](https://www.trustedsec.com/blog/automating-a-redelk-deployment-using-ansible/)
	* **Other Setups**
		* [RedTeamSiem](https://github.com/SecurityRiskAdvisors/RedTeamSIEM)
			* Repository of resources for configuring a Red Team SIEM using Elastic
		* [VECTR](https://github.com/SecurityRiskAdvisors/VECTR)
			* VECTR is a tool that facilitates tracking of your red and blue team testing activities to measure detection and prevention capabilities across different attack scenarios. VECTR provides the ability to create assessment groups, which consist of a collection of Campaigns and supporting Test Cases to simulate adversary threats. Campaigns can be broad and span activity across the kill chain, from initial compromise to privilege escalation and lateral movement and so on, or can be a narrow in scope to focus on specific detection layers, tools, and infrastructure. VECTR is designed to promote full transparency between offense and defense, encourage training between team members, and improve detection & prevention success rate across the environment.
* **Web Server**<a name="iws"></a>
	* **Apache**
	* **Nginx**
		* [nginx: Send HTTP User Agent Requests To Specific Backend Server - Vivek Gite(2010)](https://www.cyberciti.biz/faq/nginx-if-conditional-http_user_agent-requests/)	
		* [Resilient Red Team HTTPS Redirection Using Nginx - Adam Brown(2018)](https://coffeegist.com/security/resilient-red-team-https-redirection-using-nginx/)
	* **Routing**
		* **Articles/Blogposts/Writeups**
			* [Introduction To Modern Routing For Red Team Infrastructure - using Traefik, Metasploit, Covenant and Docker]
			* [Hosting and hiding your C2 with Docker and Socat - khast3x(2020)](https://khast3x.club/posts/2020-02-09-C2-Protection-Socat-Docker/)
			* [AWS Lambda Redirector - Adam Chester(2020)](https://blog.xpnsec.com/aws-lambda-redirector/)
			* [Redirecting Cobalt Strike DNS Beacons](http://www.rvrsh3ll.net/blog/offensive/redirecting-cobalt-strike-dns-beacons/)
			* [High-reputation Redirectors and Domain Fronting](https://blog.cobaltstrike.com/2017/02/06/high-reputation-redirectors-and-domain-fronting/)
			* [Cobalt Strike HTTP C2 Redirectors with Apache mod_rewrite - Jeff Dimmock](https://bluescreenofjeff.com/2016-06-28-cobalt-strike-http-c2-redirectors-with-apache-mod_rewrite/)
			* [HTTP Forwarders / Relays - @spottheplanet](https://ired.team/offensive-security/red-team-infrastructure/redirectors-forwarders)
				* Concealing attacking hosts through with redirectors/traffic forwarders using iptables or socat
		* **Samples/Setups**
			* [Apache2Mod Rewrite Setup](https://github.com/n0pe-sled/Apache2-Mod-Rewrite-Setup)
		* **Tools**
			* [Expose](https://github.com/beyondcode/expose)
				* A completely open-source ngrok alternative - written in pure PHP.
			* [Traefik](https://github.com/containous/traefik)
			* [FlaskRedirectorProtector](https://github.com/rvrsh3ll/FlaskRedirectorProtector)
				* Protect your servers with a secret header
	* **BlockRules**
		* **Tools**
			* [redirect.rules](https://github.com/0xZDH/redirect.rules)
				* Quick and dirty dynamic redirect.rules generator
			* [mkhtaccess_red](https://github.com/violentlydave/mkhtaccess_red)
				* Auto-generate an HTaccess for payload delivery -- automatically pulls ips/nets/etc from known sandbox companies/sources that have been seen before, and redirects them to a benign payload.
			 * [Sephiroth](https://github.com/0xdade/sephiroth)
				* A Python3 script to build cloud block lists for servers.
			* [RT-CyberShield](https://github.com/op7ic/RT-CyberShield)
				* Protecting Red Team infrastructure with cyber shield blocking AWS/AZURE/IBM/Digital Ocean/TOR/AV IP/ETC. ranges 
* **SSL/TLS**
	* **JA3**
		* [Impersonating JA3 Fingerprints - Matthew Rinaldi](https://medium.com/cu-cyber/impersonating-ja3-fingerprints-b9f555880e42)
		* [JA3Transport](https://github.com/CUCyber/ja3transport)
			* A Go library that makes it easy to mock JA3 signatures.
* **Automation Tooling**<a name="iat"></a>
	* [Abaddon](https://github.com/wavestone-cdt/abaddon)
		* Red team operations involve miscellaneous skills, last several months and are politically sensitive; they require a lot of monitoring, consolidating and caution. Wavestone’s red team operations management software, Abaddon, has been designed to make red team operations faster, more repeatable, stealthier, while including value-added tools and bringing numerous reporting capabilities.
	* [Paragon](https://github.com/KCarretto/paragon)
		* Paragon is a Red Team engagement platform. It aims to unify offensive tools behind a simple UI, abstracting much of the backend work to enable operators to focus on writing implants and spend less time worrying about databases and css. The repository also provides some offensive tools already integrated with Paragon that can be used during engagements.
	* [SiestaTime](https://github.com/rebujacker/SiestaTime)
		* Red Team Automation tool powered by go and terraform.
	* [Redcloud](https://github.com/khast3x/Redcloud)
		* Automated Red Team Infrastructure deployement using Docker 
	* [Red Baron](https://github.com/Coalfire-Research/Red-Baron)
		* Red Baron is a set of modules and custom/third-party providers for Terraform which tries to automate creating resilient, disposable, secure and agile infrastructure for Red Teams.
	* [RedTeam-Automation - bneg](https://github.com/bneg/RedTeam-Automation)
		* Automating those tasks which can or should be automated
	* [Red Team Hosted Infrastructure](https://github.com/redteaminfra/redteam-infra)
		* This project houses reference deployment recipies that can be used to build Red Team Infrastructure. As such, there are no security guarantees or promises. Use at your own risk. This infrastructure was discussed at CanSecWest 2019 and the slides can be found [here](https://speakerdeck.com/tophertimzen/attack-infrastructure-for-the-modern-red-team)
* **Wireless**<a name="iw"></a>
	* [Rogue Toolkit](https://github.com/InfamousSYN/rogue)
		* The Rogue Toolkit: An extensible toolkit aimed at providing penetration testers an easy-to-use platform to deploy Access Points for the purpose of conducting penetration testing and red team engagements.































------------------
### <a name="payload"></a>Payloads & Stuff
* **Creation & Development**<a name="pcd"></a>
	* **101**
	* **Articles/Blogposts/Writeups**
		* [Software Development Principals for Offensive Developers — Part 1 (Fundamentals) - James(2020)](https://web.archive.org/web/20200219060000/https://medium.com/@two06/software-development-principals-for-offensive-developers-part-1-fundamentals-7293d2ad0bde)
		* [Pentest-and-Development-Tips - 3gstudent](https://github.com/3gstudent/Pentest-and-Development-Tips/blob/master/README-en.md)
		* [Red Team Diary, Entry #3: Custom Malware Development (Establishing A Shell Through the Target’s Browser) - Dimitrios Bougioukas](https://blog.usejournal.com/red-team-diary-entry-3-custom-malware-development-establish-a-shell-through-the-browser-bed97c6398a5)
		* [Red Team Diary, Entry #1: Making NSA’s PeddleCheap RAT Invisible - Dimitrios Bougioukas](https://medium.com/@d.bougioukas/red-team-diary-entry-1-making-nsas-peddlecheap-rat-invisible-f88ccbdc484d)
			* [Slides](https://drive.google.com/file/d/1xBwMuF62eYKv3A2TNRgKNVE_nAViSrVZ/view)
		* [Malware development part 1 - 0xPat](https://0xpat.github.io/Malware_development_part_1/)
			* [Part 2](https://0xpat.github.io/Malware_development_part_2/)
			* [Part 3](https://0xpat.github.io/Malware_development_part_3/)	
		* [Tutorial: Creating a custom full featured implant(Nuages)](https://github.com/p3nt4/Nuages/wiki/Tutorial:-Creating-a-custom-full-featured-implant)
		* [An Introduction to Writing .NET Executables for Pentesters](https://www.peew.pw/blog/2017/11/24/an-introduction-to-writing-net-executables-for-pentesters)
	* **Talks/Presentations/Videos**
		* [C++ for Hackers - Josh Lospinoso(2020)](https://vimeo.com/384348826)
			* Shift5 co-founder, Josh Lospinoso, talks about how C++ can be a vital tool for infosec developers. In this talk, he presents a simple Stage 0 Implant written in modern C++ to tool developers from Army Cyber Command. Along the way, he illuminates many features of C++, the C++ Standard Library, and the Boost Libraries that are highly useful when developing cybersecurity tools.
			* [Code](https://github.com/jlospinoso/cpp-implant)
	* **Existing Code/Tools**
		* [MonkeyWorks](https://github.com/NetSPI/MonkeyWorks)
			* A C# library to facilitate the development of offensive tools against Windows systems.
		* [OffensiveDLR](https://github.com/byt3bl33d3r/OffensiveDLR)
			* Toolbox containing research notes & PoC code for weaponizing .NET's DLR
		* [covertutils - A framework for Backdoor development!](https://github.com/operatorequals/covertutils)
			* This Python package is used to create Agent/Handler backdoors, like metasploit's meterpreter, empire's empire agent, cobalt strike's beacon and so on... It automatically handles all communication channel options, like encryption, chunking, steganography, sessions, etc. With a recent package addition (httpimport), staging from pure Python2/3 is finally possible! With all those set with a few lines of code, a programmer can spend time creating the actual payloads, persistense mechanisms, shellcodes and generally more creative stuff!! The security programmers can stop re-inventing the wheel by implementing encryption mechanisms both Agent-side and Handler-side to spend their time developing more versatile Agents, and generally feature-rich shells!
	* **Bring-Your-Own-`*`**
		* **Land(Compiler/Interpreter)**
			* **Articles/Blogposts/Writeups**
				* [Bring Your Own Land (BYOL) – A Novel Red Teaming Technique - Nathan Kirk](https://www.fireeye.com/blog/threat-research/2018/06/bring-your-own-land-novel-red-teaming-technique.html)
				* [Red Teamer’s Cookbook: BYOI (Bring Your Own Interpreter) - Marcello Salvati(2020)](https://www.blackhillsinfosec.com/red-teamers-cookbook-byoi-bring-your-own-interpreter/)
				* [Red Team: How to embed Golang tools in C# - Shantanu Khandelwal(2020)](https://medium.com/@shantanukhande/red-team-how-to-embed-golang-tools-in-c-e269bf33876a)
				* [Malware Dropping a Local Node.js Instance - Xme(2019)](https://isc.sans.edu/forums/diary/Malware+Dropping+a+Local+Nodejs+Instance/25284/)
			* **Talks/Presentations/Videos**
				* [Quick Retooling in Net for Red Teams - Dimitry Snezhkov(CircleCityCon5.0)](https://www.youtube.com/watch?v=C04TD4dVLSk)
				* [Waiter theres a compiler in my shellcode - Josh Stone(NolaCon2019)](https://www.youtube.com/watch?v=55234oZ0EDU)
					* Join me in this talk about a programming language and environment built specifically with subversive remote control in mind. It's a native code, optimizing compiler that fits in about 5KB of shellcode, requires no runtime environment, can be deployed any way you like, and yet gives you all the access you need on the target host. And to top it all off, it's built around an interactive coding paradigm that makes dynamic exploratory post-exploitation fun. This talk approaches some complex topics, but is designed to be interesting to anyone, whether you're into compiler theory or not. Even a non-coder should get something out of it, so anyone with an interest in offensive hacking is encouraged to attend.
				* [Red Team Level over 9000! Fusing the powah of .NET with a scripting language of your choosing: introducing BYOI (Bring Your own Interpreter) payloads. -  Marcello Salvati(Derbycon2019)](https://www.irongeek.com/i.php?page=videos/derbycon9/1-17-red-team-level-over-9000-fusing-the-powah-of-net-with-a-scripting-language-of-your-choosing-introducing-byoi-bring-your-own-interpreter-payloads-marcello-salvati)
					* [Slides](https://github.com/byt3bl33d3r/Slides/blob/master/RT%20Level%209000%2B%2B_BsidesPR.pdf)
					* With all of the defenses Microsoft has implemented in the PowerShell run-time over the past few years Red Teamers & APT groups have started too shy away from using PowerShell based payloads/delivery mechanisms and migrate over to C#. However, C# is a compiled language, operationally this has a few major downsides: we can?t be as ?flexible? as we could be with scripting languages, setting up a proper development environment has overhead, things need to be compiled etc... in this talk, I will be covering my approach to solving these operational problems by using some of the (possibly?) lesser known features of the .NET framework and introducing BYOI (Bring Your Own Interpreter) payloads which allow you to embed a scripting language of your choosing into any .NET language!
			* **Tools**
				* [typhoon](https://github.com/dsnezhkov/typhoon)
				* [GolanginCsharp](https://github.com/shantanu561993/GolanginCsharp)
					* Project to use Golang inside C# 
				* [EvilVM](https://github.com/jephthai/EvilVM)
					* EvilVM compiler for information security research tools. The project is built around a native code Forth compiler that is deployed as a position independent shellcode. It provides a platform for remote code execution, useful in information security contexts.
					* [Talk](https://www.youtube.com/embed/55234oZ0EDU)
				* [WheresMyImplant](https://github.com/0xbadjuju/WheresMyImplant)
					* A Bring Your Own Land Toolkit that Doubles as a WMI Provider 
	* **Crypters**
		* **Articles/Blogposts/Writeups**
			* [100% evasion - Write a crypter in any language to bypass AV - Xentropy(2020)](https://netsec.expert/2020/02/06/write-a-crypter-in-any-language.html)
		* **Samples**
			* [Xencrypt](https://github.com/the-xentropy/xencrypt)
				* A PowerShell script anti-virus evasion tool
	* **Obfuscation**
		* **Articles/Blogposts/Writeups**
		* **Tools**
			* [Inline C](https://github.com/georgek42/inlinec)
				* Effortlessly write inline C functions in Python
			* [MarkovObfuscate](https://github.com/CylanceSPEAR/MarkovObfuscate)
				* Use Markov Chains to obfuscate data as other data
	* **Publishing**
		* **Linux**
			* [fpm](https://github.com/jordansissel/fpm)
				*  Effing package management! Build packages for multiple platforms (deb, rpm, etc) with great ease and sanity. 
		* **Windows**
			* **Converting an .exe to an .msi**
				* [Exe to MSI Converter](http://www.exetomsi.com/)
				* [EMCO MSI Package Builder](https://emcosoftware.com/msi-package-builder)
	* **Linux Specific**
	* **macOS Specific**
	* **Windows Specific**
		* [Windows-API-Hashing](https://github.com/LloydLabs/Windows-API-Hashing)
			* Windows API resolution via hashing
		* [Windows classic samples](https://github.com/microsoft/Windows-classic-samples)	
			* This repo contains samples that demonstrate the API used in Windows classic desktop applications.
		* [WinPwnage](https://github.com/rootm0s/WinPwnage)
			* The meaning of this repo is to study the techniques. Techniques are found online, on different blogs and repos here on GitHub. I do not take credit for any of the findings, thanks to all the researchers.
	* **Language Specific Stuff**
		* **.NET/C#**
			* See [CSharp Stuff]() in PrivescPostEx
			* [Changeling - A Feature Morphing Creature - Adam Brown](https://coffeegist.com/security/changeling-a-feature-morphing-creature/)
				* This post will be the first post in a continuing series that aims to add new methods to your arsenal, allowing you to build more payloads with less effort on your own assessments. The feature that we’ll be taking a look at today is Embedded Resources in C# projects. This is a feature that will allow us to compile code once, and reuse it on multiple assessments
		* **Go**
			* **Articles/Blogposts/Writeups**
			* **Talks/Presentations/Videos**
				* [(P|G)Ohst Exploitation - Carl Vincent](https://archive.org/details/P-G_Ohst_Exploitation)
					* This talk focuses on showcasing examples of the GO programming language being utilized to rapidly prototype, and ultimately maintain software designed to perform common or useful post-exploitation tasks. Source code for each feature will be provided, and is intended to exaggerate the limited amount of code and code familiarity required to construct relatively complex payloads capable of performing offensive security tasks fully either in an automated, or fully antonymous context.
			* **Libraries**
				* [OffensiveGoLang](https://github.com/bluesentinelsec/OffensiveGoLang)
					* Offensive GoLang is is a collection of Go packages containing commonly used cyber adversary emulation functions. Offensive GoLang accomplishes nothing by itself; rather, it is intended to support rapid red team tool development by providing common functions in a modular format.
* **Delivery & Staging**<a name="pds"></a>
	* **Articles/Blogposts/Writeups**
		* [Windows oneliners to download remote payload and execute arbitrary code](https://arno0x0x.wordpress.com/2017/11/20/windows-oneliners-to-download-remote-payload-and-execute-arbitrary-code/)
		* [Staging over HTTPS and DNS simultaneously with Cobalt Strike and Shellter - HunnicCyber](https://blog.hunniccyber.com/staging-over-https-and-dns-simultaneously-with-cobalt-strike-2/)
			* This blog post is about how to create a binary that mimics an original signed binary, injected with both DNS and HTTPs Cobalt Strike stager shellcode, and then to deliver it via a Word Macro that uses domain fronting to request the binary from a legitimate Microsoft domain.
		* [Mark-of-the-Web from a red team's perspective - Stan Hegt](https://outflank.nl/blog/2020/03/30/mark-of-the-web-from-a-red-teams-perspective/)
	* **Tools**
		* [DNSlivery](https://github.com/no0be/DNSlivery)
			* Easy files and payloads delivery over DNS.
		* [go-deliver](https://github.com/0x09AL/go-deliver)
			* Go-deliver is a payload delivery tool coded in Go.
		* [Pwndrop](https://github.com/kgretzky/pwndrop)
			*  Self-deployable file hosting service for red teamers, allowing to easily upload and share payloads over HTTP and WebDAV. 
			* [Pwndrop - Self-hosting Your Red Team Payloads - Kuba Gretzky(2020)](https://breakdev.org/pwndrop/)
		* [Satellite](https://github.com/t94j0/satellite)
			* Satellite is an web payload hosting service which filters requests to ensure the correct target is getting a payload. This can also be a useful service for hosting files that should be only accessed in very specific circumstances.
			* [Blogpost](https://posts.specterops.io/satellite-a-payload-and-proxy-service-for-red-team-operations-aa4500d3d970)
	* **File smuggling**<a name="fsm"></a>
		* **Articles/Blogposts/Writeups**
			* [Generic bypass of next-gen intrusion / threat / breach detection systems - Zoltan Balazs(2015)](https://www.mrg-effitas.com/research/generic-bypass-of-next-gen-intrusion-threat-breach-detection-systems/)
			* [HTML smuggling explained - Stan Hegt(2018)](https://outflank.nl/blog/2018/08/14/html-smuggling-explained/)
			* [Smuggling HTA files in Internet Explorer/Edge - Richard Warren(2017)](https://www.nccgroup.com/us/about-us/newsroom-and-events/blog/2017/august/smuggling-hta-files-in-internet-exploreredge/)
			* [File Smuggling with HTML and JavaScript - @spottheplanet](https://ired.team/offensive-security/defense-evasion/file-smuggling-with-html-and-javascript)
			* [Strange Bits: HTML Smuggling and GitHub Hosted Malware - Karsten Hahn(2019)](https://www.gdatasoftware.com/blog/2019/05/31695-strange-bits-smuggling-malware-github)
		* **Tools**	
			* [IronSquirrel](https://github.com/MRGEffitas/Ironsquirrel)
				* https://github.com/MRGEffitas/Ironsquirrel
			* [EmbedInHTML](https://github.com/Arno0x/EmbedInHTML)
				* What this tool does is taking a file (any type of file), encrypt it, and embed it into an HTML file as resource, along with an automatic download routine simulating a user clicking on the embedded ressource. Then, when the user browses the HTML file, the embedded file is decrypted on the fly, saved in a temporary folder, and the file is then presented to the user as if it was being downloaded from the remote site. Depending on the user's browser and the file type presented, the file can be automatically opened by the browser.
* **Keying**<a name="keying"></a>
	* **Keying**
		* **Articles**
			* [Mesh design pattern: hash-and-decrypt - rdist(2007)](https://web.archive.org/web/20200727221946/https://rdist.root.org/2007/04/09/mesh-design-pattern-hash-and-decrypt/)
			* [Bradley, hash-and-decrypt, Gauss ... a brief history of armored malware and malicious crypto - Fred Raynal(2012)](https://blog.quarkslab.com/bradley-hash-and-decrypt-gauss-a-brief-history-of-armored-malware-and-malicious-crypto.html)
			* [Keying Payloads for Scripting Languages - @leoloobeek(2017)](https://adapt-and-attack.com/2017/11/15/keying-payloads-for-scripting-languages/)
		* **Talks/Presentations/Videos**
			* [Context-Keyed Payload Encoding: Fighting The Next Generation of IDS - Dimitris Glynos(AthCon2010)](https://www.youtube.com/watch?v=mHMULvGynSU)
				* [Slides](https://census-labs.com/media/context-keying-slides.pdf)
				* [Paper](http://census.gr/media/context-keying-whitepaper.pdf)
				* Exploit payload encoding allows hiding maliciouspayloads from modern Intrusion Detection Systems (IDS). Although metamorphic and polymorphic encoding allow such payloads to be hidden from signature-based and anomaly-based IDS,these techniques fall short when the payload is being examined by IDS that can trace the execution of malicious code. Context-keyed encodingis a technique that allows the attacker to encrypt the malicious payload in such a way, that it canonly be executed in an environment (context) withspecific characteristics. By selecting an environment characteristic that will not be present during the IDS trace (but will be present on the target host), the attacker may evade detection by advanced IDS. This paper focuses on the current research in context-keyed payload encoding and proposes a novel encoder that surpasses many of the limitations found in its predecessors.
			* [Advanced Payload Strategies: “What is new, what works and what is hoax?”](https://www.troopers.de/events/troopers09/220_advanced_payload_strategies_what_is_new_what_works_and_what_is_hoax/)
				* This talk focuses on the shellcode perspective and it’s evolution. From the simplest {shell}code to the polymorphism to bypass filters and I{D|P}S (which has lots of new ideas, like application-specific decoders, decoders based on architecture-instructions, and many others), passing through syscall proxying and injection, this talk will explain how it works and how effective they are against the new evolving technologies like network code emulation, with live demonstrations. There is long time since the first paper was released about shellcoding. Most of modern text just tries to explain the assembly structure and many new ideas have just been released as code, never been detailed or explained. The talk will try to fix this gap, also showing some new ideas and considering different architectures.
			* [Genetic Malware: Designing Payloads for Specific Targets - Travis Morrow, Josh Pitts(2016)](https://www.youtube.com/watch?v=WI8Y24jTTlw)
				* [Slides](https://raw.githubusercontent.com/Genetic-Malware/Ebowla/master/Eko_2016_Morrow_Pitts_Master.pdf)
				* [Ebowla @ Infiltrate](https://downloads.immunityinc.com/infiltrate-archives/Genetic_Malware_Travis_Morrow_Josh_Pitts.pdf)
			* [Protect Your Payloads Modern Keying Techniques - Leo Loobeek(Derybcon2018)](https://www.youtube.com/watch?v=MHc3XP3XC4I)
				* Our payloads are at risk! Incident responders, threat hunters, and automated software solutions are eager to pick apart your new custom dropper and send you back to square one. One answer to this problem is encrypting your payload with key derivation functions ("keying") which leverages a variety of local and remote resources to build the decryption key. Throughout this talk I will present modern keying techniques and demo some tools to help along the way. I will start with showing how easy it is to discover attacker infrastructure or techniques in the payloads we commonly use every day. I will then quickly review how keying helps and the considerations when generating keyed payloads. Throughout the presentation many practical examples of keying techniques will be provided which can be used for typical pentests or full red team operations. Finally I will introduce KeyServer, a new piece to add to your red team infrastructure which handles advanced HTTP and DNS keying. Using unprotected payloads during ops should be a thing of the past. Let’s regain control of our malicious code and make it harder on defenders! This talk is based on the original research of environmental keying by Josh Pitts and Travis Morrow.
		* **Papers**
			* [Environmental Key Generation towards Clueless Agents - J. Riordan and B. Schneier(1998)](https://www.schneier.com/academic/archives/1998/06/environmental_key_ge.html)
				* In this paper, we introduce a collection of cryptographic key constructions built from environmental data that are resistant to adversarial analysis and deceit. We expound upon their properties and discuss some possible applications; the primary envisioned use of these constructions is in the creation of mobile agents whose analysis does not reveal their exact purpose.
			* [Strong Cryptography Armoured Computer VirusesForbidding Code Analysis: the bradley virusEric Filiol(2004)](https://hal.inria.fr/inria-00070748/document)
				* Imagining what the nature of future viral attacks might look like is the key to successfully protecting against them. This paper discusses how cryptography and key management techniques may definitively checkmate antiviral analysis and mechanisms. We present a generic virus, denoted bradley which protects its code with a very secure, ultra-fast symmetric encryption. Since the main drawback of using encryption in that case lies on the existence of the secret key or information about it within the viral code, we show how to bypass this limitation by using suitable key management techniques. Finally, we show that the complexity of the bradley code analysis is at least as high as that of the cryptanalysis of its underlying encryption algorithm.
			* [Foundations and applications for secure triggers - Ariel Futoransky, Emiliano  Kargieman, Carlos Sarraute, Ariel  Waissbein(2006)](https://dl.acm.org/doi/10.1145/1127345.1127349)
				* Imagine there is certain content we want to maintain private until some particular event occurs, when we want to have it automatically disclosed. Suppose, furthermore, that we want this done in a (possibly) malicious host. Say the confidential content is a piece of code belonging to a computer program that should remain ciphered and then “be triggered” (i.e., deciphered and executed) when the underlying system satisfies a preselected condition, which must remain secret after code inspection. In this work we present different solutions for problems of this sort, using different “declassification” criteria, based on a primitive we call secure triggers. We establish the notion of secure triggers in the universally composable security framework of Canetti [2001] and introduce several examples. Our examples demonstrate that a new sort of obfuscation is possible. Finally, we motivate its use with applications in realistic scenarios.
			* [Context-keyed Payload Encoding: Preventing Payload Disclosure via Context - 	druid@caughq.org(2008)](http://www.uninformed.org/?v=9&a=3)
			* [Malicious cryptography. . . reloaded - Eric Filiol, Fr'ed'eric Raynal(CanSecWest2008)](https://cansecwest.com/csw08/csw08-raynal.pdf)
			* [Context-keyed Payload Encoding:Fighting the Next Generation of IDS - Dimitrios A. Glynos(2010)](http://census.gr/media/context-keying-whitepaper.pdf)
			* [Impeding Automated Malware Analysis with Environment-sensitive Malware - Chengyu Song, Paul Royal, Wenke Lee(2012)](https://www.usenix.org/conference/hotsec12/workshop-program/presentation/song)
				* To solve the scalability problem introduced by the exponential growth of malware, numerous automated malware analysis techniques have been developed. Unfortunately, all of these approaches make previously unaddressed assumptions that manifest as weaknesses to the tenability of the automated malware analysis process. To highlight this concern, we developed two obfuscation techniques that make the successful execution of a malware sample dependent on the unique properties of the original host it infects. To reinforce the potential for malware authors to leverage this type of analysis resistance, we discuss the Flashback botnet’s use of a similar technique to prevent the automated analysis of its samples.
			* [Sleeping Your Way out of theSandbox - Hassan  Mourad(2015)](https://www.sans.org/reading-room/whitepapers/malicious/sleeping-sandbox-35797)
				* In recent years,the security landscape has witnessed the rise of a new breed of malware, Advanced  Persistence  Threat,  or  APT  for  short.  With  all  traditional  security  solutions failing  to  address  this  new  threat,  a  demand  was  created  for  new  solutions  that  are capable of addressing the advanced capabilities of APT. One of the offeredsolutions was file-based  sandboxes,asolution  that  dynamically  analyzes  files  and  judgestheir  threat levelsbased  on  their  behavior  in  an  emulated/virtual  environment.  But  security  is  a  cat and mouse game, and malware authors are always trying to detect/bypass such measures. Some of the common techniques used by malware for sandbox evasionwill be discussed in  this  paper. This  paperwill  also  analyze  how  to  turn somecountermeasuresused  by sandboxes against it. Finally, itwill introduce some new ideas for sandbox evasion along with recommendationsto address them.
			* [Hot Knives Through Butter: Evading File-based Sandboxes - Abhishek Singh, Zheng Bu(2014)](https://www.fireeye.com/content/dam/fireeye-www/current-threats/pdfs/pf/file/fireeye-hot-knives-through-butter.pdf)
		* **Tools**
			* **Metasploit**
				* [Hostname-based Context Keyed Payload Encoder - Metasploit Module](https://github.com/rapid7/metasploit-framework/blob/master//modules/encoders/x64/xor_context.rb)
					* 'Context-Keyed Payload Encoder based on hostname and x64 XOR encoder.'	
			* [EBOWLA](https://github.com/Genetic-Malware/Ebowla)
				* Framework for Making Environmental Keyed Payloads
			* [keyring](https://github.com/leoloobeek/keyring)
				* KeyRing was written to make key derivation functions (keying) more approachable and easier to quickly develop during pentesting and red team operations. Keying is the idea of encrypting your original payload with local and remote resources, so it will only decrypt on the target system or under other situations.
			* [satellite](https://github.com/t94j0/satellite)
				* [Satellite: A Payload and Proxy Service for Red Team Operations - Max Harley](https://posts.specterops.io/satellite-a-payload-and-proxy-service-for-red-team-operations-aa4500d3d970)
				* Satellite is an web payload hosting service which filters requests to ensure the correct target is getting a payload. This can also be a useful service for hosting files that should be only accessed in very specific circumstances.
			* [GoGreen](https://github.com/leoloobeek/GoGreen)
				* This project was created to bring environmental (and HTTP) keying to scripting languages. As its common place to use PowerShell/JScript/VBScript as an initial vector of code execution, as a result of phishing or lateral movement, I see value of the techniques for these languages.
			* [keyserver](https://github.com/leoloobeek/keyserver)
				* Easily serve HTTP and DNS keys for proper payload protection
			* [Keyring](https://github.com/leoloobeek/keyring)
				* Proper Payload Protection Prevents Poor Performance. KeyRing was written to make key derivation functions (keying) more approachable and easier to quickly develop during pentesting and red team operations. Keying is the idea of encrypting your original payload with local and remote resources, so it will only decrypt on the target system or under other situations.
			* [Spotter](https://github.com/matterpreter/spotter)
				* Spotter is a tool to wrap payloads in environmentally-keyed, AES256-encrypted launchers. These keyed launchers provide a way to ensure your payload is running on its intended target, as well as provide a level of protection for the launcher itself.
* **Storage**<a name="pstorage"></a>
	* [Cross-Site Phishing - ](https://blog.obscuritylabs.com/merging-web-apps-and-red-teams/)
	* [Windows Event Log to the Dark Side — Storing Payloads and Configurations - Mustafa(2018)](https://medium.com/@5yx/windows-event-log-to-the-dark-side-storing-payloads-and-configurations-9c8ad92637f2)
	* [Offensive Encrypted Data Storage](http://www.harmj0y.net/blog/redteaming/offensive-encrypted-data-storage/)
	* [Offensive Encrypted Data Storage (DPAPI edition)](https://posts.specterops.io/offensive-encrypted-data-storage-dpapi-edition-adda90e212ab)
* **Examples/Samples**<a name="pes"></a>
	* **File Clone**
		* [MetaTwin](https://github.com/minisllc/metatwin)
			* The project is designed as a file resource cloner. Metadata, including digital signature, is extracted from one file and injected into another. Note: Signatures are copied, but no longer valid.
			* [Blogpost](http://threatexpress.com/2017/10/metatwin-borrowing-microsoft-metadata-and-digital-signatures-to-hide-binaries/)
	* **Batch Scripts**
		* [APT Simulator](https://github.com/NextronSystems/APTSimulator)
			* APT Simulator is a Windows Batch script that uses a set of tools and output files to make a system look as if it was compromised
	* **C/C++**
		* [Ps-Tools](https://github.com/outflanknl/Ps-Tools)
			* an advanced process monitoring toolkit for offensive operations.
			* [Red Team Tactics: Advanced process monitoring techniques in offensive operations - Cornelis de Plaa(2020)](https://outflank.nl/blog/2020/03/11/red-team-tactics-advanced-process-monitoring-techniques-in-offensive-operations/)
		* [revsh](https://github.com/emptymonkey/revsh)
			* A reverse shell with terminal support, data tunneling, and advanced pivoting capabilities.
	* **C#**
		* [QuasarRAT](https://github.com/quasar/QuasarRAT)
			* Quasar is a fast and light-weight remote administration tool coded in C#. Providing high stability and an easy-to-use user interface, Quasar is the perfect remote administration solution for you.
		* [RedPeanut](https://github.com/b4rtik/RedPeanut)
			* RedPeanut is a small RAT developed in .Net Core 2 and its agent in .Net 3.5 / 4.0.
	* **Go**
		* [CHAOS](https://github.com/tiagorlampert/CHAOS)
			* Windows payload generator in go
		* [gscript](https://github.com/gen0cide/gscript)
			* Gscript is a framework for building multi-tenant executors for several implants in a stager. The engine works by embedding runtime logic (powered by the V8 Javascript Virtual Machine) for each persistence technique. This logic gets run at deploy time on the victim machine, in parallel for every implant contained with the stager. The Gscript engine leverages the multi-platform support of Golang to produce final stage one binaries for Windows, Mac, and Linux.
			* [Payload Delivery for DevOps : Building a Cross-Platform Dropper Using the Genesis Framework, Metasploit and Docker - khastex(2020)](https://khast3x.club/posts/2020-06-27-Cross-Platform-Dropper/)
	* **JavaScript**
		* [Harlem Shake JS script](https://gist.github.com/devn/5007287)
	* **Lua**
	* **PowerShell**
		* [Invoke-BSOD](https://github.com/peewpw/Invoke-BSOD)
			* A PowerShell script to induce a Blue Screen of Death (BSOD) without admin privileges. Also enumerates Windows crash dump settings. This is a standalone script, it does not depend on any other files.
		* [PowerDropper](https://github.com/gigajew/PowerDropper)
			* App that generates PowerShell dropper scripts for .NET executables
		* [PowerStager](https://github.com/z0noxz/powerstager)
			* This script creates an executable stager that downloads a selected powershell payload, loads it into memory and executes it using obfuscated EC methods. The script will also encrypt the stager for dynamic signatures and some additional obfuscation. This enables the actual payload to be executed indirectly without the victim downloading it, only by executing the stager. The attacker can then for example implement evasion techniques on the web server, hosting the payload, instead of in the stager itself.
	* **Python**
		* [Pupy](https://github.com/n1nj4sec/pupy)
			* Pupy is an opensource, multi-platform Remote Administration Tool with an embedded Python interpreter. Pupy can load python packages from memory and transparently access remote python objects. Pupy can communicate using different transports and have a bunch of cool features & modules. On Windows, Pupy is a reflective DLL and leaves no traces on disk.
			* [Pupy WebSocket Transport](https://bitrot.sh/post/28-11-2017-pupy-websocket-transport/)
		* [RedSails](https://github.com/BeetleChunks/redsails)
			* Python based post-exploitation project aimed at bypassing host based security monitoring and logging. [DerbyCon 2017 Talk](https://www.youtube.com/watch?v=Ul8uPvlOsug)
		* [stupid_malware](https://github.com/andrew-morris/stupid_malware)
			* Python malware for pentesters that bypasses most antivirus (signature and heuristics) and IPS using sheer stupidity
		* [Stitch](https://github.com/nathanlopez/Stitch)
			* This is a cross platform python framework which allows you to build custom payloads for Windows, Mac OSX and Linux as well. You are able to select whether the payload binds to a specific IP and port, listens for a connection on a port, option to send an email of system info when the system boots, and option to start keylogger on boot. Payloads created can only run on the OS that they were created on.
		* [Ares](https://github.com/sweetsoftware/Ares)
			* Ares is a Python Remote Access Tool.
		* [WEASEL](https://github.com/facebookincubator/WEASEL)
			* WEASEL is a small in-memory implant using Python 3 with no dependencies. The beacon client sends a small amount of identifying information about its host to a DNS zone you control. WEASEL server can task clients to execute pre-baked or arbitrary commands. WEASEL is a stage 1 payload, meant to be difficult to detect and useful for regaining access when your noisy full-featured stages are caught.
	* [Dragon: A Windows, non-binding, passive download / exec backdoor](http://www.shellntel.com/blog/2015/6/11/dragon-a-windows-non-binding-passive-downloadexec-backdoor)














































--------------
### <a name="simtools"></a> Adversary Simulation Stuff
* **Articles/Blogposts/Writeups**<a name="sta"></a>
	* [Offensive Tool Design and the Weaponization Dilemma - Matt Graeber(2015)](http://www.exploit-monday.com/2015/12/offensive-tool-design-and-weaponization.html)
	* [The PowerSploit Manifesto - Matt Graeber(2015)](http://www.exploit-monday.com/2015/12/the-powersploit-manifesto.html)
	* [Invoke-Adversary – Simulating Adversary Operations - Moti Bani](https://blogs.technet.microsoft.com/motiba/2018/04/09/invoke-adversary-simulating-adversary-operations/)
	* [Advanced Threat Analytics Attack Simulation Playbook - Microsoft](https://gallery.technet.microsoft.com/Advanced-Threat-Analytics-8b0a86bc)
* **Talks/Presentations/Videos**<a name="stpv"></a>
	* [Quantify Your Hunt: Not Your Parents’ Red Team - Devon Kerr, Roberto Rodriguez(2018)](https://www.youtube.com/watch?v=u_RaWTzB1wA)
		* The security marketplace is saturated with product claims of detection coverage that have been almost impossible to evaluate, all while intrusions continue to make headlines. To help organizations better understand the detection provided by a commercial or open-source technology platform, a framework is necessary to measure depth and breadth of coverage. This presentation builds on the MITRE ATT&CK framework by explaining how to measure the coverage and quality of ATT&CK, while demonstrating open-source Red Team tools and automation that generate artifacts of post-exploitation.
	* [Automated Adversary Emulation - David Hunt(BSidesCharm2019)](https://www.youtube.com/watch?v=gTGnHXgqZCo)
		* CALDERA is an open-source application designed to automate adversary emulation. With CALDERA, blue teams can create adversary profiles based on ATT&CK, unleashing them on their networks to test their vulnerability to specific techniques. Learn how to use and configure CALDERA to run a variety of tests, ranging from small scoped and heavily scripted, to AI-driven fully automated operations.
	* [RedSourcing: Cyber War Tool Development Outsourcing - Christopher Glyer, Nick Carr(Cyber June'gle Virtual Summit 2020)](https://www.youtube.com/watch?v=tA37b7kOBy8&list=PLruly0ngXhPGvyl-gOp4d_TvIiedloX1l&index=8)
* **Adversary Simulation Tools**<a name="sast"></a>
	* **Self-Contained**
		* [Caldera](https://github.com/mitre/caldera)
			* CALDERA is an automated adversary emulation system that performs post-compromise adversarial behavior within enterprise networks. It generates plans during operation using a planning system and a pre-configured adversary model based on the Adversarial Tactics, Techniques & Common Knowledge (ATT&CK™) project. These features allow CALDERA to dynamically operate over a set of systems using variable behavior, which better represents how human adversaries perform operations than systems that follow prescribed sequences of actions.
		* [DumpsterFire](https://github.com/TryCatchHCF/DumpsterFire)
			* [Slides](https://github.com/TryCatchHCF/DumpsterFire/raw/master/CactusCon_2017_Presentation/DumpsterFire_CactusCon_2017_Slides.pdf)
			* The DumpsterFire Toolset is a modular, menu-driven, cross-platform tool for building repeatable, time-delayed, distributed security events. Easily create custom event chains for Blue Team drills and sensor / alert mapping. Red Teams can create decoy incidents, distractions, and lures to support and scale their operations. Turn paper tabletop exercises into controlled "live fire" range events. Build event sequences ("narratives") to simulate realistic scenarios and generate corresponding network and filesystem artifacts.
		* [Metta](https://github.com/uber-common/metta)
			* An information security preparedness tool to do adversarial simulation. This project uses Redis/Celery, python, and vagrant with virtualbox to do adversarial simulation. This allows you to test (mostly) your host based instrumentation but may also allow you to test any network based detection and controls depending on how you set up your vagrants. The project parses yaml files with actions and uses celery to queue these actions up and run them one at a time without interaction.
		* [Invoke-Apex](https://github.com/securemode/Invoke-Apex)
			* Invoke-Apex is a PowerShell-based toolkit consisting of a collection of techniques and tradecraft for use in red team, post-exploitation, adversary simulation, or other offensive security tasks. It can also be useful in identifying lapses in "malicious" activity detection processes for defenders as well.
		* [Red Team Automation (RTA)](https://github.com/endgameinc/RTA)
			* RTA provides a framework of scripts designed to allow blue teams to test their detection capabilities against malicious tradecraft, modeled after MITRE ATT&CK. RTA is composed of python scripts that generate evidence of over 50 different ATT&CK tactics, as well as a compiled binary application that performs activities such as file timestopping, process injections, and beacon simulation as needed.
		* [ezEmu](https://github.com/jwillyamz/ezEmu)
			* ezEmu enables users to test adversary behaviors via various execution techniques. Sort of like an "offensive framework for blue teamers", ezEmu does not have any networking/C2 capabilities and rather focuses on creating local test telemetry.
		* [PurpleSharp](https://github.com/mvelazc0/PurpleSharp)
			* PurpleSharp is a C# adversary simulation tool that executes adversary techniques with the purpose of generating attack telemetry in monitored Windows environments. Detection engineering teams can leverage this telemetry to identify gaps in visibility as well as test the resilience, improve existing and build new detection analytics.
		* [PurpleSpray](https://github.com/mvelazc0/PurpleSpray)
			* PurpleSpray is an adversary simulation tool that executes password spray behavior under different scenarios and conditions with the purpose of generating attack telemetry in properly monitored Windows enterprise environments. Blue teams can leverage PurpleSpray to identify gaps in visibility as well as test the resilience, improve existing and build new detection analytics for password spraying attacks.
		* [Leonidas](https://github.com/FSecureLABS/leonidas)
			* This is the repository containing Leonidas, a framework for executing attacker actions in the cloud. It provides a YAML-based format for defining cloud attacker tactics, techniques and procedures (TTPs) and their associated detection properties.
		* [0xsp-Mongoose](https://github.com/lawrenceamer/0xsp-Mongoose)
			* A unique framework for cybersecurity simulation and red teaming operations, windows auditing for newer vulnerabilities, misconfigurations and privilege escalations attacks, replicate the tactics and techniques of an advanced adversary in a network.
	* **Tooling Automation**
		* [AutoTTP](https://github.com/jymcheong/AutoTTP)
			* Automated Tactics Techniques & Procedures. Re-running complex sequences manually for regression tests, product evaluations, generate data for researchers & so on can be tedious. I toyed with the idea of making it easier to script Empire (or any frameworks/products/toolkits that provide APIs like Metasploit (RPC), Cobalt-Strike & so on) using IDE like Visual Studio Code (or equivalent). So I started to design AutoTTP. This is still very much work in progress. Test with Empire 2.2.
		* [Purple Team ATT&CK Automation](https://github.com/praetorian-code/purple-team-attack-automation)
			* Praetorian's public release of our Metasploit automation of MITRE ATT&CK™ TTPs














-----------------------
### <a name="unusual"></a> Pen Testing Specific Stuff(that doesn't fit in PrivEsc/PostEx or Network_Attacks)
* **AIX<a name="aix"></a>
	* **General**
		* [AIX for Penetration Testers 2017 thevivi.net](https://thevivi.net/2017/03/19/aix-for-penetration-testers/)
		* [Hunting Bugs in AIX : Pentesting writeup](https://rhinosecuritylabs.com/2016/11/03/unix-nostalgia-hunting-zeroday-vulnerabilities-ibm-aix/)
		* [Penetration Testing Trends John Strand - Derbycon6](https://www.youtube.com/watch?v=QyxdUe1iMNk)
* **Embedded<a name="embedded"></a>
	* **General**
		* [War Stories on Embedded Security Pentesting IoT Building Managers and how to do Better Dr Jared - Derbycon7](https://www.youtube.com/watch?v=bnTWysHT0I4&index=8&list=PLNhlcxQZJSm-PKUZTYe1C94ymf0omysM3)
* **Faxes, Printers, Other**
	* **Talks/Presentations/Videos**
		* [Why You Should Fear Your "mundane" Office Equipment - Daniel Romero, Mario Rivas(Defcon27)](https://www.youtube.com/watch?v=3X-ZnlyGuWc)
			*  In this talk we walk through the entire research engagement, from initial phases such as threat modelling to understand printer attack surfaces to the development of attack methodologies and fuzzing tools used to target printer-specific protocols and functions. Besides of remarking important vulnerabilities found and their respective CVE’s, proof of concept exploits showing how it is possible to gain full control of printers and all of the data they manage will be presented. This will show how to use enterprise printers as a method of persistence on a network, perhaps to exfiltrate sensitive data or support C2 persistence on Red Team engagements. We also address a number of challenges that researchers can face when performing vulnerability research on devices such as printers and how we used different techniques to overcome these challenges, working with limited to no debugging and triage capabilities. We also present mitigations that printer manufacturers can implement in order to reduce printer attack surfaces and render exploitation more difficult.
* **IBM Lotus**
	* [Domi-Owned](https://github.com/coldfusion39/domi-owned)
		* Domi-Owned is a tool used for compromising IBM/Lotus Domino servers.
* **MainFrames** <a name="main"></a>
	* [Soldier of Fortran Tumblr](https://mainframed767.tumblr.com/)
	* [Internet Mainframe Project](https://mainframesproject.tumblr.com/)
	* **101**
		* [Introduction to z/OS and IBM mainframes world and security](https://www.whitewinterwolf.com/posts/2017/10/01/introduction-to-zos-and-ibm-mainframes-world-and-security/)
		* [mainframed767 - tumblr(Soldier of Fortran)](https://mainframed767.tumblr.com/post/43170687339/shmoocon-presentation-links?is_related_post=1)
		* [Everything you wanted to know about mainframe security, pen testing and vulnerability scanning .. But were  too afraid to ask!](http://www.newera.com/INFO/SEC_12_17_2015.pdf)
		* [Introduction to the New Mainframe z/OS Basics](https://www.redbooks.ibm.com/redbooks/pdfs/sg246366.pdf)
		* [Learning the Mainframe - Kurt's Blog](https://kurthaeusler.wordpress.com/2016/11/16/learning-the-mainframe/)
		* [So, you want your own mainframe? // Hercules z/Architecture Emulator Tutorial](https://modernmainframer.com/2017/01/30/so-you-want-your-own-mainframe-hercules-zarchitecture-emulator-tutorial/)
		* [Master the Mainframe - IBM](https://www.ibm.com/it-infrastructure/z/education/master-the-mainframe)
	* **Reference**
		* [MVS Commands](http://hansen-family.com/mvs/MVS%20Commands.htm)
		* [Command reference](https://www.redbooks.ibm.com/tips/TIPS0091/tips0091.pdf)
			* This summary lists many of the commonly used commands (with  brief descriptions) for FTP and TCP/IP, as well as related z/OS,  z/VM, VSE, Linux, and VTAM commands. 
		* [TimeShare400](http://www.timeshare400.com/products/individual-accounts/)
	* **Articles/Writeups**
		* [2017 - A New Look at Mainframe Hacking and Penetration Testing v2.2](https://www.slideshare.net/rmfeio/2017-a-new-look-at-mainframe-hacking-and-penetration-testing-v22)
			* Sequel to above link
			* [Re: PenTest for Mainframe - Seclists](http://seclists.org/basics/2012/Aug/26)
		* [Reduce Risk and Improve Security on IBM Mainframes: Volume 1 Architecture and Platform Security](https://www.redbooks.ibm.com/redbooks/pdfs/sg247803.pdf)
	* **Talks/Videos/Slides**
		* [Hacking Mainframes; Vulnerabilities in applications exposed over TN3270 - Dominic White](http://www.irongeek.com/i.php?page=videos/derbycon4/t217-hacking-mainframes-vulnerabilities-in-applications-exposed-over-tn3270-dominic-white)
			* IBM System Z Mainframes are in regular use in Fortune 500 companies. Far from being legacy these systems are running an actively maintained operating system (z/OS). Applications on these often occupy roles critical to the business processes they underpin, with much of the later technology built around them, rather than replacing them. However, these systems are often bypassed by security testing due to worried of availability or assumptions about legacy. This talk will introduce you to assessing mainframe applications, which turn out to be quite similar to web applications. For this purpose we built a tool, Big Iron Recon & Pwnage (BIRP), to assist with performing such assessments. Importantly, our research uncovered a family of mainframe application vulnerabilities introduced by the TN3270 protocol. We found numerous applications, but not all, vulnerable to these flaws. Applications running within the two most popular transaction managers (CICS and IMS) as well as one of IBM’s own applications. The tool released assists with the exploitation of these flaws.
		* [Learning Mainframe Hacking: Where the hell did all my free time go? - Chad Rikansrud - Derbycon5](https://www.irongeek.com/i.php?page=videos/derbycon5/stable31-learning-mainframe-hacking-where-the-hell-did-all-my-free-time-go-chad-rikansrud)
		* [Security Necromancy : Further Adventures in Mainframe Hacking - Phillip Young/Chad Rikansrud - Defcon23](https://www.youtube.com/watch?v=LgmqiugpVyU&feature=youtu.be)
			* [Slides](https://www.slideshare.net/bigendiansmalls/security-necromancy-publish)
		* [Smashing the Mainframe for Fun and Prison Time - Phillip Young - Hacktivity2014](https://www.youtube.com/watch?v=SjtyifWTqmc)
		* [How to Embrace Hacker Culture For z/OS | Phil Young at SHARE in Seattle2015](https://www.youtube.com/watch?v=5Ra4Ehmifh4)
		* [Hacking Mainframes Vulnerabilities in applications exposed over TN3270 - Dominic White - Derbycon4](https://www.youtube.com/watch?v=3HFiv7NvWrM)
		* [Why You Should (But Don't) Care About Mainframe Security - Northsec2015 - Phillip Young](https://www.youtube.com/watch?v=YLxvrklh2tM)
		* [Hack the Legacy: IBM I aka AS400 Revealed - Bart Kulach - Defcon23](https://www.youtube.com/watch?v=JsqUZ3xGdLc)
		* [From root to SPECIAL - Pwning IBM Mainframes - Defcon22 - Philip Young](https://www.youtube.com/watch?v=MZDIblU9pBw)
		* [Mainframed: The Secrets Inside that Black Box [Shmoocon 2013] - Philip Young](https://www.youtube.com/watch?v=KIavTQeQqSw)
		* [Mainframed - The Forgotten Fortress - Philip Young - BSidesLV2012](https://www.youtube.com/watch?v=tjYlXW2Dldc)
		* [we hacked the gibson now what - Philip Young - BSidesLV2014](https://www.youtube.com/watch?v=n_sXG0Ff2oM)
		* [Mainframes - Mopeds and Mischief; A PenTesters Year in Review](http://www.irongeek.com/i.php?page=videos/derbycon4/t203-mainframes-mopeds-and-mischief-a-pentesters-year-in-review-tyler-wrightson)
	* **Tools**
		* [The Hercules System/370, ESA/390, and z/Architecture Emulator](http://www.hercules-390.org/)
			* Hercules is an open source software implementation of the mainframe System/370 and ESA/390 architectures, in addition to the new 64-bit z/Architecture
		* [Privilege escalation on z/OS](https://github.com/ayoul3/Privesc)
			* Privilege escalation tools on Mainframe
		* [Nmap Mainframe Scripts](https://github.com/zedsec390/NMAP)
			* NMAP scripts for TN3270 interaction as well as NJE. Most notably TSO User Enumeration and Brute Force. CICS transaction ID enumeration and NJE node name brute forcing.
		* [shells-payloads - Source code for SystemZ Shells / Payloads](https://github.com/zedsec390/shells-payloads)
		* [TN3270 Python Library](https://github.com/zedsec390/tn3270lib)
			* This library is a pure python implemnation of a TN3270e emulator. To test this library you can issue the command python tn3270lib.py <hostname> <port>.
		* [REXX-tools](https://github.com/zedsec390/REXX-tools)
			* Various tools in REXX
		* [NJElib](https://github.com/zedsec390/NJElib)
			* z/OS (mainframe) Network Job Entry (NJE) python library and example scripts.
		* [Privilege escalation on z/OSINT - ayoul3 github](https://github.com/ayoul3/Privesc)
			* Some scripts to quickly escalate on z/OS given certain misconfigurations.
		* [REX_Scripts](https://github.com/ayoul3/Rexx_scripts)
			* A collection of interesting REXX scripts to ease the life a mainframe pentester
* **SAP** <a name="sap"></a>
	* **101**
		* [mySapAdventures](https://github.com/shipcod3/mySapAdventures)
			* A quick methodology on testing/hacking SAP Applications for n00bz and bug bounty hunters
	* **Articles/Papers/Talks/Writeups**
		* [Perfect SAP Penetration testing. Part 3: The Scope of Vulnerability Search](https://erpscan.com/press-center/blog/perfect-sap-penetration-testing-part-3-scope-vulnerability-search/)
		* [SAP NetWeaver ABAP security configuration part 3: Default passwords for access to the application](https://erpscan.com/press-center/blog/sap-netweaver-abap-security-configuration-part-2-default-passwords-for-access-to-the-application/)
		* [List of ABAP-transaction codes related to SAP security](https://wiki.scn.sap.com/wiki/display/Security/List+of+ABAP-transaction+codes+related+to+SAP+security)
		* [Breaking SAP Portal](https://erpscan.com/wp-content/uploads/presentations/2012-HackerHalted-Breaking-SAP-Portal.pdf)
		* [Top 10 most interesting SAP vulnerabilities and attacks](https://erpscan.com/wp-content/uploads/presentations/2012-Kuwait-InfoSecurity-Top-10-most-interesting-vulnerabilities-and-attacks-in-SAP.pdf)
		* [SAP Penetration Testing Using Metasploit](http://information.rapid7.com/rs/rapid7/images/SAP%20Penetration%20Testing%20Using%20Metasploit%20Final.pdf)
		* [Assessing the security of SAP ecosystems with bizploit: Discovery](https://www.onapsis.com/blog/assessing-security-sap-ecosystems-bizploit-discovery)
	* **Exploits**
		* [SAP_exploit](https://github.com/vah13/SAP_exploit)
			* CVE-2016-2386 SQL injection; CVE-2016-2388 Information disclosure; CVE-2016-1910 Crypto issue
	* **Tools**
		* [PowerSAP](https://github.com/airbus-seclab/powersap)
			* PowerSAP is a simple powershell re-implementation of popular & effective techniques of all public tools such as Bizploit, Metasploit auxiliary modules, or python scripts available on the Internet. This re-implementation does not contain any new or undisclosed vulnerability.
		* [RFCpwn](https://github.com/icryo/RFCpwn)
			* An SAP enumeration and exploitation toolkit using SAP RFC calls
	* **Miscellaneous**
		* [pysap](https://github.com/CoreSecurity/pysap)
			* This Python library provides modules for crafting and sending packets using SAP's NI, Message Server, Router, RFC, SNC, Enqueue and Diag protocols.
* **SCADA/PLCs** <a name="scada"></a>
	* See [SCADA.md](./SCADA.md)
* **Virtual Appliances** <a name="va"></a>
	* **General**
		* [Hacking Virtual Appliances - Jeremy Brown - Derbycon2015](https://www.irongeek.com/i.php?page=videos/derbycon5/fix-me08-hacking-virtual-appliances-jeremy-brown)
			* Virtual Appliances have become very prevalent these days as virtualization is ubiquitous and hypervisors commonplace. More and more of the major vendors are providing literally virtual clones for many of their once physical-only products. Like IoT and the CAN bus, it's early in the game and vendors are late as usual. One thing that it catching these vendors off guard is the huge additional attack surface, ripe with vulnerabilities, added in the process. Also, many vendors see software appliances as an opportunity for the customer to easily evaluate the product before buying the physical one, making these editions more accessible and debuggable by utilizing features of the platform on which it runs. During this talk, I will provide real case studies for various vulnerabilities created by mistakes that many of the major players made when shipping their appliances. You'll learn how to find these bugs yourself and how the vendors went about fixing them, if at all. By the end of this talk, you should have a firm grasp of how one goes about getting remotes on these appliances.
		* [External Enumeration and Exploitation of Email and Web Security Solutions - Ben Williams](https://www.blackhat.com/docs/us-14/materials/us-14-Williams-I-Know-Your-Filtering-Policy-Better-Than-You-Do.pdf)
		* [Hacking Appliances: Ironic Exploitation Of Security Products - Ben Williams - BHEU 2013](https://www.youtube.com/watch?v=rrjSEkSwwOQ)
			* [Slides](https://www.blackhat.com/docs/webcast/07182013-Hacking-Appliances-Ironic-exploits-in-security-products.pdf)
* **Sort**
	* **Routers**
		* [ASUS Router infosvr UDP Broadcast root Command Execution](https://github.com/jduck/asus-cmd)
