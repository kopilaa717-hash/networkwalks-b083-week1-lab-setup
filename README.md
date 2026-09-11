# Kali Linux Cybersecurity Lab Setup

## Lab Overview

This project documents the setup of a cybersecurity lab environment using Kali Linux and VirtualBox. The lab environment will be used for hands-on cybersecurity practice, including vulnerability assessment, penetration testing, incident response, digital forensics, and risk assessment.

## Objectives


Set up and configure a Kali Linux virtual machine using VirtualBox. Configure the virtual machine's hardware and network settings. Establish and verify network connectivity within the lab environment. When configuring NAT setup, change the name, configure IPv4 address, enable DHCP. Setup Linux on VirtualBox and configure and troubleshoot IP connectivity issues.

## Lab Environment 
- Host OS: windows 10 Home 
- hypervisor: VirtualBox
- Guest OS: Kali Linux 
- Network configuration: NAT

# Lab setup
# Step1 - Install 7-Zip
7-Zip is installed to download the kali linux archive  ([https://www.7-zip.org/](https://www.7-zip.org/))

# Step 2 - Install VirtualBox
Download VirtualBox on your laptop. VirtualBox is installed to make the virtual machines.
[https://www.virtualbox.org/](https://www.virtualbox.org/)
<img width="1920" height="1080" alt="Screenshot 2026-09-10 142139" src="https://github.com/user-attachments/assets/667316c7-b422-4187-9d90-bb2528ac1517" />

# Step 3 - configuring NAT Network
configure network settings on vitualbox(NAT Network: 10.0.0.0/24)
<img width="1920" height="1080" alt="Screenshot 2026-09-10 142846" src="https://github.com/user-attachments/assets/1e0223ae-57cc-440b-b714-324d7a875afc" />
<img width="1920" height="1080" alt="Screenshot 2026-09-10 143228" src="https://github.com/user-attachments/assets/db5595d6-68ed-4ac6-bbe4-e48e12ebf769" />

# Step 4 - Download kali linux
download the kali linux ([https://www.kali.org/get-kali/](https://www.kali.org/get-kali/))

#Step 5 - set up the Ip configuration of kali linux
kali Linux was configured to use NAT networking. After configuration the Ip settings were checked to verify network connectivity and troubleshoot connectivity issues.
<img width="767" height="586" alt="Capture" src="https://github.com/user-attachments/assets/4ea36496-909f-427b-b9be-fe5e328c783a" />

# Step 6- Connectivity issues
- check if the network settings are correct
- check if the NAT Network is created properly
- check that no other Vm on the same NAT Network is using 10.0.0.2
- "Run below commands and restart the kali linux"
- nmcli connection show
- sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
- sudo nmcli connection up "Wired connection 1"
- Restart your virtual machines

  # Challanges and Troubleshooting
 - During the lab setup, I encountered kali linux is not configuring  on virtual box then I open  C:\Users\Dell\.VirtualBox\VirtualBox.xml in Notepad and Check the <MachineRegistry> section and delete the <MachineEntry> line.
 - I encountered a network connecivity issue which I succesfully established the network connectivity by following the above commands.



