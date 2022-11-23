# OSI Model & TCP/IP Suite

**What is a networking model?**

Networking models categorize and provide a structure for networking protocols and standards.

Being a protocol a set of rules defining how network devices and software should work.

# OSI 

- **Open System Interconnection model**
- A conceptual model that categorizes and standardizes the different functions in a network 
- Created by the "international organization for standardization" (ISO)
- Functions are divided into 7 layers 
- These layers work together to make networks work 

The OSI model:
1. Physical
2. Data link
3. Network
4. Transport
5. Session
6. Presentation
7. Application

How to remember it: **Please Do Not Throw Sausage Pizza Away**

## Layer 7
- The closest to the end user
- Interacts with software applications, for example web browsers
- HTTP and HTTPS are layer 7 protocols 
- Identifying communication partners
- Synchronizing communication

## Layer 6
- The presentation layer's work is to translate between application and network formats.
- For example encryption and decryption.

## Layer 5 
- Controls dialogs (sessions) between communicating hosts 
- Establishes, manages and terminates connections between the local application and the remote application.

## The upper layers
- Networking engineers don't usually work with the top 3 layers
- Application developers work with the top layers of the OSI model to connect their applications over networks

## Layer 4 
- Segments and reassembles data for communications between end hosts 
- Breaks large pieces of data into smaller segments which can be more easily sent over the network and are less likely to cause transmission problems if errors occur.
- Provide end-to-end communication.


## Layer 3 
- Provides connectivity between end hosts on different networks (Outside of LAN)
- Provide logical addressing (IP addressing)
- Provides path selection between source and destination 
- Routers operate at layer 3

## Layer 2 
- Provides node-to-node connectivity and data transfer
- Defines how data is formatted for transmission over a physical medium
- Detects and corrects physical layer errors
- Uses Layer 2 addressing (MAC addresses)
- Switches operate at this layer

## Layer 1 
- Defines physical characteristics of the medium used to transfer data between devices 
- For example voltage levels, maximum transmission distances, physical connectors, etc.
- Digital bits converted into electrical or radio signals
- Cables, pins, layouts, hardware operate at this layer

## Encapsulation (OSI upside down) 
1. Data 
2. Segments
3. Packet 
4. Frame

## Communication
From the application layer, we want to send some information to another computer, so the information goes through **encapsulation** which is packaging the data to be transported, then goes through the OSI stack upside down, by then making it to the layer 1 where is a communication between cables and when the capsule reaches the defined computer it goes through **de-encapsulation** and reaches the 7 layer of the OSI model.

# TCP/IP 
- Conceptual model and set of communications protocols used in the internet and other networks
- Known as TCP/IP because those are two of the foundational protocols in the suite
- Developed by the US DOD through DARPA
- Similar structure to the OSI but with fewer layers 
- This is the model in use in modern networks

## Model 
1. Link (OSI 1, 2)
2. Internet (OSI Network)
3. Transport 
4. Application (OSI 5,6,7)

## Resources

## Slides
![[Day 3 Slides - OSI Model & TCP-IP Suite.pdf]]

## Anki
![[Day 03 Flashcards - OSI Model, TCP_IP Suite.apkg]]

## Packet tracer labs
![[Day 03 Lab - OSI Model.pkt]]