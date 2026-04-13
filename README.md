### This project is designed to provide students in the ICT program/Any IT related program an easy template for deploying a full ADDS lab on minimal/low powered hardware: 

The current proof-of-concept is demonstrated on three nodes:

Node 1: Lenovo Tiny (Intel Core i5-7400T) with 24GB RAM – Salvaged from recycling.

Node 2: Headless Laptop (AMD Ryzen 7 PRO 5850U) with 32GB RAM.

Node 3: Custom NAS (AMD Ryzen 5 4600G) with 16GB RAM – Used for maintaining quorum and hosting ISO files.

Note: This build is highly accessible. It can be replicated using 2–3 Lenovo Tiny units (widely available on the used market due to Windows 10's end-of-life) and a Raspberry Pi to maintain quorum.

This build is possible with 2 - 3 Lenovo Tiny's and a raspberry pi to maintain quorum, the Lenovo Tiny's are redally available on the used market as well as Ebay due to the recent discontinuation of windows 10

Pre Requsets: 

1. 2(or 3)Proxmox nodes with necessary configs ie: ethernet, etc.

2. It is important that one node has a minimum of 24GB of ram - The CPU Specs are not important as long 

3. A third device such as a raspberry pi to maintain quorum - You can install corosync-qnetd and configure it however this specific build relies on having 3 full proxmox nodes available

4. Download the modified Windows ISO files from the following site onto the dedicated nodes local storage:
   iso.spinks.ca

How To create a proxmox cluster: 


1. From whichever proxmox node is going to be your inital node(it does not matter) click on data center:
<img width="959" height="701" alt="Screenshot 2026-04-08 at 3 58 10 PM" src="https://github.com/user-attachments/assets/f9fb13c6-f4e8-4037-b1c1-ca10c8750346" />

2. From the Datacenter page click on cluster:<img width="938" height="482" alt="Screenshot 2026-04-08 at 3 58 44 PM" src="https://github.com/user-attachments/assets/9f8de462-8495-4b24-ad6f-32fef02e37e1" />

3. From the cluster page click on Create cluster and follow the prompts: <img width="938" height="482" alt="Screenshot 2026-04-08 at 3 58 44 PM" src="https://github.com/user-attachments/assets/44411069-acdc-4667-82c2-2e059e6bebbc" />




   

How to Run the Playbook
Download and Prepare: Download the ZIP file from the GitHub repository. Extract the contents and navigate to the folder using your terminal (I recommend the integrated terminal in VS Code).

Configure Environment Variables:
Open the following files in your code editor and update the placeholders:

a. Inventory.ini: Replace the placeholder hostnames/IPs with the addresses of your Proxmox nodes.

b. playbook.yaml (Hosts): Update the hosts and node_name variables to match your cluster configuration.

c. Credentials: Replace the placeholder passwords and usernames.

3. Once everything is updated to reflect your personal config simply run the following command:
   ansible-playbook -i Inventory.ini playbook.yaml

### To login to the VM's that the playbook created use the following login: 

Username: Owen 
Password: P@ssw0rd
   
