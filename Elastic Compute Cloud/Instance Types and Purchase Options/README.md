# AWS EC2 Instance Types

Amazon Elastic Compute Cloud (EC2) provides different types of instances optimized for various workloads. Each instance family is designed for a specific use case such as compute-intensive tasks, memory-heavy applications, storage workloads, or GPU-based processing.

---

## 1. General Purpose Instances

General purpose instances provide a balanced combination of **CPU, memory, and networking resources**. They are suitable for a wide variety of workloads.

### Common Instance Families

* t2
* t3
* t4g
* m5
* m6i

### Use Cases

* Web servers
* Small databases
* Development and testing environments
* Business applications

### Example

```bash
t2.micro
t3.medium
m5.large
```

---

## 2. Compute Optimized Instances

Compute optimized instances are designed for applications that require **high CPU performance**.

### Common Instance Families

* c5
* c6i
* c7g

### Use Cases

* High-performance web servers
* Batch processing
* Scientific modeling
* Gaming servers
* Media transcoding

### Example

```bash
c5.large
c6i.xlarge
```

---

## 3. Memory Optimized Instances

Memory optimized instances are designed for workloads that require **large amounts of RAM**.

### Common Instance Families

* r5
* r6i
* x1
* x2

### Use Cases

* In-memory databases
* Real-time analytics
* Big data processing
* SAP applications

### Example

```bash
r5.large
r6i.2xlarge
```

---

## 4. Storage Optimized Instances

Storage optimized instances are designed for workloads that require **high disk throughput and IOPS**.

### Common Instance Families

* i3
* i4i
* d2
* h1

### Use Cases

* NoSQL databases
* Data warehousing
* Distributed file systems
* Log processing

### Example

```bash
i3.large
d2.xlarge
```

---

## 5. Accelerated Computing Instances

Accelerated computing instances use **hardware accelerators like GPUs or FPGAs** to speed up complex workloads.

### Common Instance Families

* p3
* p4
* g4
* g5
* f1

### Use Cases

* Machine learning
* Artificial intelligence
* Video rendering
* Graphics processing
* Scientific simulations

### Example

```bash
g4dn.xlarge
p3.2xlarge
```

---

## Summary

| Instance Category     | Focus                | Example Use Case    |
| --------------------- | -------------------- | ------------------- |
| General Purpose       | Balanced CPU, RAM    | Web applications    |
| Compute Optimized     | High CPU             | Batch processing    |
| Memory Optimized      | High RAM             | In-memory databases |
| Storage Optimized     | High disk throughput | Data warehouses     |
| Accelerated Computing | GPU/FPGA             | Machine learning    |

---

## How to View Instance Types Using AWS CLI

```bash
aws ec2 describe-instance-types
```

---

## Useful Reference

Official AWS Documentation:
https://docs.aws.amazon.com/ec2/latest/instancetypes/

---

## Conclusion

Selecting the right EC2 instance type is important for optimizing **performance, cost, and scalability**. AWS provides multiple instance families to support different types of workloads and application requirements.

# AWS EC2 Instance Purchase Options

Amazon EC2 provides multiple purchasing options to help users optimize **cost, flexibility, and availability** depending on workload requirements.

Each purchase option is designed for a different type of usage pattern.

---

# 1. On-Demand Instances

On-Demand instances allow you to pay for compute capacity **by the hour or second with no long-term commitments**.

## Characteristics

* No upfront payment
* No long-term contract
* Pay only for the time you use the instance

## Advantages

* Maximum flexibility
* No commitment required
* Ideal for unpredictable workloads

## Use Cases

* Development and testing
* Short-term projects
* Applications with unpredictable traffic

## Example

```bash
Launch instance normally from EC2 console
```

---

# 2. Reserved Instances

Reserved Instances (RI) provide a **significant discount compared to On-Demand pricing** in exchange for a **1-year or 3-year commitment**.

## Characteristics

* Long-term commitment
* Lower hourly pricing
* Reservation applied to matching instances

## Types of Reserved Instances

* **Standard Reserved Instances**
* **Convertible Reserved Instances**

### Standard Reserved Instances

* Highest discount
* Cannot change instance family

### Convertible Reserved Instances

* Slightly lower discount
* Can change instance type, family, or OS

## Use Cases

* Long-running production workloads
* Stable applications
* Databases and backend services

---

# 3. Spot Instances

Spot Instances allow you to use **unused AWS EC2 capacity at very low prices**, sometimes up to **90% cheaper than On-Demand**.

However, AWS can **terminate the instance with a 2-minute notice** when capacity is needed.

## Characteristics

* Very low cost
* Can be interrupted anytime
* Best for fault-tolerant applications

## Advantages

* Significant cost savings

## Use Cases

* Batch processing
* Data analysis
* CI/CD pipelines
* Big data workloads
* Machine learning training

---

# 4. Savings Plans

Savings Plans provide flexible pricing in exchange for a **commitment to use a certain amount of compute per hour for 1 or 3 years**.

## Characteristics

* Commitment-based pricing
* Applies across instance families
* Automatically reduces costs

## Types of Savings Plans

* **Compute Savings Plans**
* **EC2 Instance Savings Plans**

### Compute Savings Plans

* Most flexible
* Works across instance types and regions

### EC2 Instance Savings Plans

* Highest discount
* Applies to a specific instance family in a region

---

# 5. Dedicated Instances

Dedicated Instances run on **hardware dedicated to a single AWS account**.

## Characteristics

* Physical server isolation
* Useful for compliance requirements

## Use Cases

* Regulatory compliance
* Security-sensitive workloads

---

# 6. Dedicated Hosts

Dedicated Hosts provide **full control over the physical server**.

## Characteristics

* Entire physical server allocated
* Visibility of sockets and cores

## Use Cases

* License-based software
* Compliance workloads
* Enterprise applications

---

# Summary Table

| Purchase Option     | Cost       | Commitment   | Interruption | Best Use Case            |
| ------------------- | ---------- | ------------ | ------------ | ------------------------ |
| On-Demand           | Highest    | None         | No           | Short-term workloads     |
| Reserved Instances  | Lower      | 1 or 3 years | No           | Long-running workloads   |
| Spot Instances      | Lowest     | None         | Yes          | Fault-tolerant workloads |
| Savings Plans       | Discounted | 1 or 3 years | No           | Flexible long-term usage |
| Dedicated Instances | High       | Optional     | No           | Compliance workloads     |
| Dedicated Hosts     | Highest    | Optional     | No           | Licensing requirements   |

---

# Conclusion

AWS EC2 provides multiple purchasing models to help organizations **balance cost, flexibility, and performance**. Selecting the right option depends on workload stability, budget, and tolerance for interruptions.
