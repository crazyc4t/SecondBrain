What's up guys! Back again with a new blogpost of a new Try Hack Me machine! This room is spec****ialized on privilage escalation, so this should be fun!

[The room](https://tryhackme.com/room/rrootme)

The challenge is to root the machine so let's get into it:

## Enumeration

You already know, nmap, gobuster at the same time always to save tons of time:

### Gobuster

```
gobuster -t 30 dir -u 10.10.132.53 -w common.txt
```

![[Pasted image 20221026100737.png]]

## Nmap
```
sudo nmap -sS -Pn -p- --open -T5 -oG allports 10.10.132.53
```

![[Pasted image 20221026105337.png]]

With this knowing that there are two ports open:
- SSH (22)
- HTTP (80)

# Exploiting

In /panel you can upload files to the server but no .php extension so we will change our .php to .php5 reverse shell.

![[Pasted image 20221026111050.png]]

![[Pasted image 20221026111605.png]]

![[Pasted image 20221026112146.png]]