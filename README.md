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

### 4. Change the status of Ethernet card on PC2 to down using ifconfig command:

   ![image](https://github.com/Ali-Elbana/networking_assignement/assets/97269796/6ce3043c-b759-4c99-a323-c3b11190e327)

### 5. Mointoring Packets using wireshark after making Ethernet card down:







