# networking_assignement

### Setup
![Screenshot 2023-09-27 at 8 12 49 AM](https://github.com/embeddedlinuxworkshop/networking_assignement/assets/139722851/b6c99d24-7411-4cc4-b7b6-633d865ed73e)




## Requirements

1. Get IP for each Board.
2. Check connectivity between them by sending ICMP packets by using *ping command*
3. Mointoring ICMP Packets using wireshark.
4. change the status of Ethernet card on PC2 to down using *ifconfig command*.
5. Mointoring Packets using wireshark.

--------------------------------------------------------
## Extra
1. Check if ping command Listen to any sockets using *ss command*.
2. strace ping command and check the main system calls send to Network stack.
--------------------------------------------------------
## My enviroment

I have two devices one of them is running on windows 10 and the other is ubuntu 22.04

--------------------------------------------------------
## Solution 

### 1. Get IP for each Board:

- **Windows 10** device IP: **192.168.1.9** (I used ipconfig command to get it)
- **Ubuntu** device IP: **192.168.1.14** (I used btop/ifconfig command to get it)

### 2. Check connectivity between them by sending ICMP packets by using ping command:

- I used **ping** command from the windows machine followed by the IP of the Ubuntu machine ( ip 192.168.1.14 )

   ![image](https://github.com/Ali-Elbana/networking_assignement/assets/97269796/4b436410-c519-44c6-a9e2-94eccf5c3193)

### 3. Mointoring ICMP Packets using wireshark:

   ![image](https://github.com/Ali-Elbana/networking_assignement/assets/97269796/0190436f-77de-4473-9e52-82bad258b7a4)

### 4. Change the status of networking interface on PC2 to down using ifconfig command:

   ![image](https://github.com/Ali-Elbana/networking_assignement/assets/97269796/b7fc6717-af12-40be-bd53-9c97556e7a3f)


### 5. Mointoring Packets using after making networking interface down:

   ![image](https://github.com/Ali-Elbana/networking_assignement/assets/97269796/3ae10642-d20e-4ae1-9073-fa2103136270)

### 6. Check if ping command Listen to any sockets using ss command:

   ![image](https://github.com/Ali-Elbana/networking_assignement/assets/97269796/8979b0df-d490-47ff-a5d3-848e1074ff89)

### 7. Strace ping command and check the main system calls send to Network stack:

   - Some of the main system calls that are related to the network stack are:
   
    socket: This system call creates a new socket of a specified type and protocol. For example, the ping command uses socket(AF_INET, SOCK_RAW, IPPROTO_ICMP) to create a raw IPv4 socket for ICMP protocol.
    bind: This system call assigns a local address to a socket. For example, the ping command uses bind(3, {sa_family=AF_INET, sin_port=htons(0), sin_addr=inet_addr("0.0.0.0")}, 16) to bind the socket 3 to any local IPv4 address and port.
    sendto: This system call sends a message to a specified destination address on a socket. For example, the ping command uses sendto(3, "\10\0\377\377\1\0\0\0\0\0\0\0\20\21\22\23\24\25\26\27"..., 64, 0, {sa_family=AF_INET, sin_port=htons(0), sin_addr=inet_addr("8.8.8.8")}, 16) to send an ICMP echo request packet of size 64 bytes to 8.8.8.8 on socket 3.
    recvfrom: This system call receives a message from a specified source address on a socket. For example, the ping command uses recvfrom(3, "E\0\0T\6\375@\0?\1\t\t\b\b\b\b\n\n\n\n\0\0\f5!\1\1"..., 192, 0, {sa_family=AF_INET, sin_port=htons(0), sin_addr=inet_addr("8.8.8.8")}, [16]) to receive an ICMP echo reply packet of size 84 bytes from 8.8.8.8 on socket 3.







