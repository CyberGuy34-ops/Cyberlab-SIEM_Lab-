# Cyberlab-SIEM_Lab-
This repository documents a localized "Cyber Homelab" designed for practicing threat detection. The infrastructure features a SIEM deployed on an Ubuntu server that monitors a Windows Active Directory environment. A Kali Linux machine is utilized to execute simulated attacks and generate actionable alerts within the SIEM lab.

<h1>Setup of DNS</h1>

I created my DNS with the domain name ad.cyberlab.com and it forwards its queries to cloudflares DNS. 

<img width="1470" height="956" alt="DNS Config" src="https://github.com/user-attachments/assets/952c6844-2170-442c-aba7-36989464aa8f" />

<h1>Configure the ADDS</h1>

Assign a static Ip to the DC to ensure the Ip address stays constant, assigning the default gateway to my VM switch

<img width="1470" height="956" alt="IP Addresses" src="https://github.com/user-attachments/assets/ff81005a-c10c-4346-93cf-031dca4d3dae" >

I enabled Remote Desktop so I can remote into the server from my macbook. I also enabled ICMP requests and responses to confirm the system can communicate on my network.

I installed the roles Active Directory and DNS onto the server

<img width="1470" height="956" alt="Showing AD and DNS" src="https://github.com/user-attachments/assets/7473a12a-aa52-4f3f-bff3-b4ea14191d05" />

<h1>Troubleshooting why my ADDS wouldn't send the ubuntu server the logs</h1>

Figured out that my drive on the ubuntu server was maxed out due to Wazuh Vulnerability Detector. Ran the **sudo systemctl stop wazuh-manager** and **sudo pkill -f ossec** to stop the service while I escalated my privilege. Ran **sudo rm -rf /var/ossec/queue/vd_updater** to remove the directory and delete the temporary corrupt cache files that was filling my disk up which stopped me from receiving event logs.
Recreated the directory with **sudo mkdir -p /var/ossec/queue/vd_updater/tmp** , gave the permission back to ossec **sudo chown -R ossec:ossec /var/ossec/queue/vd_updater**

<img width="1470" height="956" alt="Screenshot 2026-09-30 at 3 52 33 PM" src="https://github.com/user-attachments/assets/af69cde6-1898-4f03-8203-aa72ac4fb66d" />




