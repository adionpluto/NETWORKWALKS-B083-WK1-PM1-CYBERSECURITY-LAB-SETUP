---

## Project Overview

This project documents the creation of a **virtual cybersecurity and penetration-testing laboratory** using VirtualBox and Kali Linux.

The objective is to establish a repeatable and controlled workspace for practicing network reconnaissance, scanning, vulnerability analysis, security testing, and other cybersecurity techniques without affecting unrelated systems.

The environment uses a private virtual network, allowing additional virtual machines to be connected later as authorized targets for testing.

---

## Objectives

The project is designed to accomplish the following:

- Set up and configure VirtualBox.
- Import and prepare Kali Linux as a virtual machine.
- Build a private **NAT Network** for the laboratory.
- Establish network access for the Kali VM.
- Configure a predictable IP address for the Kali machine.
- Confirm connectivity and DNS functionality.
- Save a clean VM snapshot that can be used for recovery.
- Record the complete configuration and setup process.
- Establish a foundation for subsequent cybersecurity exercises.

---

## Purpose of the Lab

This laboratory serves as a separated environment for cybersecurity education and authorized security experimentation.

Possible activities within the environment include:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet inspection and analysis
- Web security testing
- Exploitation exercises
- Testing and learning security tools

**Important:** The environment and its tools should only be used against systems that you own or have explicit authorization to test. Unauthorized attacks or testing are not permitted.

---

## Lab Architecture

![](1-screenshot-title-image.png)

Additional target machines can be connected to the same virtual network as the laboratory is expanded for future projects.

---

## Lab Configuration

| Component | Configuration |
| ------------------ | ------------------ |
| Host OS | Windows 10 |
| Host RAM | 8 GB |
| Processor | Intel Core i7 |
| Hypervisor | VirtualBox 7.2 |
| Security OS | Kali Linux 2026.2 |
| Kali RAM | 2048 MB |
| Virtual Network | NAT Network |
| Network Address | 10.0.0.0/24 |
| Kali IP Address | 10.0.0.2/24 |
| Default Gateway | 10.0.0.1 |
| DNS Server | 8.8.8.8 |
| Future VM Range | 10.0.0.3–10.0.0.99 |

---

# Lab Setup Procedure

## Step 1. Install 7-Zip

7-Zip was installed so that the Kali Linux virtual-machine package could be extracted when provided in `.7z` format.

**Tool:** 7-Zip

---

## Step 2. Install VirtualBox

VirtualBox was installed and used as the hypervisor for the virtual cybersecurity environment.

---

## Step 3. Configure the NAT Network

A separate NAT Network was created within VirtualBox for the lab.

Configuration:

```text
Network Name: NatNetwork
IPv4 Prefix:  10.0.0.0/24
DHCP:         Enabled
IPv6:         Disabled
```

![](2-screenshot-network-settings-1.png)

A **NAT Network** was chosen because multiple virtual machines attached to the same network can communicate with each other while still receiving outbound network connectivity.

This setup also provides a suitable foundation for adding attacker and target virtual machines in later exercises.

---

## Step 4. Import Kali Linux

Kali Linux was obtained from the official Kali Linux website and then imported into VirtualBox.

The VM's network adapter was configured as follows:

```text
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```

The virtual machine was assigned:

```text
RAM: 2048 MB
```

![](3-screenshot-kali-linux.png)

A shared folder was configured as well, allowing files to be exchanged between the host operating system and the Kali virtual machine.

---

## Step 5. Configure the Kali Linux Network

The Kali Linux network settings were reviewed and configured with a consistent IPv4 address for easier identification within the lab.

Example configuration:

```text
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```

Using a predictable address makes it simpler to document the environment and refer to the Kali system during later exercises.

![](4-screenshot-kali-network-settings.png)

---

## Step 6. Save a Clean VM Snapshot

Once the initial configuration was complete, a VirtualBox snapshot was created to preserve the working state of the laboratory.

Example snapshot name:

```text
Clean Kali - Network Setup
```

This snapshot serves as the baseline state of the VM.

If a later experiment modifies or breaks the configuration, the virtual machine can be returned to this known-good state.

---

# Lab Verification

| Test | Command | Expected Result |
| ----------------------------- | ------------------------------- | ------------------------------- |
| Check IP configuration | `ip a` | Correct Kali IP is displayed |
| Check gateway access | `ping 10.0.0.1` | Successful replies |
| Check Internet access | `ping 8.8.8.8` | Successful replies |
| Check DNS resolution | `nslookup networkwalks.com` | Domain resolves successfully |
| Confirm Nmap installation | `nmap --version` | Nmap version is displayed |
| Confirm snapshot recovery | Restore snapshot and run `ip a` | Baseline network configuration is restored |

### Example Results

```text
IP Address:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8
```

---

# Problems Encountered and Solutions

Recording configuration issues and their resolutions is an important part of documenting the laboratory.

## Problem 1. Internet Access After Assigning a Static IP

After manually setting the IPv4 configuration, Internet access can stop working depending on how Kali Linux and NetworkManager handle the connection.

One workaround used during the setup was:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
```

The connection was subsequently restarted or the system was rebooted, followed by another connectivity test.

> **Important:** Connection and interface names can vary between systems. Always identify the actual connection name on the system before executing an `nmcli` command.

---

## Problem 2. VirtualBox VT-x / Hardware Virtualization Error

The VM initially could not start because hardware virtualization was disabled in the computer's firmware/BIOS configuration.

The problem was fixed using the following process:

1. Restart the computer.
2. Open the BIOS/UEFI configuration.
3. Enable Intel VT-x or the available hardware-virtualization option.
4. Save the BIOS/UEFI changes.
5. Restart the computer.
6. Launch the Kali VM again.

After virtualization support was enabled, the virtual machine started normally.

---

# What I Learned

This project provided practical experience in building a virtualized environment for cybersecurity training and testing.

The main concepts covered were:

### 1. NAT and NAT Network

A standard NAT setup and a NAT Network provide different networking capabilities.

A NAT Network permits multiple virtual machines connected to that network to communicate with one another while also using network address translation for external connectivity.

This makes NAT Network configuration well suited to multi-machine cybersecurity labs.

### 2. Virtual Machine Networking

I learned how VirtualBox network adapters connect virtual machines to different network configurations and how these settings influence communication between virtual systems.

### 3. Static IP Configuration

I gained experience configuring and checking IPv4 addresses, subnet masks, gateways, and DNS settings in Kali Linux.

### 4. VM Snapshots

A clean snapshot should be created **before carrying out risky or experimental activities**.

Having this baseline provides a reliable recovery point for future cybersecurity exercises.

### 5. Documentation

I learned that keeping a record of commands, network settings, screenshots, encountered issues, and their solutions is an important part of maintaining a professional cybersecurity project.

---

# Security and Ethical Use

This laboratory is intended solely for educational purposes and authorized security testing.

---

# Tools and Resources

- **7-Zip:** [https://7-zip.org/download.html](https://7-zip.org/download.html)
- **VirtualBox:** [https://virtualbox.org/wiki/Downloads](https://virtualbox.org/wiki/Downloads)
- **Kali Linux:** [https://kali.org/get-kali](https://kali.org/get-kali)

---

# Author

**Waqas Karim**\
Cybersecurity Professional B082

LinkedIn: [https://www.linkedin.com/in/waqaskarim/](https://www.linkedin.com/in/waqaskarim/)

---

## Project Information

**Program Name:** Cybersecurity at Networkwalks | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub
