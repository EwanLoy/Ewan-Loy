# Pyramid ofPain

## Table of contents

## Table of Contents

- [Task 1: Introduction](#task-1-introduction)
- [Task 2: Hash Values (Trivial)](#task-2-hash-values-trivial)
- [Task 3: IP Address (Easy)](#task-3-ip-address-easy)
- [Task 4: Domain Names (Simple)](#task-4-domain-names-simple)
- [Task 5: Host Artifacts (Annoying)](#task-5-host-artifacts-annoying)
- [Task 6: Network Artifacts (Annoying)](#task-6-network-artifacts-annoying)
- [Task 7: Tools (Challenging)](#task-7-tools-challenging)
- [Task 8: TTPs (Tough)](#task-8-ttps-tough)
- [Task 9: Practical - The Pyramid of Pain](#task-9-practical---the-pyramid-of-pain)
- [Task 10: Conclusion](#task-10-conclusion)
- --

## Task 1: Introduction
The Pyramid Of Pain is a well-known concept used in cybersecurity solutions such as Cisco Security, SentinelOne, and SOCRadar to improve the effectiveness of Cyber Threat Intelligence, threat hunting, and incident response

---

## Task 2: Hash Values (Trivial)
A hash value is a numeric value of fixed length that uniquely identifies data, some of the most common hashing algorithms are:
  - **MD5** - Widely used cryptographic hash function with a 128-bit hash value. Not considered cryptographically secure
  - **SHA-1** - Takes an input and produces a 160-bit hash value string as a 40 digit hexadecimal number. Susceptible to brute force attacks
  - **SHA-2** - Has many variants, the most common is SHA-256 which returns a value of 256-bits as a 64 digit hexadecimal number

A hash is not considered cryptographically secure if two values have the same hash value or digest, security professionals use hash values to gain insight into specific files or artefacts using tools such as:
  - VirusTotal
  - MetaDefenderCloud - OPSWAT

Threat hunting using hash values as the IOC can be difficult since changing 1 bit of data in a file will change the hash. This results in many variations of and instances of known malware and ransomware

---

## Task 3: IP Address (Easy)
From a defense standpoint, knowledge of the IP addresses an adversary uses can be valuable. Acommon defense tactic is to block, drop, or deny inbound requests from IP addresses on your parameter or external firewall

An experienced adversary can get around this by using a new public IP address. One of the ways an adversary can make it difficult to carry out  IP blocking is by using **Fast Flux**:
  - FastFlux is a DNS technique used by botnets to hide phishing, web proxying, malware delivery, and malware communication activities behind compromised hosts acting as proxies.
  - The purpose is to hide the communication between malware and its command anc control centre from security professionals
 
---

## Task 4: Domain Names (Simple)
Domain names are harder for an attacker to change as they would need to purchase  the domain, register it, abd modify DNS records. Unfortunatley, many DNS providers have loose standards and provide APIs to make it easier for an attacker to change the domain

**Punycode**
  - An attack that can be used to redirect users to  to a malicious domain  seems legitimate
  - Punycode is a way of converting words that cannot bw written in ASCII, into a unicode ASCII encoding
  - ```adidas.de``` and ```adıdas.de``` look similar right?
  - The second URL actually has a punycode of ```http://xn--addas-o4a.de/```
  - Most web browsers a pretty good at translating the obfuscated characters into the full punycode domain name

**URL Shorteners**
  - A tool that creates a short, uniqie URL that will redirect to the website specified during the initial setup of the URL shortener link
  - Attackers use the following URL-shortening services to create malicious links:
    - bit.ly
    - goo.gl
    - ow.ly
    - s.id
    - smarturl.it
    - tiny.pl
    - tinyurl.com
    - x.co
  - You can see the actual website the the shortened link is redirecting you to by appending "+" to it

 **Viewing Connections in Any.run**
  Any.run is a sandboxing service which can be use review any requests, to do so we can look at the networking tab:
   - **HTTP Requests** - Shows the recorded HTTP requests since the detonation of the sample
   - **Connections** - Shows any communications made since the detonation of the sample
   - **DNS Requests** - Shows the DNS requests made since the detonation of the sample
   - 
---

## Task 5: Host Artifacts (Annoying)

---

## Task 6: Network Artifacts (Annoying)
Analysis of network indicators such as specific traffic patterns, ports, or beaconing behaviors.

---

## Task 7: Tools (Challenging)
Reflection on the use of attacker tools and how identifying them creates high defensive value.

---

## Task 8: TTPs (Tough)
Understanding attacker behaviors and techniques that are deeply ingrained and difficult to change.

---

## Task 9: Practical - The Pyramid of Pain
Details from the hands-on exercise applying the pyramid to classify and prioritize IOCs.

---

## Task 10: Conclusion
Final thoughts on the value of the Pyramid of Pain and how it guides defensive strategies.
