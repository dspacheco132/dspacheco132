### Diogo Pacheco
[![GitHub followers](https://img.shields.io/github/followers/dspacheco132.svg?style=social&label=Follow&maxAge=2592000)](https://github.com/dspacheco132?tab=followers)

# AWS Network Architecture (PDL-VPC)

![AWSPROJECT](https://github.com/user-attachments/assets/94cddc6e-107a-4ee0-a96e-58d045d52695)


## General Description

This project describes a network architecture configured on Amazon Web Services (AWS), implemented in a **VPC (Virtual Private Cloud)** with the address range **10.0.0.0/20**, within the **us-east-1** AWS region. The setup also includes a **public subnet** hosting instances such as a Windows Server (WIN SRV) and several Windows Clients (WIN CLI).

## Architecture Components

### 1. **AWS Cloud**
   - The entire environment runs on **AWS Cloud**, specifically in the **us-east-1** region.

### 2. **PDL-VPC (10.0.0.0/20)**
   - The **VPC** is the isolated AWS environment where all project resources are available.

### 3. **Public Subnet**
   - All remote access within this subnet is directly accessible from the internet via an **Internet Gateway**.
   - The main components within this subnet are:
     - **WIN SRV**: Windows Server configured for services such as (IIS) and FTP (FileZilla).
     - **WIN CLI**: Windows Client machines connected to the **Active Directory** (AD) in the **enta.pt** domain.

### 4. **WIN SRV (Windows Server)**
   - This server is mainly responsible for essential services such as:
     - **IIS**: Web server, with HTTP/HTTPS.
     - **FileZilla**: FTP server sharing files with connected users (Maria, Terceira, Corvo), providing the site directory.
     - Domains available on the server: **oriental.pt**, **central.pt**, **occidental.pt**.
     - Public server IP: **3.81.242.104**.

### 5. **WIN CLI 1, 2, 3 (Windows Clients)**
   - These machines are clients connected to the server's **Active Directory**. Each has a public IP:
     - **WIN CLI 1**: 54.162.230.48
     - **WIN CLI 2**: 107.20.194.40
     - **WIN CLI 3**: 3.209.233.185
   - They are configured to authenticate and communicate with the **DC | AD server** within the **enta.pt** domain.
### 6. **Active Directory (DC | AD)**
   - The **DC (Domain Controller)** handles authentication and access for **WIN CLI** clients, enabling centralized user and permission management.

### 7. **Security Group**
   - Controls network traffic, acting as a firewall at the instance level, allowing or denying access based on configured rules.

### 8. **NACL (Network Access Control List)**
   - Implemented at the subnet level, controls inbound and outbound traffic for the public subnet.

### 9. **Internet Gateway**
   - The **Internet Gateway** (IGW) allows internet traffic to access resources within the **public subnet**. It also enables instances in the public subnet to send and receive internet traffic.

### 10. **External Domain (ciberdsp.hopto.org)**
   - The diagram shows a connection to an external domain via **no-ip**, which allows the acquisition of one hostname, directed to the server's public IP.

## Contacts

Feel free to contact me by email:

- Email: diogosilvapacheco@enta.pt

Thank you for visiting! �
