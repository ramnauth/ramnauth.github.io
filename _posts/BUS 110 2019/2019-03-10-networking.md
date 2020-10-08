---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Networking

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   Handout: [PDF](https://drive.google.com/file/d/1Gv80gxzA5LpCnhEEL1Y2p5CDPgbIJIQh/view?usp=sharing); A brief introduction to computer networking and web development.

# (Optional) Link to an image that represents your blog post.
# The aspect ratio should be ~16:9.
image: /assets/img/default.jpg

# You can hide the description and/or image from the output
# (only visible to search engines) by setting:
# hide_description: true
# hide_image: true

# (Optional) Each post can have zero or more categories, and zero or more tags.
# The difference is that categories will be part of the URL, while tags will not.
# E.g. the URL of this post is <site.baseurl>/hydejack/2017/11/23/example-content/
categories: [BUS 110]
tags: []
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

A **computer network** is a collection of computing devices that are connected to communicate and share resources. Email, IM, and websites all rely on communication that occur 
across a **wireless** computer network. Wireless connections use radio waves or infra-red signals to send and receive data. Sometimes, we connect our phones 
(e.g., to transfer photos) or printers (e.g., to print our homework) to our computer using a **wired** connection. Computer networks contain devices other than computers. Any device on a network is called a **node**. 

One problem related to networks is the **data transfer rate** or **bandwidth**, aka the speed with which data moves from one place on a network to another. Large amounts of data can cause a lot of **traffic** on our network and cause the transfer rate to decrease.

## Types of Networks
There are many ways computer networks can be classified:
- A **local-area network** (LAN) connects a small number of machines that are geographically close to each other (e.g., in the same room or building). Various configurations, called **topologies**, have been used to administer LANs.
![Topologies](https://docs.google.com/uc?id=1jO39qLyc7VRE87gEXY4HC6UwkEcdN5w9)
- A **wide-area network** (WAN) connects two or more LANs over a relatively large geographic distance. Often one particular node on a LAN is setup as a **gateway** to handle all communication going between that LAN and other networks.
- Communication between networks is called **internetworking** (aka Internet), which is essentially an ultimate wide-area network, covering the entire globe.
- A **metropolitan-area network** (MAN) refers to a large network that covers an entire college campus or city. 

## Internet Connections
Who owns the Internet? Well, no one. No single person or company owns/controls the entire Internet
because, as a WAN, the Internet is made up of many smaller networks. These smaller networks are often owned/managed by a person or company. 

The **Internet backbone** is a set of high-capacity data routes. These routes that allow us to receive/send data across the Internet are 
provided by companies such as AT&T and Verizon. An **Internet service provider** (ISP) is a company that provides other companies/individuals access to the Internet. ISPs connect directly to the Internet backbone or bigger ISPs that have a connection to the backbone. 

How does our home computers connect to the Internet? There are 3 popular techniques for home connections:
1. **Phone modem**: converts computer data into an analog audio signal (looks like binary) for transfer over a telephone line, and then a modem (short for a modulator/demodulator) at the destination converts it back into human-understandable data again. 
2. **Digital subscriber line** (DSL) uses regular copper phone lines to transfer digital signals (which is much faster than analog signals) to and from the phone company's central office.
3. **Cable modem** is a device that transfers data using the cable TV hookup. In other words, data is transferred on the same line that your cable TV signals come in on.

Both DSL connections and cable modems fall into a category called **broadband** connections because depending on the location and whether access is by satellite, phone wire, video cable, or fiber optics, it is possible to obtain much faster data transfer speeds. 
However, for both DSL and cable modems, the speed for **downloads** (getting data from the Internet such as receiving web pages or videos to view) may not be the same as the speed for **uploads** (sending data to the Internet such as sending an email or submitting your homework via a form).

To improve the efficiency of transferring data, large chunks of data are divided into small, fixed-size, numbered packets. The packets are sent over the network individually to their destination, where they are collected and reassembled into the original message. This technique is called **packet switching**.

## Open Systems & Protocols

The International Organization for Standardization (ISO) established the **Open Systems Interconnection (OSI) Reference Model** to help with the development of network technologies:
![OSI Model](http://www.blackmoreops.com/wp-content/uploads/2016/05/OSI-Layer-Please-Do-Not-Tell-Secret-Passwords-Anytime-blackMORE-Ops-1.png)

### Network Protocols
A network **protocol** is an agreement between connected devices that a particular type of data will be formatted in a particular manner. Often, some protocols are based on other protocols, forming the **protocol stack** -- layers of protocols that build and rely on each other. In the OSI Model, you can see the protocol layers and how they relate.

### IP

An **Internet Protocol** deals with the routing of packets through the maze of interconnected networks 
to their final destination.  As shown in the OSI Model, IPs are at the *network* layer. Above it is the *transport* layer that is made up of 2 main protocols: 
1. **Transmissions Control Protocol** (TCP) breaks messages into packets, hands them off to the IP software for delivery (aka *transport*ation), and then reassembles the packets at their destination. TCP also handles any errors that occurs, such as if a packet never arrives at the destination.
2. **User Datagram Protocol** (UDP) is an alternative to TCP, but is faster and less reliable.
 
In what scenario would UDP be better than TCP? *Hint*: streaming videos? 

### High-Level Protocols

On top of the TCP/IP protocol suite, here are some high-level protocols (found on the OSI's *presentation* layer):
1. Simple Mail Transfer Protocol (**SMTP**) - used to specify the transfer for emails
2. File Transfer Protocol (**FTP**) - used to specify that transfer of files from one computer to another.
3. **Telnet** - used to log into a computer system from a remote computer as if you were seated in front of it (e.g., the [Chrome Remote Desktop](https://chrome.google.com/webstore/detail/chrome-remote-desktop/gbchcmhmhahfdphkhkmpfmihenigjmpp?hl=en))
4. Hypertext Transfer Protocol (**HTTP**) - defines the exchange of World Wide Web documents which are usually written using Hypertext Markup Language (**HTML**).

## Network Addresses
How does our computer make sure it's not leaking information to other devices on the network? When we want to communicate to a single connected device, how do we know we're talking with that specific device?

A **hostname** is a unique id that specifies a particle computer on the Internet. Hostnames are usually readable words separated by dots (e.g., `ramnauth.liu.edu`). As humans, we prefer to use hostnames when dealing with emails addresses and website because they are easy to remember. However, behind the scenes, 
a **Domain Name System** (DNS) has to translate a hostname into its corresponding **IP address**, which is easier for a computer to use/understand. An IP address is a series of four decimals numbers separated by dots (e.g., `193.133.20.4`).

In IPv4, IP addresses are stored into 32 bits:
```
10010100	01001110	11111010	00001100
148		  . 78		  . 250		  . 12
```

However, as Internet use increased (especially with the invention of smart phone, and other smart devices), the supply of unique 4-byte IP addresses were running out. By 2011, the last block of IPv4 addresses were assigned. As a result, IPv6 was created. It used 128 bits, organized in eight groups of 16. Thus, IPv6 addresses are usually written using hexadecimal digits to keep the length manageable. For example: `FE80:0000:0000:0000:0202:B3FF:FE1E:8329`. Not only does IPv6 provide more addresses, but also provides additional features that improve network traffic management and works alongside IPv4. 

## Domain Name Systems
A hostname consists of the computer name followed by the **domain name**. For example in the 
hostname `ramnauth.cs.liu.edu`, `ramnauth` is perhaps the name of a particular computers, and `cs.liu.edu` is the domain name. A domain name that has more than one section can give more information about the organization of which the computer is a part. For example, `ramnauth` is a computer in the Department of Computer Sciences at Long Island University. The very last section of the domain (e.g., `.edu`) is called its **top-level domain** (TLD) name.

The **DNS hierarchy**:
![DNS Hierarchy](https://www.cisco.com/c/dam/en_us/about/security/images/csc_child_pages/domain-name-space.gif)