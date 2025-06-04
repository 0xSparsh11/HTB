Task 1
What does the acronym VM stand for?
Virtual Machine

Task 2 
What tool do we use to interact with the operating system in order to issue commands via the command line, such as the one to start our VPN connection? It's also known as a console or shell.
Terminal

Task 3
What service do we use to form our VPN connection into HTB labs?
![image](https://github.com/user-attachments/assets/955c7c4d-0cea-4c10-aa89-919c40d4a474)
systemctl | grep vpn
- This is the systemd command-line utility.
- By default, running systemctl (with no arguments) lists all loaded units (services, sockets, etc.) — both active and inactive.
- The pipe (|) takes the output of systemctl and passes it as input to the next command.
- grep searches for the keyword vpn in the incoming lines- It filters and shows only lines that mention "vpn", case-sensitive by default.

Task 4
What tool do we use to test our connection to the target with an ICMP echo request?
ping

Task 5
What is the name of the most common tool for finding open ports on a target?
nmap
![image](https://github.com/user-attachments/assets/f445423d-3723-4b57-b766-369204d3753d)


Task 6
What service do we identify on port 23/tcp during our scans? 
- Telnet- A protocol used for remote login to another computer over a network.
- Telnet is often used to simulate weak systems. It allows attackers (or testers) to:
- Try logging in without encryption, Use default or blank credentials, Exploit misconfigurations.

![image](https://github.com/user-attachments/assets/4d8cde20-269e-4552-8833-2c7c45b7afe8)

Task 7 
What username is able to log into the target over telnet with a blank password?
root
- Sometimes, misconfigured Telnet servers allow login with:
- A known default username (like admin, root, guest)
- And a blank password ("" — literally nothing)

Submit root flag

Use tlenet to connect to the ip and enter root, admin or guest etc.. ) later do ls and cat 

![image](https://github.com/user-attachments/assets/2677d238-2adb-459e-a015-d43fb49d062f)

- The Flag: 
![image](https://github.com/user-attachments/assets/0a85f5cf-613b-4b23-bf22-5e3f586d13a6)

But in general 
- cat /etc/passwd
![image](https://github.com/user-attachments/assets/994bf9a4-beb8-40c4-8d89-73ff38772d68)
- Look for users with a valid shell (e.g., /bin/bash, not /usr/sbin/nologin)
- root has /bin/bash "root:x:0:0:root:/root:/bin/bash"
- sudo cat /etc/shadow or 
- sudo grep '^[^:]*::' /etc/shadow
- sudo passwd -S <username>

