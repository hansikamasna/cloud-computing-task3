# 🌐 Task 3: Create and Configure a Virtual Private Cloud (VPC) with Subnets

## 🎯 Objective

The goal of this task is to **understand cloud networking fundamentals** by creating a **Virtual Private Cloud (VPC)** with both **public and private subnets**, and configuring controlled internet access.  
You’ll learn how to securely isolate and connect resources within the cloud.

---

## 🧠 Learning Outcomes

By completing this task, you will:

- Understand **VPC architecture** and **CIDR addressing**
- Learn the difference between **public** and **private** subnets
- Configure **Internet Gateways** and **Route Tables**
- Control **internet access** to resources within the VPC
- Build a foundation for **secure cloud deployments**

---

## 🛠️ Tools & Platforms

Choose one of the following free-tier platforms:

- **Amazon Web Services (AWS Free Tier)** 


---

## 🧭 Step-by-Step Implementation Guide

### 1️⃣ Login to Cloud Console

- Sign in to **AWS Management Console** 
- Open the **VPC Dashboard**

---

### 2️⃣ Create a Virtual Private Cloud (VPC)

1. Click **Create VPC**
2. Set the following:
   - **Name:** `myVPC`
   - **IPv4 CIDR Block:** `10.0.0.0/16`
3. Create the VPC.

This defines your private network space in the cloud.

---

### 3️⃣ Create Subnets

#### a. Public Subnet
- **Name:** `Public-Subnet`
- **CIDR Block:** `10.0.1.0/24`
- **Auto-assign Public IP:** Enabled  
  *(Allows instances to access the internet)*

#### b. Private Subnet
- **Name:** `Private-Subnet`
- **CIDR Block:** `10.0.2.0/24`
- **Auto-assign Public IP:** Disabled  
  *(Instances remain isolated from the internet)*

---

### 4️⃣ Create and Attach an Internet Gateway (IGW)

1. Navigate to **Internet Gateways → Create Internet Gateway**
2. **Name:** `MyVPC-IGW`
3. Click **Attach to VPC** and select your `MyVPC`

This enables outbound internet connectivity for your public subnet.

---

### 5️⃣ Configure Route Tables

#### a. Public Route Table
1. Create a route table named `Public-RT`
2. Add a route:
   - **Destination:** `0.0.0.0/0`
   - **Target:** Internet Gateway (`MyVPC-IGW`)
3. Associate `Public-RT` with **Public Subnet**

#### b. Private Route Table
1. Create another route table named `Private-RT`
2. Leave it with only the **local route** (default)
3. Associate it with **Private Subnet**

---

### 6️⃣ Verification

1. Go to **VPC → Subnets**
2. Confirm:
   - Public Subnet → Internet access enabled  
   - Private Subnet → No internet route
3. Optionally, launch test EC2 instances in each subnet to verify connectivity.

---

## 📸 Deliverables

Please include the following screenshots in your submission:

1. ✅ **VPC Dashboard** showing both subnets  
2. ✅ **Route Table Configuration** for Public and Private Subnets  

---

## 📝 Documentation Summary

| Item | Details |
|------|----------|
| **VPC Name** | MyVPC |
| **CIDR Range** | 10.0.0.0/16 |
| **Region** | (e.g., us-east-1 or your chosen region) |
| **Subnets** | 2 — Public (10.0.1.0/24) and Private (10.0.2.0/24) |
| **Internet Access** | Enabled for Public Subnet via IGW; Disabled for Private Subnet |
| **Route Tables** | Public-RT (with 0.0.0.0/0 → IGW), Private-RT (local only) |

---

## 💡 Outcome

After completing this task, you will have:

- Built a functional **VPC with public and private segmentation**
- Enabled secure internet access for public-facing resources
- Isolated private subnet resources for internal communication
- Gained a practical understanding of **cloud network security and routing**

---

### ✅ Example Submission Structure

