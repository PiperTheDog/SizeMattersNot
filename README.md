# Size Matters Not: Automated Proxmox AD Lab

This proof of concept is designed to provide IT students with a Template they can follow to deploy a Multi Node Proxmox cluster. The only requirement is that at least ONE node have 24GB of ram as Ram is the biggest bottleneck in virtualization - CPU Doesn't matter as much as the template utilizes CPU Over Allocation, 

# $\color{red}{\text{CRITICAL:}}$ Review ALL scripts before running as it is dangerous to run scripts downloaded from the internet

The current proof-of-concept is demonstrated on three nodes:

Node 1: Lenovo Tiny (Intel Core i5-7400T) with 24GB RAM – Salvaged from recycling.

Node 2: Headless Laptop (AMD Ryzen 7 PRO 5850U) with 32GB RAM.

Node 3: Custom NAS (AMD Ryzen 5 4600G) with 16GB RAM – Used for maintaining quorum and hosting ISO files.

### Note: This build is highly accessible. It can be replicated using 2–3 Lenovo Tiny units (widely available on the used market due to Windows 10's end-of-life) and a Raspberry Pi to maintain quorum.

Lenovo Tiny PC's using 7th gen CPU's are readily avialable on the Used Market due to the recent discontinuation of windows 10 which has required many buisnesses to upgrade and replace fleets of machines. 

### Pre Requsets: 

1. 2(or 3)Proxmox nodes with necessary configs ie: ethernet, etc.

2. Memory: At Least one node must have 24GB of ram to handle the deployment of the DC, Utility server and the Workstation

3. A third device such as a raspberry pi to maintain quorum - You can install corosync-qnetd and configure it however this demo asumes that you have 3 nodes available
   
5. Download the modified Windows ISO files from the following site onto the dedicated nodes local storage:
   - These ISO files have been modified to skip the OOBE Expierence saving time allowing you to skip straight to the configuration of your domain.
   iso.spinks.ca

### How To create a proxmox cluster: 

1. From whichever proxmox node is going to be your inital node(it does not matter) click on data center:
<img width="959" height="701" alt="Screenshot 2026-04-08 at 3 58 10 PM" src="https://github.com/user-attachments/assets/f9fb13c6-f4e8-4037-b1c1-ca10c8750346" />

2. From the Datacenter page click on cluster:<img width="938" height="482" alt="Screenshot 2026-04-08 at 3 58 44 PM" src="https://github.com/user-attachments/assets/9f8de462-8495-4b24-ad6f-32fef02e37e1" />

3. From the cluster page click on Create cluster and follow the prompts: <img width="938" height="482" alt="Screenshot 2026-04-08 at 3 58 44 PM" src="https://github.com/user-attachments/assets/44411069-acdc-4667-82c2-2e059e6bebbc" />




   

### How to Run the Playbook

1. Download and Prepare: Download the ZIP file from the GitHub repository. Extract the contents and navigate to the folder using your terminal (I recommend the integrated terminal in VS Code).

2. Configure Environment Variables: Open the following files in your code editor and update the commented place holders with your own information

   a. Inventory.ini: Replace the placeholder hostnames/IPs with the addresses of your Proxmox nodes.

   b. playbook.yaml (Hosts): Update the hosts and node_name variables to match your cluster configuration.

   c. Credentials: Replace the placeholder passwords and usernames.

3. Once everything is updated to reflect your personal config simply run the following command:
   ansible-playbook -i Inventory.ini playbook.yaml

### To login to the VM's that the playbook created use the following login: 

Username: Owen 
Password: P@ssw0rd

### Any Issues just open a GitHub Request Request and i'll take a look
   
