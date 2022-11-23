# Introduction to the Cisco IOS CLI

# How to connect to a cisco device? (Console port)

The console port are the USB Mini-B and the RJ-45, we can connect to either of this ports but if we wanted to connect to the RJ-45 one we will need a cable that is RJ-45 from one side and Serial from the other side, the cable is named "Rollover cable", but laptops nowadays does not support serial so you will need on top of that an adapter from serial to USB, so the USB Mini-B is a solid choice nowadays.

![[Pasted image 20221013194610.png]]

## Terminal emulator (PuTTY)
PuTTY  is a terminal emulator, meaning it's a program that shows output from a console, being in this case the cisco console, if you wish to connect a cisco router physically, you will need to choose the "Serial" option inside putty, leaving configurations default because it's already done for cisco routers, being:

- Speed (baud): 9600 bits per second
- Data bits: 8
- Stop bits: 1
- Parity: None
- Flow control: None

# Cisco IOS CLI

## User EXEC mode
You will be prompted to enter the initial configuration dialog, that's your choice, after that you will get dropped off into a command prompt that will look like this

`Router>`

And that is the "User EXEC Mode", meaning the ">" execute and being "Router" the hostname.

- User EXEC mode is very limited
- Users can look at some things, but can't make any changes to the configuration.
- Also called "user mode"

## Privilaged EXEC Mode
`Router#`

- Provides complete access to view the device's configuration, restart the device, etc.
- Cannot change the configuration, but can change the time on the device, save the configuration file, etc.
- 