# EC2

## AWS Budget Setup

- **Billing & Cost Management**: Free to use for tracking bills, invoices, and payments.
- **Budgets**:
  - 2 budgets per account → Free.
  - Beyond 2 → $0.02 per day per budget.
- **Cost Explorer**:
  - Free for 12 months (750 hours/month).
  - After → $0.01 per usage report.
- **Alerts**:
  - Uses Amazon SNS.
  - Free up to 1M notifications/month.

## EC2

- **IaaS** (Infrastructure as a Service).
- **Elastic Cloud Computing**: Flexible, on-demand compute capacity.
- **Virtual Machines (EC2)**: Run scalable servers.
- **Storing Data (EBS)**: Persistent block storage volumes for EC2.
- **Distributing Load (ELB)**: Balances incoming traffic across multiple EC2 instances.
- **Scaling (ASG)**: Auto Scaling Groups automatically adjust the number of EC2 instances to match demand.

---

# 🚀 EC2 & AWS Budgets – Elite 1% Insight

Only the top 1% AWS practitioners internalize this depth of understanding. What you’re about to read is **not surface-level AWS training**—this is the mindset and knowledge that separates an AWS user from an AWS architect.

---

## 🧾 AWS Budgets – The Secret Weapon

- **Definition**: AWS Budgets is a _financial control plane_. It doesn’t just track costs—it enforces financial discipline on your cloud strategy.
- **Purpose for the Elite**: Instead of waiting for a $10k surprise bill at month’s end, you build _guardrails_ that notify and automate reactions before damage happens.
- **Core Principle**: Treat cost like another resource—if you don’t architect for cost, you are not architecting at all.

### Elite Strategies:

1. **Budget by Team/Project** – assign budgets per IAM group.

   > Forces cost accountability across departments.

2. **Anomaly Detection** – pair AWS Budgets with _CloudWatch + SNS_ to auto-trigger actions when costs spike.

   > Example: Shut down non-critical EC2s automatically at 2 AM when cost thresholds are breached.

3. **Game Theory Mindset** – the best engineers budget not for current cost, but for _future scale_.
   > Anticipating exponential growth avoids death by “cloud bill shock.”

---

## 🖥️ EC2 – The Beating Heart of AWS Infrastructure

EC2 is not “just servers in the cloud.” To the top 1%, EC2 represents **elastic computing as an economic engine**.

- **IaaS (Infrastructure-as-a-Service)**  
  Full control: OS, networking, storage. AWS only manages the bare metal.

- **Elasticity**  
  Spin up 1 VM or 10,000 in minutes. _Elastic Cloud_ = competitive advantage in speed-to-market.

- **EBS (Elastic Block Store)**  
  Persistent, durable storage. Think of it as SSDs you can attach/detach from your VMs at will.

  - 🔥 Pro Tip: Top engineers **always snapshot** EBS volumes—cheap insurance for disasters.

- **ELB (Elastic Load Balancer)**  
  Not just distributing traffic—it’s a **resilience layer**. If you aren’t balancing across AZs, you aren’t really doing “high availability.”

- **ASG (Auto Scaling Groups)**  
  This is the killer feature. With correct policies:
  - Traffic doubles → Instances double.
  - Traffic halves → Instances halve.
    > Elite mindset: **Never pay for idle compute.**

---

## 🏆 What the 1% Know That 99% Don’t

1. **EC2 isn’t about servers—it’s about leverage.**  
   You don’t buy hardware, you rent elastic capability.

2. **Cost control is architecture.**  
   AWS Budgets + EC2 Auto Scaling = _financially-aware infrastructure_.

3. **Speed beats size.**  
   Any startup with this knowledge can outmaneuver incumbents with 100x bigger budgets.

4. **Mental Model:**
   - EC2 = _muscle (compute)_
   - EBS = _memory (storage)_
   - ELB = _circulatory system (distribution)_
   - ASG = _autonomic nervous system (self-adjusting)_
   - Budgets = _conscious brain (control & discipline)_

---

### EC2 Instances

- **t2.micro** → Small, low-cost instance (used for free tier, testing, very light workloads).
- **t2.xlarge** → Larger general-purpose instance with more CPU & memory.
- **c5d.4xlarge** → Compute-optimized instance with local NVMe storage (good for CPU-heavy tasks like gaming servers, video encoding).
- **r5.16xlarge** → Memory-optimized instance (used for databases, in-memory caches).
- **m5.8xlarge** → Balanced instance for both compute and memory workloads (good for enterprise apps).

---

### Creating an Instance

1. **Create an instance**

   - Choose AMI (Amazon Machine Image → Ubuntu, Windows, etc.)
   - Select instance type (e.g., t2.micro)

2. **Use tags**

   - Add metadata like:
     - `Name = WebServer`
     - `Environment = Production`

3. **User data on first launch**

   - Add startup scripts (e.g., install Nginx, set up app).
   - Example:

     ```bash
     #!/bin/bash
     apt update -y
     apt install nginx -y
     systemctl start nginx
     ```

# EC2 — Knowledge from the Top 0.5%

Most people know **EC2 is a VM in the cloud**.  
But the real experts know the **deep mechanics** that separate a "cloud user" from a "cloud architect".

---

## 1. EC2 is Not Just a VM

- **Under the hood**, EC2 instances run on a **hypervisor called Nitro**.
- Nitro offloads storage, networking, and security into **dedicated hardware cards**, so the main CPU is **100% yours**.
- This is why EC2 outperforms many traditional VM platforms.

---

## 2. Burstable Performance (t2/t3 Instances)

- Instances like **t2.micro** run on **CPU credits**.
- You earn credits when the CPU is idle, and spend them during bursts.
- If you run out, your CPU speed can **throttle to the baseline** (making apps super slow).
- Top engineers **monitor CPU credit balance** with CloudWatch to avoid hidden performance cliffs.

---

## 3. Placement Groups = Hidden Superpower

- EC2 instances can be launched in **placement groups**:
  - **Cluster** → Low latency, high bandwidth (great for HPC, ML training).
  - **Spread** → Separate across hardware for high availability.
  - **Partition** → Control failure domains (used in Hadoop, Cassandra).
- Misplacing instances can **double or triple network latency**.

---

## 4. EBS vs Instance Store

- **EBS** = Persistent storage (survives stop/start).
- **Instance Store** = Fast ephemeral NVMe, **10x faster**, but data is lost when stopped.
- Smart engineers combine both:
  - Databases → EBS for persistence.
  - Cache/temp data → Instance store for speed.

---

## 5. ENA & SR-IOV Networking

- EC2 uses **Elastic Network Adapter (ENA)** and **SR-IOV** (Single Root I/O Virtualization).
- This allows **direct hardware-level networking** bypassing the hypervisor.
- Result: **10–100 Gbps throughput** with microsecond latency.
- This is why EC2 can handle **HPC clusters and real-time trading apps**.

---

## 6. EC2 Spot = Billion-Dollar Hack

- Spot instances are **90% cheaper**, but can be reclaimed anytime.
- Experts run **fault-tolerant workloads** (batch jobs, ML training, CI/CD) on Spot.
- Using **EC2 Fleet + Spot Advisor**, you can **game AWS pricing** to save millions.

---

## 7. Hidden Cost Traps

- **EBS IOPS** and **data transfer out** often cost more than the instance itself.
- Real experts always measure **$/IOPS** and **$/Gbps**, not just **$/hour**.

---

## 8. EC2 Warm Pools

- Scaling groups normally take minutes to launch new instances.
- **Warm pools** keep instances pre-initialized but stopped.
- This cuts auto-scaling response times from **minutes to seconds**.

---

# 🔑 Key Insight

EC2 is not just "a VM in the cloud".  
It’s a **hardware abstraction layer + custom networking + billing game**.  
The top 0.5% know:

> The biggest cost/performance wins come from **understanding Nitro, placement groups, Spot strategy, and IOPS math** — not just launching bigger instances.

### Instance type basics

### Security groups and Classic ports
