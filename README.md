# Meow - Hack The Box
![maxresdefault](https://user-images.githubusercontent.com/104053455/190591761-4e6b7b47-c134-4966-8f4a-4e440fe87a8a.jpg)

## CONTENTS:
Connecting to Hack The Box machine

checking connection with the target

Nmap scanning

What is telnet?

login to the machine

Capture the flag.

## Connecting to Hack The Box machines:
First, we need to connect to the HTB machine using a VPN that is downloaded from HTB (Hack The Box).

*My VPN: 'starting_point_dracula2001 TCP.ovpn'*

if you are getting an error in connecting to VPN (like due to connected ipv6) you can disable ipv6 by using the following command:

sysctl net.ipv6.conf.all.disable_ipv6=0

# Checking the connection with the target:

After getting the IP let's try to ping to the machine to check whether the host is up or down.

command: ping 10.129.251.109
![ping](https://user-images.githubusercontent.com/104053455/190592799-76cb5def-ef6f-46eb-9c32-b81b3b1b40d1.png)

As you know Nmap scanning is used to scan the open ports and vulnerability.

Command: Nmap -A 10.129.251.109 {-A is used for an aggressive scan}
![Nmap -scan](https://user-images.githubusercontent.com/104053455/190593099-fd4d5fb9-df4e-417b-a98e-c1ee7b614c62.png)

Nmap scanningafter the scan we get to know about telnet, so let's try to exploit it. let's get into telnet.

# 4. What is a Telnet?
A network protocol that allows a user on one computer to log into another computer that is part of the same network.

*command: telnet 10.129.251.109*

Here we got stuck because we don't know the credentials. Here got a chance to do a brute-forcing attack. but first, let's try with some accounts that have self-explanatory names, such as 

>Administrator

>Admin

>Root

Let's attempt logging in with these credentials.
![loggin](https://user-images.githubusercontent.com/104053455/190593316-01d9fe10-7438-4f8e-bb80-eca89f3aa54c.png)
![loggin 2](https://user-images.githubusercontent.com/104053455/190593497-3788ca2c-212b-4f6c-8f34-057d7ea8bec1.png)


finally, we logged into the target system. Now let's check for the flag 
Now let's list the files in the system using the command

*Command: ls*

after the ls command, we can see the list of directories and files.
we got 2 files: flag.txt and snap

let's open the flag.txt

*command: cat flag.txt*
![flag](https://user-images.githubusercontent.com/104053455/190594294-a72c9d39-8278-4c25-8f7e-5e5b3c0295d9.png)

finally, we got the flag.
![telenet](https://user-images.githubusercontent.com/104053455/190594552-2b833bd0-4188-493c-bdba-1478a5199a1e.png)

# Meow has been Pwned!
