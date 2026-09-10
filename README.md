# Hacking101-Bootcamp

DAY 1 -: 
ifconfig
curl ifconfig.me
TCP (protocol) - in more arranged way
UDP - for fatser work
HTTP - less secure as compare to HTTPS (not encrypted that much)
HTTPS - more secure (encrypted)
ip address - given to device (unique)
You can send email through terminal also
Packets - big data is broken into small pieces to travel across the network.
OSI model -: The 7 layers framework that helps network talk to each other.(open system interconnection)
OSI journey -: Encapsulation and Hop by hop routing
VPN helps to change ip address regularly
DNS -: mapping of domain name and ip address
Website -: what is my ip address

command to non-root user
praniti031@DESKTOP-0D8J05Q:~$ sudo usermod -aG wireshark $USER
praniti031@DESKTOP-0D8J05Q:~$ newgrp wireshark

DAY 2-:
OS internal books
Thread is small unit of a process sharing same memory
This process comes from process trees
A process is divided into threads
DLL - dynamic library link (kind of attack) /used as extension
DLL hijacking.
dynamic libraries let programs reuse functionalities.
*Privileges - permissions to execute anything.
sudo - : substitue userdo or superuserdo

Three modes - 1.user mode , 2.Kernel mode, 3.
Linux fundamentals -: 
linux kernel - core software that manages CPU, memory, devices and processes
linux history -: UNIX-> GNU -> Linux kernel -> Distributions
regular files, directories, 
grep to find specific number on file
xz video

Day - 3
Browser - client , web server - backend, Database - stores information
HTml , css, javascript
HTTP Methods - Get, post,put,patch,delete
Aunthentication, Authorization
rate limiting

Flag on postman - GET 
1.OWASP{g4l4ct1c_p1zz4_m4st3r_c0sm1c_fl4g}
2.OWASP{g4l4ct1c_p1zz4_m4st3r_c0sm1c_fl4g}
3.OWASP{g4l4ct1c_p1zz4_m4st3r_c0sm1c_fl4g}

DAY - 4

Cryptography (for secure communication)
Converts our messages in encrypt format so it is hard to understand for others(Encryption)
(Decryption) - reverse of encryption
Encoding Vs Encryption
Julius Caeser's Secret Weapon
Vigenere Cipher Example 
Caeser Cipher
Frequency analysis
Symmetric Vs Asymmetric Cryptography
Symmetric - ONE key is used only
Asymmetric - TWO key are used (private-server side ,public-client) 
Hashing -: 
AES - Advanced Encryption standard
RSA - 
OSINT - open source intelligence

Tools for stalkig or checking usernames
Sherlock , Whatsmyname , Namechk
OSNIT

Need to explore reverse and forensic domain in cybersecurity











# 🔐 Hacking 101 Bootcamp

> **Bootcamp:** Hacking 101
> **Progress:** Day 1 & Day 2 completed
> **Purpose:** Fundamentals of Networking, Operating Systems, Processes, Privileges, and Security

---

# 📅 DAY 1 — Networking Fundamentals

## 1. What is Networking?

Computer networking is the process of connecting devices so that they can communicate and exchange data.

When we access a website, send an email, or connect to a server, information is transferred between our device and another system through a network.

---

# 2. IP Address

An **IP (Internet Protocol) address** is an address assigned to a device/interface on a network.

It helps identify where network traffic should be sent.

### Example

```text
192.168.1.10
```

There are two major versions:

* **IPv4** → Example: `192.168.1.10`
* **IPv6** → Example: `2001:db8::1`

### Important

An IP address is **not necessarily a permanent unique identity of a person or device**. Addresses can be private, public, dynamic, shared, or changed over time.

---

# 3. Checking IP Address in Linux

### `ifconfig`

```bash
ifconfig
```

It displays information about network interfaces.

> On modern Linux systems, `ip addr` is generally preferred because `ifconfig` is considered an older utility.

```bash
ip addr
```

---

## 4. Finding Public IP Address

A service such as `ifconfig.me` can return the public IP address visible to the internet.

```bash
curl ifconfig.me
```

### Difference

```text
Private IP
    ↓
Used inside local network

Public IP
    ↓
Visible to external internet services
```

---

# 5. Network Packets

When we send data over a network, the data is usually divided into smaller units called **packets**.

For example:

```text
Large Data
     ↓
┌────┬────┬────┬────┐
│ P1 │ P2 │ P3 │ P4 │
└────┴────┴────┴────┘
     ↓
Network
     ↓
Destination
     ↓
Data reconstructed
```

Packets contain information required for delivering the data, along with protocol-specific headers.

---

# 6. TCP

**TCP = Transmission Control Protocol**

TCP is a connection-oriented transport protocol.

It provides mechanisms for:

* Reliable delivery
* Ordering of data
* Retransmission of lost data
* Flow control
* Congestion control

### Simple example

When downloading a file, TCP helps ensure that the data arrives reliably and in the correct order.

```text
Sender
   ↓
TCP connection
   ↓
Packets
   ↓
Receiver
```

---

# 7. UDP

**UDP = User Datagram Protocol**

UDP is a connectionless transport protocol.

It has less overhead than TCP and does not provide TCP-style guarantees of reliable, ordered delivery.

It is useful when **low latency and speed are more important than guaranteed delivery**.

### Common use cases

* DNS
* Online gaming
* Voice/video communication
* Streaming
* Real-time applications

### TCP vs UDP

| TCP                    | UDP                      |
| ---------------------- | ------------------------ |
| Connection-oriented    | Connectionless           |
| Reliable delivery      | No guarantee of delivery |
| Ordered data           | No guarantee of order    |
| More overhead          | Less overhead            |
| Useful for reliability | Useful for low latency   |

---

# 8. HTTP

**HTTP = Hypertext Transfer Protocol**

HTTP is used for communication between web clients and web servers.

Example:

```text
Browser
   ↓
HTTP Request
   ↓
Web Server
   ↓
HTTP Response
   ↓
Browser
```

HTTP itself does **not encrypt the traffic**.

Therefore, sensitive information sent over plain HTTP can potentially be observed by an attacker who can intercept the traffic.

---

# 9. HTTPS

**HTTPS = HTTP Secure**

HTTPS uses **TLS (Transport Layer Security)** to protect communication between the client and server.

It provides:

* Encryption
* Integrity protection
* Server authentication through certificates

### Simple comparison

```text
HTTP
Client ───────────────→ Server
       Data exposed to
       potential interception

HTTPS
Client ═══════════════→ Server
       Encrypted communication
```

> HTTPS is not simply "more encrypted." HTTP does not provide TLS encryption, while HTTPS uses HTTP over TLS.

---

# 10. DNS

**DNS = Domain Name System**

DNS converts human-readable domain names into IP addresses.

Instead of remembering:

```text
142.250.x.x
```

we can use:

```text
google.com
```

### Basic flow

```text
User enters:
google.com
     ↓
DNS lookup
     ↓
IP address
     ↓
Connect to server
```

DNS can be thought of as a **directory system for domain names and network addresses**.

---

# 11. Website — "What Is My IP?"

Websites such as "What Is My IP" display the public IP address that the website sees for your connection.

This is useful for understanding the difference between:

* Local/private IP
* Public IP

---

# 12. VPN

**VPN = Virtual Private Network**

A VPN creates an encrypted connection between your device and a VPN server.

A simplified flow:

```text
Without VPN

Your Device ─────────→ Website


With VPN

Your Device
     ↓
VPN Server
     ↓
Website
```

From the website's perspective, the connection generally appears to come from the VPN server's public IP rather than directly from your original public IP.

### Important

A VPN does **not automatically make you anonymous** or change your IP "regularly" by itself. The visible IP may change when you connect to different VPN servers or when the VPN provider changes the assigned address.

---

# 13. OSI Model

**OSI = Open Systems Interconnection**

The OSI model is a conceptual framework that divides network communication into **7 layers**.

### The 7 Layers

```text
7. Application
6. Presentation
5. Session
4. Transport
3. Network
2. Data Link
1. Physical
```

### Easy way to remember

**A P S T N D P**

> **All People Seem To Need Data Processing**

---

## Layer 7 — Application

Provides network services to applications.

Examples:

* HTTP
* DNS
* SMTP

---

## Layer 6 — Presentation

Responsible for how data is represented.

Examples include:

* Data formatting
* Encoding
* Encryption/decryption concepts

---

## Layer 5 — Session

Manages communication sessions between applications.

---

## Layer 4 — Transport

Provides end-to-end transport services.

Examples:

* TCP
* UDP

---

## Layer 3 — Network

Responsible for logical addressing and routing.

Example:

* IP

Routers primarily operate at this layer.

---

## Layer 2 — Data Link

Responsible for communication over a local network/link.

Examples:

* Ethernet
* Wi-Fi link-layer mechanisms

MAC addresses are associated with this layer.

---

## Layer 1 — Physical

Deals with the physical transmission of bits.

Examples:

* Cables
* Radio signals
* Electrical/optical signals
* Network hardware

---

# 14. OSI Journey

When data is sent, it moves down through the protocol stack on the sender's side.

This process is called **encapsulation**.

```text
Application
     ↓
Presentation
     ↓
Session
     ↓
Transport
     ↓
Network
     ↓
Data Link
     ↓
Physical
     ↓
      NETWORK
     ↓
Physical
     ↓
Data Link
     ↓
Network
     ↓
Transport
     ↓
Session
     ↓
Presentation
     ↓
Application
```

At each relevant layer, protocol information such as headers may be added.

At the receiving side, the process is reversed. This is called **decapsulation**.

---

# 15. Hop-by-Hop Routing

When a packet travels across the internet, it usually does not go directly from the source to the destination.

Instead, it can pass through multiple network devices.

```text
Your Computer
     ↓
Router
     ↓
ISP
     ↓
Router
     ↓
Router
     ↓
Destination Server
```

Each routing step is called a **hop**.

Routers examine network-layer information and determine where to forward packets next.

---

# 16. Sending Email Through Terminal

Email can also be sent from a terminal using command-line tools or mail utilities.

At a high level:

```text
Terminal
   ↓
Mail client / SMTP
   ↓
Mail server
   ↓
Recipient's mail server
   ↓
Recipient
```

**SMTP (Simple Mail Transfer Protocol)** is commonly used for sending and relaying email.

---

# 17. Wireshark User Permissions

Wireshark can capture network traffic, which may require access to network interfaces.

Instead of always running Wireshark as root, Linux can provide the required permissions through a dedicated group.

Example:

```bash
sudo usermod -aG wireshark $USER
```

Then:

```bash
newgrp wireshark
```

### What does this mean?

```text
sudo
↓
Execute command with elevated privileges

usermod
↓
Modify a user account

-aG
↓
Append user to a supplementary group

wireshark
↓
Target group

$USER
↓
Current username
```

### Security principle

It is generally better to grant the **minimum permissions required** rather than running an entire application with root privileges.

---

# 📅 DAY 2 — Operating System Fundamentals

## 1. Operating System

An **Operating System (OS)** is system software that manages computer hardware and provides services to applications.

Examples:

* Linux
* Windows
* macOS
* Android

The OS manages resources such as:

* CPU
* Memory
* Storage
* Network
* Devices
* Processes

---

# 2. Process

A **process** is a running instance of a program.

For example:

```text
Program
   ↓
Execution
   ↓
Process
```

A process has its own resources and address space.

Examples:

```text
Browser
   ↓
Running browser process

Terminal
   ↓
Running terminal process
```

---

# 3. Process Tree

Processes can create other processes.

This creates a parent-child relationship.

```text
init/systemd
      │
      ├── Process A
      │      ├── Child Process
      │      └── Child Process
      │
      └── Process B
             └── Child Process
```

This structure is called a **process tree**.

On Linux, commands such as:

```bash
pstree
```

can be used to view process relationships.

---

# 4. Thread

A **thread** is a unit of execution within a process.

Multiple threads can exist inside the same process and can share many resources, including the process's address space.

```text
Process
│
├── Thread 1
├── Thread 2
└── Thread 3
```

### Process vs Thread

| Process                                    | Thread                                        |
| ------------------------------------------ | --------------------------------------------- |
| Independent execution environment          | Execution unit inside a process               |
| Has its own address space                  | Threads of a process share its address space  |
| More resource-heavy                        | Generally lighter                             |
| Processes communicate using IPC mechanisms | Threads can communicate through shared memory |

---

# 5. User Mode and Kernel Mode

Modern operating systems separate execution into different privilege levels.

Two important concepts are:

### User Mode

Applications normally run in user mode.

Examples:

* Browser
* Text editor
* Terminal
* Normal user programs

User-mode applications have restricted access to system resources.

### Kernel Mode

The operating system kernel runs with much greater privileges.

It can access:

* Hardware
* Memory management facilities
* Devices
* Core operating-system functionality

### Basic idea

```text
User Applications
       ↓
   System Calls
       ↓
      Kernel
       ↓
     Hardware
```

This separation helps prevent ordinary applications from directly accessing critical system resources.

> There are other privilege levels and execution contexts depending on the operating system and architecture, so "three modes" is not a universal OS rule.

---

# 6. Privileges

**Privileges** determine what actions a user, process, or program is allowed to perform.

Examples:

* Read a file
* Write to a file
* Execute a program
* Access a device
* Modify system configuration

### Principle of Least Privilege

A very important cybersecurity principle is:

> Give a user or program only the permissions it actually needs.

This reduces the potential damage if an account or application is compromised.

---

# 7. `sudo`

`sudo` is commonly expanded as **"superuser do"**, although its broader purpose is to allow an authorized user to run commands with another user's privileges, commonly root.

Example:

```bash
sudo apt update
```

Here, the command is executed with elevated privileges if the user is authorized.

### Why is `sudo` important?

It allows administrative operations without requiring users to remain logged in as the root user.

---

# 8. Dynamic Libraries

A **dynamic library** contains reusable code that programs can load at runtime.

Examples:

```text
Program
   ↓
Dynamic Library
   ↓
Reusable functionality
```

On Windows, dynamic libraries commonly use the:

```text
.dll
```

extension.

On Linux, commonly:

```text
.so
```

files are used for shared libraries.

### Why use libraries?

Instead of every application containing its own copy of common functionality, programs can reuse shared code.

Benefits include:

* Code reuse
* Smaller executables
* Easier updates
* Shared functionality between applications

---

# 9. DLL Hijacking

**DLL hijacking** is a security issue in which an application loads an unintended malicious or unauthorized DLL instead of the legitimate library it expects.

A simplified example:

```text
Application
     ↓
Looks for required DLL
     ↓
Unexpected DLL is found first
     ↓
Application loads it
     ↓
Unintended code execution
```

The exact conditions depend on how the application searches for and loads libraries.

### Security lesson

Applications should use secure library-loading practices and avoid ambiguous search paths.

---

# 10. Malicious Document Attack Chain

A malicious document can sometimes be used as the initial entry point for an attack.

A simplified attack chain discussed in the bootcamp was:

```text
Malicious Document
       ↓
Legitimate Application
       ↓
Unexpected Child Process
       ↓
Code Execution
       ↓
Further Attack Activity
```

For example, an attacker might attempt to abuse a document-processing application to cause an unexpected process to execute.

### Important security concepts

When investigating such activity, security analysts may look at:

* Parent process
* Child process
* Command line
* File location
* User context
* Network connections
* Process creation time

This is why **process trees are important in cybersecurity**.

---

# 11. Sockets

A **socket** is a communication endpoint used by applications to communicate over a network.

A socket is commonly associated with information such as:

```text
IP Address + Port + Protocol
```

For example:

```text
192.168.1.10 : 8080
```

A server can listen on a port, while a client can connect to it.

### Simplified communication

```text
Client
  │
  │ Socket connection
  ↓
Server
```

Sockets are fundamental to many network applications.

---

# 🧠 DAY 1–2 Key Takeaways

## Networking

```text
IP
↓
Identifies network interfaces/addresses

DNS
↓
Maps domain names to network addresses

TCP
↓
Reliable, ordered transport

UDP
↓
Low-overhead transport without TCP's delivery guarantees

HTTP
↓
Web communication without TLS

HTTPS
↓
HTTP protected by TLS

Packets
↓
Units of network data
```

## OS

```text
Program
   ↓
Process
   ↓
Threads

Process
   ↓
Parent/Child relationships
   ↓
Process Tree
```

## Security

```text
Privileges
↓
What a user/process is allowed to do

sudo
↓
Run authorized commands with elevated privileges

Dynamic Libraries
↓
Reusable code loaded by programs

DLL Hijacking
↓
Application loads an unintended library

Malicious Document
↓
Application
↓
Unexpected Child Process
↓
Possible Code Execution
```

---

# 🔑 Important Commands Learned

```bash
ifconfig
```

Display network interface information.

```bash
ip addr
```

Modern Linux command for displaying network addresses/interfaces.

```bash
curl ifconfig.me
```

Query a service to display the public IP visible to that service.

```bash
sudo usermod -aG wireshark $USER
```

Add the current user to the `wireshark` supplementary group.

```bash
newgrp wireshark
```

Start a shell with the updated group membership.

```bash
pstree
```

Display processes in a tree structure.

---

# 🎯 Concepts to Revise Before Day 3

* [ ] IPv4 vs IPv6
* [ ] Private vs Public IP
* [ ] TCP vs UDP
* [ ] HTTP vs HTTPS
* [ ] DNS
* [ ] Packets
* [ ] OSI 7 layers
* [ ] Encapsulation and decapsulation
* [ ] Routing and hops
* [ ] Process
* [ ] Process tree
* [ ] Thread
* [ ] User mode vs kernel mode
* [ ] Privileges
* [ ] `sudo`
* [ ] Dynamic libraries
* [ ] DLL hijacking
* [ ] Sockets
* [ ] Parent process vs child process

---

## 🛡️ Cybersecurity Mindset

The most important lesson from these first two days is that cybersecurity is not just about learning "hacking commands."

It is about understanding:

**How computers communicate → How operating systems work → How programs execute → How privileges are managed → How attacks abuse these mechanisms → How defenders detect and prevent them.**

That foundation will make later topics such as **Wireshark, Linux security, privilege escalation, web security, malware analysis, and penetration testing** much easier to understand.

