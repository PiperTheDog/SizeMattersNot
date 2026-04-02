This project is designed to provide students in the ICT program/Any IT related program an easy template for deploying a full ADDS lab on minimal/low powered hardware: 

The current proof-of-concept is demonstrated on three nodes:

Node 1: Lenovo Tiny (Intel Core i5-7400T) with 24GB RAM – Salvaged from recycling.

Node 2: Headless Laptop (AMD Ryzen 7 PRO 5850U) with 32GB RAM.

Node 3: Custom NAS (AMD Ryzen 5 4600G) with 16GB RAM – Used for maintaining quorum and hosting ISO files.

Note: This build is highly accessible. It can be replicated using 2–3 Lenovo Tiny units (widely available on the used market due to Windows 10's end-of-life) and a Raspberry Pi to maintain quorum.

This build is possible with 2 - 3 Lenovo Tiny's and a raspberry pi to maintain quorum, the Lenovo Tiny's are redally available on the used market as well as Ebay due to the recent discontinuation of windows 10

Pre Requsets: 

1. 2 Proxmox nodes with necessary configs ie: ethernet, etc.

2. A third device such as a raspberry pi to maintain quorum - You can install corosync-qnetd and configure it however this specific build relies on having 3 full proxmox nodes available

3. Download the modified Windows ISO files from the following site onto the dedicated nodes local storage:
   iso.spinks.ca


How to run the Playbook: 

1. Download the playbook as well as the inventory.ini file from this github and put them in the same location 
