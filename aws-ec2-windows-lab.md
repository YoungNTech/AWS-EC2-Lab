
# Watch me build the lab HERE
https://www.loom.com/share/fa2274b192cb4ae7a68be8e5f8fbae68

# AWS EC2 Windows VM Lab

## Overview
This lab demonstrates how to create and access a basic Windows virtual machine using Amazon EC2.

## Steps Performed

### 1. Create an EC2 Instance
- **Service:** Amazon EC2  
- **AMI:** Windows Server (default image)  
- **Instance Type:** t2.micro (Free Tier eligible)  
- **Key Pair:** Created or selected existing key pair for RDP access  
- **Network Settings:** Default VPC, Auto-assign public IP enabled  
- **Storage:** Default settings  
- **Security Group:** Allowed RDP (port 3389) inbound from my IP address  

### 2. Launch the Instance
- Clicked **Launch Instance** to deploy the VM.
- Waited for the instance state to show **Running** and verified status checks passed.
<img width="1873" height="792" alt="image" src="https://github.com/user-attachments/assets/fc8eab1c-5344-4d0e-afd6-b59b295b366a" />


### 3. Retrieve Windows Login Credentials
- Selected the instance → Clicked **Connect** → Chose **RDP Client**.
- Clicked **Get Password** and uploaded my private key file to **decrypt the administrator password**.
<img width="1780" height="822" alt="image" src="https://github.com/user-attachments/assets/97c57baf-270a-4b4f-962c-349050ad62e9" />


### 4. Connect via RDP
- Copied the decrypted **Administrator password**.
- Used **Remote Desktop Connection (RDP)** on my local machine.
- Entered the **Administrator credentials**.
- Successfully logged in to the Windows EC2 instance.
<img width="448" height="456" alt="image" src="https://github.com/user-attachments/assets/3e1fedfc-17ac-4d86-95eb-dbf78097e022" />


## Verification
- Verified network connectivity and desktop environment.
- Confirmed ability to interact with the instance via RDP.
<img width="1907" height="1059" alt="image" src="https://github.com/user-attachments/assets/b74d7221-2654-4e8c-bfa2-887eeb8ca97f" />


## Cleanup
- Stopped or terminated the EC2 instance to avoid incurring charges.

## Notes
- Always restrict RDP access to specific IPs for security.
- Store private keys securely; they cannot be recovered from AWS if lost.
