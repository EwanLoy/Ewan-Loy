# Cyber Kill Chain

## Table of Contents

- [Task 1: Introduction](#task-1-introduction)
- [Task 2: Reconnaissance](#task-2-reconnaissance)
- [Task 3: Weaponization](#task-3-weaponization)
- [Task 4: Delivery](#task-4-delivery)
- [Task 5: Exploitation](#task-5-exploitation)
- [Task 6: Installation](#task-6-installation)
- [Task 7: Command & Control](#task-7-command--control)
- [Task 8: Actions on Objectives (Exfiltration)](#task-8-actions-on-objectives-exfiltration)
- [Task 9: Practice Analysis](#task-9-practice-analysis)
---

## Task 1: Introduction
  - The Cyber Kill Chain is a framework developed by Lockheed Martin in 2011 based on the military concept. The framework defines the steps an adversary must take in order to succeed
  - Understanding the Kill Chain helps you to recognise the intrusion attempts and understand the intruder's goals and objectives
**7 Phases of the Cyber Kill Chain**
    - Reconnaissance
    - Weaponization
    - Delivery
    - Exploitation
    - Installation
    - Command & Control
    - Actions on Objectives
**Learning Objectives:** Learn each phase of the Cyber Kill Chain Framework, the advantages and disadvantages of the traditional cyber kill chain

---

## Task 2: Reconnaissance
Reconnaisance is discovering and collecting information on the system and the victim. This is the planning phase for adversaries and often involves the use of OSINT (Open Source Intelligence) techniques

**What attackers do in this phase**
  - Collect information on an organisation or individuals from publicly available sources
  - Study employee names, email addresses, technologies in use, and infrastructure layout
  - Use tools to perform email harvesting, subdomain discovery, and metadata collection
**Common tools**
  - **theHarvester** for gathering emails, domains, IPs, and subdomains
  - **Hunter.io** for email lookup and domain level intelligence
  - **OSINT Framework** a collection of categorised tools for data discovery
  - **Social Media** such as LinkedIn and Facebook to gather information used in a phishing attack
 

---

## Task 3: Weaponization
In this stage, attackers create a weapon that combines malware, and exploit into a deliverable payload. Most attackers use automated tools or purchase malware from the Dark Web. More sophisticated APT groups create custom malware to avoid detection

**Terminology**
  - **Malware:** A program or software designed to damage, disrupt, or gain unauthorised access to a computer
  - **Exploit:** A program or code that takes advantage of the vulnerability or flaw in the application or system
  - **Payload** A malicious code that the attacker runs on the system

**In this Phase, the attacker would:**
  - Create an infected Microsoft Office document containing a malicious macro or VBA (Visual Basic for Applications) scripts
  - Create a malicious payload or a very sophisticated worm, implant it on the USB drives, and then distribute them in public
  - Choose Command and Control (C2) techniques for executing the commands on the victim's machine or deliver more payloads
  - Select a backdoor implant (the way to access the computer system, which includes bypassing the security mechanisms

---

## Task 4: Delivery
The delivery phase is where the adversary chooses a method for transmitting the payload or malware, choosing from:
  - **Phishing emails:** Used in broad and highly targeted attacks (Spear phishing). The attacker may impersonate a known contact or brand, embedding the payload in a document or link
  - **Malicious USB drops:** Attackers may leav infected USB drives in public areas or send them directly to the company, disguised as promotional gifts
  - **Watering Hole Attacks:** Attackers compromise a website frequently visited by the targeted audience, embedding malware that triggers a drive-by download when visited

---

## Task 5: Exploitation
- In the exploitation phase, the attacker executes their payload, taking advantage of a vulnerability to gain initial access to the victim's system
- After gaining access, the attacker could exploit software, system, or server-based vulnerabilities to escalate privileges or move laterally through the network
- The attacker couls also exploit a zero-day-exploit

**Examples of how an attacker carries out exploitation**
  - Victim triggers the exploit by opening the email attachment or clicking on a malicious link
  - Using a zero-day exploit
  - Exploit software, hardware, or even human vulnerabilities
  - Attacker triggers the exploit for server-based vulnerabilities

---

## Task 6: Installation
In the installation phase, the attacker deploys a persistent backdoor so they don't lose access to the system, persistence can be achieved through:  
- Installing a web shell on the server
- Installing a backdoor on the victim's machine
- Creating or modifying Windows Services
- Adding the entry to the "run keys" for the malicious payload in the Registry or Startup folder
In this phase, an attacker can also use timestomping to avoid detection and make the malware appear as a part of a legitimate program

---

## Task 7: Command & Control
In this phase, the attacker opens up the C2 (Command & Control) channel through the malware to remotely control and manipulate the victim
  - This term is also known as C&C or C2 Beaconing as a type of malicious communication between a C&C server and malware on the infected host
**Common C2 Channels**
  - **HTTP/HTTPS (Port 80 & 443):** Blends in with legitimate traffic
  - **DNS Tunneling:** Infected machine makes constant DNS requests to the DNS server that belongs to an attacker
  - **IRC (Internet Relay Chat):** Until recently, was the traditional C2 channel used by attackers but modern security solutions can easily detect malicious IRC traffic

---

## Task 8: Actions on Objectives (Exfiltration)
After going through six phases of the attack, the attacker reaches their end goal, which means taking action on the original objectives.

With hands-on keyboard access, the attacker can achieve the following:
  - Harvest user credentials
  - Privilege Escalation
  - Internal Reconnaissance
  - Lateral Movement
  - Collect and exfiltrate sensitive data
  - Delete the backups and shadow copies
  - Overwrite or corrupt data

---

## Task 9: Practice Analysis
This task involves applying what I had learned across Cyber Kill Chain to a real-world breach: the Target cyber attack of 2013 
**Scenario**
The infamous Target cyber-attack, which led to one of the largest data breaches in history took place on November 27, 2013.

On December 19th, 2013, Target released a statement confirming the breach, stating that approximately 40 million credit and debit card accounts were impacted between Nov. 27 and Dec. 15, 2013. Target had to pay the fine of $18.5 million under the terms of the multistate settlement agreement. This is considered to be the largest data-breach settlement in history.

**Task**
Map the phases of the attack to their corresponding stage in the Kill Chain

---



