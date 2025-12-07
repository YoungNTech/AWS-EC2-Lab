# AWS EC2 Windows VM Lab

## Overview
This lab shows how to launch a basic Windows Server virtual machine (VM) on Amazon EC2 and connect to it via Remote Desktop (RDP). 

- Estimated time: 10–20 minutes
- Cost: Uses a t2.micro instance; stop or terminate the instance after the lab to avoid charges
- Goal: Launch a Windows Server instance, retrieve the Administrator password, and connect with RDP

## Prerequisites
- An AWS account with permissions to create EC2 instances, key pairs, and security groups
- A local machine with an RDP client (Remote Desktop Connection on Windows, Microsoft Remote Desktop on macOS)
- Your private key (.pem) file for the EC2 key pair (saved securely and accessible)

---

## Steps

### 1. Create an EC2 instance
1. Open the AWS Management Console → EC2 → Instances → Launch instances.
2. Configure the instance:
   - AMI: Select a Windows Server image (e.g., Windows Server 2019 or 2022)
   - Instance type: t2.micro (or another type as required)
   - Key pair: Create a new key pair or select an existing key pair. Download and keep the private key (.pem) safe.
   - Network: Use the Default VPC (or your preferred VPC). Enable Auto-assign Public IP if you need a public IP for RDP access.
   - Storage: Leave defaults or adjust as needed.
   - Security group: Create or select a security group that allows RDP (TCP 3389) inbound from your IP address only.

Notes:
- Restrict RDP access to your IP or your organization's IP range — do not allow 0.0.0.0/0 for RDP in production environments.

<img width="1720" height="800" alt="EC2 launch screenshot" src="https://github.com/user-attachments/assets/2b45d0f6-ad6e-4941-9413-b3cd3e16aafc" />

### 2. Launch and verify the instance
- Click "Launch instance".
- Wait until the instance state is "running" and the status checks show "2/2 checks passed".
- Note the instance's public IPv4 address or public DNS name for RDP.

### 3. Retrieve the Windows Administrator password
1. Select the instance in the EC2 console → Actions → Connect → RDP Client.
2. Click "Get Password".
3. Upload your private key (.pem) when prompted and click "Decrypt Password".
4. Copy the decrypted Administrator password.

<img width="1720" height="800" alt="Get password screenshot" src="https://github.com/user-attachments/assets/0090ad39-beaf-4688-b431-f8aab1cfad4b" />

### 4. Connect via RDP
1. Open your RDP client.
2. Enter the instance's public IP or DNS as the host.
3. When prompted, log in as "Administrator" and paste the decrypted password.
4. Accept any certificate warnings and complete the connection.

You should now see the Windows desktop for your EC2 instance.

<img width="448" height="450" alt="RDP session screenshot" src="https://github.com/user-attachments/assets/252cfc60-84ef-41b8-9ef6-007b8712879b" />
<img width="1800" height="880" alt="Windows desktop screenshot" src="https://github.com/user-attachments/assets/6fb38685-81d6-42bc-9ea5-4d1322dcbe9b" />

---

## Verification
- Confirm you can interact with the desktop and open applications.
- Verify network connectivity (e.g., open a browser and browse a test page).
- Check Windows Event Viewer if any errors occur during login.

---

## Cleanup
To avoid unexpected charges:
- Stop the instance if you want to preserve the VM and restart later (note: stopping and restarting can change the public IP unless you use an Elastic IP).
- Terminate the instance to delete it permanently and remove associated resources.
- Remove unused security groups and key pairs if they are no longer needed.

---

## Troubleshooting
- If RDP times out:
  - Ensure the instance is running and status checks passed.
  - Check the security group allows inbound TCP 3389 from your current public IP.
  - Verify the instance has a public IP (unless you are connecting through a VPN/ bastion host).
- If you cannot decrypt the password:
  - Make sure you are using the correct private key that pairs with the instance key pair.
  - Ensure the private key file permissions are correct and the key file is not corrupted.

---
