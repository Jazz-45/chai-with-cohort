# Understanding Network Devices

## Introduction

Ever wondered how we receive an instant message on our social media site from someone who is sitting at some other corner of the globe? Ever wondered how we see live telecast of the football match of our favourite team? This is the magic of Internet and web of Networks.

This blog will provide you a beginner's perspective on the interesting world on network devices.

## Basics of Network and Internet

Before diving deep into how networks work and what all devices actually make this happen , will have a look at the basics of network and Internet.

### Network

A network is basically a connection between computers and devices. In simple words networks are a combination of computers, wires and protocols (rules).

Depending upon connection area and entities network is divided in different categories such as :-

1. PAN ( Personal Area Network)
    
2. LAN (Local Area Network)
    
3. MAN (Metropolitan Area Network)
    
4. WAN (Wide Area Network)
    

Networks can be also categorized by how the devices are actually connected and how the data flow actually happens. These are called network topologies and they are pretty self-explanatory by their names.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769322549216/f7cbecf4-87e1-408c-a398-030ffb7fdbcb.png)

### Internet

Internet = Inter + Net Internet by definition means networks which are connected globally. In simple words , internet is a network of different network across the globe.

## How Internet Reaches our Home ?

Now since we have gained sufficient knowledge about networks and Internet , lets move our discussion to how actually Internet reaches our home.

At a very high-level the data is transferred through deep sea cables and distributed to the consumers by different ISPs (Internet Service Providers).

This flow includes many hardware devices in between such as router, modem, firewall, load balancer, switch etc. Each part has its specific function to perform.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769410001880/b8fa0d5d-d74f-4487-b65b-e092158d754d.png)

## Different Newtork Devices

### 1. Hub

Hub is a central connection point between many devices in a LAN network. It's job is to receive signal on a port and then broadcast it to all the ports , regardless of the destination. Analogy :- A conference call

### 2. Switch

Switch is a device which learns the MAC address of the connected devices and forwards the received signal to the destination port only.

Analogy :- A personal phone call

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769410288776/9002ff58-258b-43ad-810f-b61b84889c6d.png)

### 4. Modem

Modem (Modulator & Demodulator) converts the digital signal from our computers to analog signals for cable transmission through ISP . This conversion is known as modulation and de-modulation.

Analogy :- A Language Transalator

### 5. Router

Router is an intelligent device that connects different networks and routes the data to the destination using the best path. Routers maintain a routing table to keep track of the data routes. Routers use the IP address and sequence of the data packets and uses routing tables to forward it to the desired destination.

Analogy :- A GPS traffic controller

### 6. Firewall

Firewall is a device that acts as filter for incoming traffic (data over network). It uses some rules and policies to block the unauthorized access to the internal network. Firewall adds a layer of security because of the rules it enforces on the incoming and outgoing traffic.

Analogy :- A security Guard at an office

### 7. Load Balancer

Load Balancer is a network device which distributes the incoming traffic to multiple servers. This prevents server crashes when too much traffic overwhelms a single server. They are an integral part of scalable system as it increases the throughput and uptime of the backend systems.

Analogy :- A traffic police balancing traffic at a busy junction.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769411017195/c1d72919-6f0a-4613-bc30-5f408f09094c.png)

## How it relates to Backend Systems ?

The working of the above network devices resembles with the backend systems. The software version of the load balancers are a need for modern day scalable systems. Firewalls and Gateways are important for API security. This is the magic of network devices which is behind the requests that we make from our browsers.

## What Happens Before a Request Even Reaches the Server?

When you type a website name like [`google.com`](http://google.com) into your browser, your system does **not** understand that name directly. It only understands **IP addresses**.So before routers route traffic and servers respond, one important question must be answered:

> **Where is this website actually located on the Internet?**

This question is handled by **DNS (Domain Name System)**.

In the next blog, we’ll see how DNS translates domain names into IP addresses and why every network request begins with DNS.


