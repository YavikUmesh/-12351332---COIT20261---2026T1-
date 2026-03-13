# Week 01 Portfolio – GNS3 Introduction

**Unit:** COIT20261 – Network Security  
**Student Name:** Yavik Umesh Dayaram  
**Student ID:** 12315332  
**Date:** 13 March 2026  

---

# 1. Aim of the Tutorial

The aim of this tutorial was to gain basic familiarity with the GNS3 network simulator.  
The tutorial focused on learning how to:

- Create a new GNS3 project
- Add and configure a Linux host
- Assign a static IP address
- Use annotations such as text and rectangles
- Start and stop nodes
- Access the Linux console through a web browser
- Run Linux commands to verify network configuration

This activity helps develop fundamental networking and simulation skills that will be used in later cybersecurity and networking exercises.

---

# 2. Software Setup

Before starting the tutorial, the required software tools were checked to ensure they were installed and working correctly.

The following software was used:

- **VirtualBox** – used for virtualization
- **GNS3** – used for network simulation
- **GitHub** – used to store and manage the portfolio

A private GitHub repository was created using the required naming format:

```
12315332-COIT20261-2026T1
```

This repository will contain weekly portfolio tasks and documentation for the unit.

---

# 3. Creating the GNS3 Project

A new project was created in GNS3 with the following name:

```
GNS3-Intro-12315332
```

Steps followed:

1. Opened the GNS3 application.
2. Selected **New Project**.
3. Entered the project name `GNS3-Intro-12315332`.
4. Opened the project workspace where the network topology would be built.

---

# 4. Adding a Linux Host Node

A **Linux Host** node was added to the workspace.

Steps performed:

1. Selected **Linux Host** from the device list.
2. Dragged the device into the workspace.
3. Named the device **Host1**.

This host represents a basic Linux machine that can be configured with networking settings.

---

# 5. Adding Annotations

Annotations were added to clearly document the network topology.

## Text Annotation

A text annotation was added containing the following information:

```
Week 1 Tutorial
Student ID: 12315332
Name: Vayik Umesh Dayaram
13 March 2026
```

## Rectangle Annotation

A rectangle shape was drawn around the text to make the information more organized and visible in the network diagram.

Another small text label was placed near the host node to indicate the IP address assigned to the device.

---

# 6. Configuring a Static IP Address

Before starting the Linux host, the network configuration file was edited to assign a static IP address.

The file used was:

```
/etc/network/interfaces
```

The following configuration was added for the `eth0` interface:

```bash
auto eth0
iface eth0 inet static
   address 10.10.0.2
   netmask 255.255.255.0
   up sysctl net.ipv4.ip_forward=0
```

### Explanation of the Configuration

- **auto eth0**  
  Ensures the interface automatically starts when the system boots.

- **iface eth0 inet static**  
  Specifies that the interface will use a static IPv4 address.

- **address 10.10.0.2**  
  Assigns the IP address to the host.

- **netmask 255.255.255.0**  
  Defines the subnet mask for the network.

- **up sysctl net.ipv4.ip_forward=0**  
  Disables IP forwarding so the host behaves as a standard computer rather than a router.

---

# 7. Starting the Node

After configuring the network interface:

1. The **Host1 node** was started.
2. A **web console** was opened from GNS3.
3. The Linux terminal became accessible through the browser.

---

# 8. Checking the IP Address

To confirm that the IP address was configured correctly, the following command was executed in the Linux console:

```bash
ip addr show
```

This command displays all network interfaces and their associated IP addresses.

The output showed the configured interface:

```
eth0
inet 10.10.0.2/24
```

This confirmed that the static IP address was successfully assigned to the host.

---

# 9. Network Topology Screenshot

The network topology consists of:

- One Linux host node
- Text annotation containing student information
- IP address label near the host
- A rectangle highlighting the annotation

Example:

```
Insert image here:
GNS-Intro-12315332-network.png
```

---

# 10. Console Output Screenshot

The console screenshot shows the result of the command used to display the network configuration.

```
ip addr show
```

Example:

```
Insert image here:
GNS-Intro-12315332-ipaddress.png
```

---

# 11. Files Generated

The following files were created as part of this tutorial:

- `GNS3-Intro-12315332.gns3project` – exported GNS3 project file  
- `GNS-Intro-12315332-network.png` – screenshot of the network topology  
- `GNS-Intro-12315332-ipaddress.png` – screenshot showing the IP configuration  

These files will be uploaded to the GitHub repository as part of the Week 01 portfolio.

---

# 12. What I Learned

From this tutorial, I learned several important concepts related to networking and network simulation.

## Understanding GNS3

GNS3 is a powerful network simulation tool that allows users to create virtual network environments. It is commonly used for learning networking concepts, testing configurations, and practicing network design.

## Static IP Configuration

I learned how to manually configure a static IP address in Linux using the `/etc/network/interfaces` file. This allows devices to have fixed network addresses instead of automatically receiving them from a DHCP server.

## Linux Networking Commands

The command:

```bash
ip addr show
```

is used to display the network interfaces and their IP addresses. This command is useful for verifying network configurations.

## Network Interfaces

Linux systems use interface names such as `eth0` to represent network connections. Configuring these interfaces allows the system to communicate with other devices on the network.

## Importance of Documentation

Using Markdown and GitHub helps organise and document networking tasks clearly. This improves collaboration and makes it easier to track learning progress.

---

# 13. Conclusion

This tutorial provided an introduction to using GNS3 and basic Linux network configuration. By creating a simple network with a Linux host and assigning a static IP address, I gained practical experience with network simulation and command-line tools.

These foundational skills will be useful for more advanced networking and cybersecurity labs throughout the unit.
