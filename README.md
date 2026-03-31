# Configuring-Router-in-Cisco-Packet-Tracer


## Overview

I want to simulate a real-world scenario connecting 2 switches with a router. But the IP range for one switch is different from that of the second switch. In real companies, not every computer should be able to freely talk to every other computer. The accounting department shouldn't be on the same network as the warehouse floor.

At a retail store, for example, it typically runs three separate networks: one for the back office, one for the registers, and in some cases one for guest Wi-Fi. Keeping these networks isolated means that if a threat actor ever gets access to the guest Wi-Fi, they cannot see or intercept traffic from the registers or internal systems. This practice is called network segmentation and is a foundational security principle that should be used across retail, healthcare, and corporate environments.

# Steps Taken

1. I opened my previous Packet Lab and added a 1941 Router. Connected both switches to the router using a copper straight-through wire.

<img width="1254" height="722" alt="image" src="https://github.com/user-attachments/assets/90e758e4-6bd8-4c2f-9155-8a342f14d913" />


2. I then went to PC3 and changed the IPc4 Address to 172.16.1.10

<img width="856" height="338" alt="image" src="https://github.com/user-attachments/assets/bdac4e60-6de0-4dd5-afb2-195340ab1d54" />

Explain why

3. I then changed PC4 IPv4 Address to 172.16.1.11

<img width="1258" height="612" alt="image" src="https://github.com/user-attachments/assets/eb990ae1-6237-49f7-916b-f0ee81d6915e" />


4. I then clicked on our router. I clicked on the configure tab, then went to the Gigabit Ethernet0/0, turned on the port status. Port status indicates whether it communicates with the other ports connected to the router. 

I set the IPv4 Address to 192.168.1.1. This will be for Switch1. 

<img width="1406" height="756" alt="image" src="https://github.com/user-attachments/assets/2aefa7f4-49d4-4d98-8117-02aa91c7886c" />

5. I then clicked on GigabitEthernet0/1 and followed the same steps as before. 

I set the IPv4 Address to 172.16.1.1

<img width="1358" height="772" alt="image" src="https://github.com/user-attachments/assets/48c3c427-de0b-486c-bc9a-511baa02388e" />


6. I then need to set the Gateway for the computers. I would need to go to each computer and configure the Default gateway. 

A default gateway is the router's address that a computer would use when it sends data outside of its own network. The way I would think of he's like a ramp to the highway. If your computer doesn't know which ramp to use, it will just stay local, and it will never reach anything outside of its own neighborhood. Without setting the default gateway, PC-3 could talk to PC 4, which is on the same network and the same switch. But it cannot reach another computer on a different switch, even if it's already connected but not set to the specific gateway. The highway might be built, but there is no ramp to enter through.

For PC3, I went to the Desktop tab, then clicked on Default Gateway, and gave it 192.168.1.1

<img width="1494" height="770" alt="image" src="https://github.com/user-attachments/assets/5d1806e0-7a41-4ee7-b7e7-f502e6b03224" />

7. I followed the same steps for PC4 and PC5. Every device on the network needs to know the gateway. In a company setting, this is usually handled automatically through DHCP, but this is a static setting.

<img width="900" height="732" alt="image" src="https://github.com/user-attachments/assets/df4f1f53-6edd-4c3d-9057-958be43f1a32" />

<img width="816" height="378" alt="image" src="https://github.com/user-attachments/assets/663afea9-fa19-4a56-a690-99ac0e099a8a" />


8. I will now do the same thing for switch one's computers, which are PC0, PC1, and PC2, but input the IPV 4 address as 172.16.1.1.

<img width="1202" height="670" alt="image" src="https://github.com/user-attachments/assets/51d63974-eb5a-4329-bb14-73096056c6a4" />

<img width="832" height="492" alt="image" src="https://github.com/user-attachments/assets/8d69417e-1e86-418d-aa1a-9718e4f3c836" />


<img width="1404" height="686" alt="image" src="https://github.com/user-attachments/assets/451e7b2a-ba23-46e0-bf56-cfe5096585d1" />


9. Now WE TEST!!! I went to PC3, clicked on the desktop, then went to the command prompt and pinged 192.168.1.11

The ping command is the most fundamental network diagnostic tool. It sends a signal to the target IP and waits for the response. It's kind of like the digital equivalent of knocking on a door and waiting for someone to answer. Successfully pinging 192.168.1.11 from PC3, which lives on the 17.16.1.x network, confirms that both networks are correctly configured and the router also knows how to move traffic between them, and the default gateway is pointing in the right direction.


<img width="1174" height="602" alt="image" src="https://github.com/user-attachments/assets/63d08853-c654-4138-9bcc-46a6967e1a03" />

It took a little bit of time, but it worked. 


Let's simulate by looking at the enevlopes traveling in real time from PC1 to PC3. 

<img width="1176" height="626" alt="image" src="https://github.com/user-attachments/assets/7c2cba8d-a2ce-45a9-8568-a825922cc08d" />

It checked with the other computers connected to the switch to ask if it was 172.16.1.11, and also relayed that envelope to the router, which then will ask switch 2. 


<img width="1112" height="554" alt="image" src="https://github.com/user-attachments/assets/3d8161ec-6247-4b58-8f4f-22eb67059de9" />

## What I Learned
In 
this lab, I was able to test my ability to configure the Internet work routing, assign IP addresses across multiple subnets, and troubleshoot connectivity using industry-standard tools such as Cisco Packet Tracer
