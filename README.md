# Cyberlab-SIEM_Lab-
This repository documents a localized "Cyber Homelab" designed for practicing threat detection. The infrastructure features a SIEM deployed on an Ubuntu server that monitors a Windows Active Directory environment. A Kali Linux machine is utilized to execute simulated attacks and generate actionable alerts within the SIEM lab.

<h1>Setup DNS</h1>

I created my DNS with the domain name ad.cyberlab.com and it forwards its queries to cloudflares DNS. 

<img width="1470" height="956" alt="DNS Config" src="https://github.com/user-attachments/assets/952c6844-2170-442c-aba7-36989464aa8f" />

<h1>Configure ADDS</h1>

Assign a static Ip to the DC to ensure the Ip address stays constant, assigning the default gateway to my VM switch

<img width="1470" height="956" alt="IP Addresses" src="https://github.com/user-attachments/assets/ff81005a-c10c-4346-93cf-031dca4d3dae" >

I enabled Remote Desktop so I can remote into the server from my macbook. I also enabled ICMP requests and responses to confirm the system can communicate on my network.

I installed the roles Active Directory and DNS onto the server

<img width="1470" height="956" alt="Showing AD and DNS" src="https://github.com/user-attachments/assets/7473a12a-aa52-4f3f-bff3-b4ea14191d05" />


