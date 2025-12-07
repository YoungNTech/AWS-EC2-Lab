

# AWS EC2 Windows VM Lab

## Overview
This lab demonstrates how to create and access a basic Windows virtual machine using Amazon EC2.

## Steps Performed

### 1. Create an EC2 Instance
- **Service:** AWS EC2  
- **AMI:** Windows Server  
- **Instance Type:** t2.micro  
- **Key Pair:** Created or selected existing key pair for RDP access  
- **Network Settings:** Default VPC, Auto-assign public IP enabled  
- **Storage:** Default settings  
- **Security Group:** Allowed RDP (port 3389) inbound from my IP address  

### 2. Launch the Instance
- Clicked **Launch Instance** to deploy the VM.
- Waited for the instance state to show **Running** and verified status checks passed.

<img width="1720" height="800" alt="Screenshot (2)" src="https://github.com/user-attachments/assets/2b45d0f6-ad6e-4941-9413-b3cd3e16aafc" />



### 3. Retrieve Windows Login Credentials
- Selected the instance → Clicked **Connect** → Chose **RDP Client**.
- Clicked **Get Password** and uploaded my private key file to **decrypt the administrator password**.

<img width="1720" height="800" alt="Screenshot (3)" src="https://github.com/user-attachments/assets/0090ad39-beaf-4688-b431-f8aab1cfad4b" />


### 4. Connect via RDP
- Copied the decrypted **Administrator password**.
- Used **Remote Desktop Connection (RDP)** on my local machine.
- Entered the **Administrator credentials**.
- Successfully logged in to the Windows EC2 instance.
<img width="448" height="450" alt="Screenshot 2025-12-04 233442" src="https://github.com/user-attachments/assets/252cfc60-84ef-41b8-9ef6-007b8712879b" />


## Verification
- Verified network connectivity and desktop environment.
- Confirmed ability to interact with the instance via RDP.

<img width="1800" height="880" alt="Screenshot 2025-12-04 234132" src="https://github.com/user-attachments/assets/6fb38685-81d6-42bc-9ea5-4d1322dcbe9b" />


## Cleanup
- Stopped or terminated the EC2 instance to avoid incurring charges.

## Notes
- Always restrict RDP access to specific IPs for security.
- Store private keys securely; they cannot be recovered from AWS if lost.
