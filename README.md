# aws
# Understanding Port Numbers in AWS

## Q1) What is a Port Number?

In AWS, a **port number** is a communication endpoint that allows specific types of traffic to reach services or applications hosted on AWS resources, such as EC2 instances or RDS databases. Port numbers help identify the type of service running and control access through security group rules.

Alternatively:

- A **port number** is a numerical identifier assigned to a specific process or service on a computer or server to facilitate communication over a network. It helps direct incoming and outgoing data to the correct application or service.

- A **port number** is like a door that helps a computer or server decide where to send or receive data. Each type of service or application has its own port number.

### Examples of AWS Port Numbers:

1. **Port 22**: Used for SSH access to EC2 instances.  
2. **Port 80**: Used for HTTP traffic to web servers.  
3. **Port 443**: Used for HTTPS traffic to secure web servers.  
4. **Port 3306**: Used for connecting to a MySQL database on RDS.  

These ports are managed in AWS Security Groups to allow or deny specific traffic, ensuring secure and efficient communication.

# Security Groups
## Q2) What is a Security Group?

A **security group** in AWS acts as a virtual firewall for your EC2 instances and other resources. It controls inbound and outbound traffic to ensure secure communication.

### Key Points:
1. **Inbound Rules**: Define the traffic allowed **into** the resource.  
2. **Outbound Rules**: Define the traffic allowed **out** of the resource.  
3. **Stateful**: If you allow traffic in one direction, the response traffic is automatically allowed in the opposite direction.  
4. **Assigned to Resources**: You can attach one or more security groups to EC2 instances, RDS databases, or other services.  

### Example in Day-to-Day Life:
Imagine your house:  
1. **Inbound Rules**: You allow friends to enter through the main door (specific people).  
2. **Outbound Rules**: You allow family members to leave for work (specific people leaving).  
3. **Stateful**: If a friend is allowed in, they are also allowed to leave without needing extra permission.

In AWS:
- You allow **port 22** (SSH) for trusted people (developers) to log in.  
- You allow **port 80** (HTTP) for anyone to view your website.  
- Only the rules you set determine who can access your resources or services, keeping them safe.

# AWS Key Pair Overview

## What is a Key Pair?

A **key pair** in AWS is a security credential used to securely log in to your EC2 instances. It consists of two parts:

1. **Public Key**: Stored on the EC2 instance by AWS.
2. **Private Key**: Downloaded and kept by the user to authenticate and access the instance.

## How It Works

- The **public key** stays on the server (EC2 instance).
- The **private key** is used by the user to establish a secure connection via SSH.
- Only someone with the correct private key can access the instance.

## Example

When launching an EC2 instance, you create or select a key pair. You use the private key file (e.g., `my-key.pem`) to connect to the instance securely.

## Important Notes

- Keep the private key safe; AWS cannot regenerate it for you.
- If you lose the private key, you'll lose SSH access to the instance unless you create a workaround (e.g., creating a new key pair and adding its public key to the instance).

This ensures secure access to your AWS resources.
