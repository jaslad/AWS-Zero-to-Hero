# 🚀 AWS Application Load Balancer (ALB) Lab

## 📌 Overview

This lab demonstrates how to set up an **Application Load Balancer (ALB)** in AWS to distribute traffic across multiple EC2 instances. You will create EC2 instances, configure a target group, and attach them to an ALB.

---

## 🎯 Objectives

* Launch EC2 instances
* Install and configure a web server (Nginx)
* Create a Target Group
* Create an Application Load Balancer
* Register EC2 instances with the target group
* Test load balancing

---

## 🧱 Architecture

```
User → ALB → Target Group → EC2 Instances
```

---

## 🛠️ Prerequisites

* AWS account
* Basic knowledge of EC2 and networking
* Key pair for SSH access
* Security group allowing:

  * HTTP (80)
  * SSH (22)

---

## 🚀 Step 1: Launch EC2 Instances

1. Go to EC2 Console → Launch Instance
2. Configure:

   * AMI: Amazon Linux 2
   * Instance Type: t2.micro
   * Number of instances: 2
3. Configure Security Group:

   * Allow HTTP (80)
   * Allow SSH (22)
4. Launch instances using a key pair

---

## 🔧 Step 2: Install Web Server (Nginx)

SSH into each instance:

```bash
sudo yum update -y
sudo yum install nginx -y
sudo systemctl enable --now nginx
```

---

## 📝 Step 3: Add Custom Web Page

On Instance 1:

```bash
echo "This is Server 1" | sudo tee /usr/share/nginx/html/index.html
```
```
sudo systemctl restart nginx
```
On Instance 2:

```bash
echo "This is Server 2" | sudo tee /usr/share/nginx/html/index.html
```
```
sudo systemctl restart nginx
```
---

## 🎯 Step 4: Create Target Group

1. Go to EC2 → Target Groups
2. Click **Create Target Group**
3. Configure:

   * Target type: Instances
   * Protocol: HTTP
   * Port: 80
   * Health check path: `/`
4. Register EC2 instances
5. Create target group

---

## 🌐 Step 5: Create Application Load Balancer

1. Go to EC2 → Load Balancers
2. Click **Create Load Balancer**
3. Choose **Application Load Balancer**
4. Configure:

   * Scheme: Internet-facing
   * Listener: HTTP (80)
   * Select at least 2 Availability Zones
5. Select the target group created earlier
6. Create load balancer

---

## 🧪 Step 6: Test Load Balancer

1. Copy the **DNS name** of the ALB
2. Open in browser
3. Refresh multiple times

✅ You should see:

* "This is Server 1"
* "This is Server 2"

👉 This confirms load balancing is working

---

## 🔍 Step 7: Health Check Verification

* Go to Target Groups → Targets
* Ensure both instances show **healthy**

---

## 🧹 Cleanup

To avoid charges:

* Terminate EC2 instances
* Delete Load Balancer
* Delete Target Group
* Delete Security Groups (if created specifically for lab)

---

## 💡 Key Learnings

* How ALB distributes traffic
* Importance of health checks
* Target group configuration
* High availability using multiple instances

---

## 🔥 Bonus (Optional Enhancements)

* Add HTTPS using ACM
* Configure path-based routing
* Use Auto Scaling Group
* Deploy using Terraform

---

## 📢 Conclusion

This lab provides hands-on experience in setting up a scalable and highly available architecture using AWS Application Load Balancer and EC2 instances.

---
