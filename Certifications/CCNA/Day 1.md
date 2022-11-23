# What is a network?
> "A computer network is a digital telecommunications network which allows nodes to share resources"

**But, what are nodes?**

Network nodes are devices that share resources, for example:

- Switches
- Routers
- Firewalls
- Servers
- Clients

# Building a network
To build a very simple network we just need to cable up two computers, and now they are nodes that can share resources.

## Clients
A client is a device that accesses a service made available by a server.

## Servers
A server is a device that provides resources to clients, meaning that a server is a role, not hardware.

## Switches 
Switches are made to forward traffic in a LAN (local area network), that's where you will connect your servers and your clients, to make them talk to each other, making that a LAN.

**Cisco Model Switches**
- Catalyst 9200
- Catalyst 3650

The Catalyst series from cisco is their enterprise level switch to connect various LANs.

**Switches have...**
- Many network interface/ports for end hosts to connect to (usually 24+)
- Provide Connectivity to hosts within the same LAN 
- Switches does not provide connectivity to others LANs and the internet (to do so you need a router)

## Routers
Routers are connected to the internet and the switch, making all of the interfaces in the switch have internet access, making the model of the network like so:

Clients > Switch > Router > Internet > Router > Switch > Server 

That's an example of a client/server conversation.

**Cisco Routers**
- ISR 1000
- ISR 900 
- ISR 4000

These are routers used in the enterprise space.

**Routers...**
- Have fewer network interfaces than switches 
- Are used to provide connectivity between LANs

## Firewalls
If there's an attacker connected to the internet (certainly are) with the purpose to steal data and damage our enterprise, then we will need a firewall to protect our self from the dangers of the internet, the firewall can be outside as it can be inside of our network, and it should be configured with security rules to permit/deny traffic.

**Cisco firewalls**
- ASA 5500-X (classic cisco firewall)
- Firepower 2100

These are enterprise firewalls.

**Firewalls...**
- Monitor and control network traffic based on configured rules.
- Can be placed inside the network or outside the network.
- Are known as "next generation firewalls" when they include more modern and advanced filtering capabilities like an IPS, for example the ASA 5500-X and the firepower 2100

**Network Firewalls**
Are hardware devices that filter traffic between networks.

**Host-based firewalls**
Are software applications that filter traffic entering and exiting the host machine like a PC.

## Resources

### Slides
![[Day 1 Slides - Network Devices 1.pdf]]

### Anki
![[Day 01 Flashcards - Network Devices.apkg]]

### Packet Tracer Lab
![[Day 01 Lab - Packet Tracer Introduction.pkt]]