# NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP
# Cybersecurity Lab Setup — Kali Linux Virtualization with VirtualBox

## Project Overview

This project documents the creation of a **virtual cybersecurity and penetration-testing laboratory** with **Oracle VirtualBox** and **Kali Linux**.

The main goal is to establish a **controlled and isolated workspace** in which cybersecurity tools and techniques, including **network reconnaissance, scanning, vulnerability assessment, and security testing**, can be practiced safely and consistently.

A **private virtual network** is used for the laboratory, making it possible to introduce additional virtual machines later as targets for **authorized testing and experimentation**.

---

## Objectives

The project aims to:

* Configure **Kali Linux** as a virtual machine through Oracle VirtualBox.
* Establish an **isolated virtual environment** for cybersecurity activities.
* Learn the fundamentals of **virtual networking** within VirtualBox.
* Install and work with commonly used **cybersecurity and penetration-testing tools**.
* Develop a practical foundation in **ethical hacking, network security, and vulnerability assessment**.
* Prepare the laboratory for adding target machines during future security exercises.

---

## Purpose of the Project

The project was undertaken to:

* Build practical familiarity with **Kali Linux** and its security-focused tools.
* Understand the process involved in designing and configuring a **virtual cybersecurity laboratory**.
* Perform security-related experiments in a **safe, controlled, and authorized environment**.
* Practice **network reconnaissance and vulnerability-assessment concepts** without interacting with real-world systems.
* Strengthen practical skills relevant to **Cybersecurity, Ethical Hacking, and Penetration Testing**.
* Create a reusable setup that can support **future cybersecurity projects and experiments**.

---

## Technologies Used

* **Oracle VirtualBox**
* **Kali Linux**
* **7Zip/WinRAR** — Used for extracting files

---

## Lab Setup Procedure

The laboratory was established through the following stages:

* **Step 1: Install 7-Zip/WinRAR**
* **Step 2: Install [VirtualBox](https://www.virtualbox.org/)**
* **Step 3: Configure a NAT Network**
* **Step 4: Import [Kali Linux(2026.2}](https://www.kali.org/get-kali/#kali-installer-images)**
* **Step 5: Set up the Kali Linux Network**
* **Step 6: Create a VM Snapshot**

---

## Lab Setup Snapshots

Kali Linux:
![Kali Linux](https://github.com/adionpluto/NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/main/screenshot-kali-linux.png)

Network Settings:
![Network Settings](https://github.com/adionpluto/NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/main/screenshot-kali-network-settings.png)

NAT Setup:
![Nat](https://github.com/adionpluto/NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/main/screenshot-natnetwork.png)

Snapshot:
![VirtualBox Snapshot](https://github.com/adionpluto/NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/main/screenshot-snapshot.png)

Internet Connectivity Verification:
![Internet](https://github.com/adionpluto/NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/main/screenshot-internet-connectivity.png)

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

## Security & Ethical Use

This laboratory is intended exclusively for **educational activities and authorized security testing**.

Unauthorized access, scanning, exploitation, or testing of systems is prohibited.

---

## Tools & Resources

* **WinRAR:** [https://www.win-rar.com/download.html](https://www.win-rar.com/download.html?&L=0)
* **VirtualBox:** https://virtualbox.org/wiki/Downloads
* **Kali Linux:** https://kali.org/get-kali (2026.2)

---

# Author

*Aditya Choubey*  
**Computer Science Student**

[LinkedIn](https://www.linkedin.com/in/adityachby/) 

---

## Project Information

**Program Name:** Cybersecurity at Networkwalks | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub
