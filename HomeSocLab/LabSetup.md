# Setting up the lab

## Contents
- [Introduction](#Introduction)
- [Tools Used](#Tools-Used)
- [Topology](#Topology)
- [Setting up the VM's](Setting-up-the-VM's)
- [Installing Sysmon](#Installing-Sysmon)
- [Installing Splunk](Installing-Splunk)
---

## Introduction
This project documents the creation of a basic home SOC lab followuing a tutorial from [MyDFIR](https://www.youtube.com/watch?v=kku0fVfksrk&t=653s), the lab will then be used to simulate cyber attacks and monitor event logs.

## Tools Used
| Tool       | Description           |
|------------|-----------------------|
| VirtualBox  | This is the virtualisation software I will be using to host the virtual machines |
| Win10 VM  | This is the target VM, Sysmon and Splunk will be installed on this VM |
| Kali Linux VM  | This is the attack VM, it will be used to simulate attacks against the Win10 VM |
| Sysmon  | This will be used to log events |
| Splunk  | This will be used to analyse logs |

## Topology

## Setting Up the VM's

### Windows 10
The Windows 10 VM will be our target VM, after using Kali Linux to perfrom an attack, Sysmon will log the events which will then be forwarded to Splunk fo analysis. To install the Windows VM:

1. Download Windows 10 from the [Microsoft Website](https://www.microsoft.com/en-us/software-download/windows10)
2. Open the Windows 10 creation tool and create an ISO image
3. On VirtualBox, create a new machine named Win10 and use the ISO image created in step 2
4. On network settings choose NAT for adapter 1 and Internal network (SocNet) for adapter 2
5. Start the VM

### Kali Linux
Kalin Linux is an open source, Debian based cybersecurity tool used for digital forensics, penetration testing, and security auditing. We will be using it to perform attacks against out Windows VM, to install Kali:

1. Download the Kali Linux ISO image for VirtualBox from the [Kali Website](https://www.kali.org/get-kali/#kali-virtual-machines)
2. Use 7zip to extract the .vbox image file
3. Double click the ```.vbox``` file to automatically create the VM on VirtualBox
4. On network settings choose NAT for adapter 1 and Internal network (SocNet) for adapter 2
5. Start the VM

### Connecting the VM's
In order for the Virtual machines to be able to reach each other over the SocNet internal network we are going to assign static IP's to them:

On windows: Turn off Windows Defender Firewall and set the IPv4 address on adapter 2 to ```192.168.100.10```

![image](https://github.com/user-attachments/assets/4eee6d1d-144d-4a23-ae00-b6209829964f)

On Kali: Set the IP address on eth1 to ```192.168.100.20```

![image](https://github.com/user-attachments/assets/4ac8369d-c18b-415d-a858-507fbd876e09)

### Testing Connectivity
Ping Kali from Windows:

![image](https://github.com/user-attachments/assets/ff2d3dd3-ef1d-4c0e-b163-3454bd8bf11e)

## Installing Sysmon
System Monitor (Sysmon) is a Windows system service and driver that logs detailed system activity such as process creation, network connections, and file modifications. I will be using it to monitor events and generate logs for analysis in Splunk.

To install Sysmon:

- Download Sysmon from [Microsoft sysinternals](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon)
- Download a ```sysmonconfig.xml```, I used [this one](https://github.com/SwiftOnSecurity/sysmon-config) from SwiftOnSecurity
- Open PowerShell as an administrator and change directory to where the sysmon executable and config files are stored
- Run the following command to install sysmon as a service using the ```sysmonconfig.xml``` file:
```.\sysmon.exe -i sysmonconfig-export-xml```

## Installing Splunk
Splunk is a SIEM (Security Information and Events Management) platform that is used to collect, analyse, and respond to events. I will be using Splunk to analyse the sysmon logs collected from the Windows VM and build custom detection rules.

To install Splunk:

Download Splunk Enterprise from the [Splunk Website](https://www.splunk.com/en_us/download/splunk-enterprise.html)

![image](https://github.com/user-attachments/assets/21125227-ed5c-4700-950b-cc301efc4a21)
