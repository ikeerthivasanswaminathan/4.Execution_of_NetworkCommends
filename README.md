# 4.Execution_of_NetworkCommands

## AIM :Use of Network commands in Real Time environment

## Software : Command Prompt And Network Protocol Analyzer

## Procedure: To do this EXPERIMENT- follows these steps:

In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer. All commands related to Network configuration which includes how to switch to privilege mode and normal mode and how to configure router interface and how to save this configuration to flash memory or permanent memory.

This commands includes 
• Configuring the Router commands
• General Commands to configure network
• Privileged Mode commands of a router 
• Router Processes & Statistics
• IP Commands
• Other IP Commands e.g. show ip route etc.

## Program

Client Code 
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```

Server Code
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```

Tracert Code
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```

## Output

Client Output

![exp4client](https://github.com/ikeerthivasanswaminathan/4.Execution_of_NetworkCommends/assets/148937372/d96fc099-c1cb-49f4-8127-2975c1baed2c)

Server Output

![exp4server](https://github.com/ikeerthivasanswaminathan/4.Execution_of_NetworkCommends/assets/148937372/afb775b4-8036-4261-88ce-8856bef0e14e)

Tracert Output

![exp4tracert](https://github.com/ikeerthivasanswaminathan/4.Execution_of_NetworkCommends/assets/148937372/c911c748-93e1-41af-8b00-828e5656a1d9)

## Result
Thus Execution of Network commands are performed.
