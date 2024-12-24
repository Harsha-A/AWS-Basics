# AWS-Basics
Basics of AWS

### 1. **Subnet**
   - **Definition**: A **subnet** (short for sub-network) is a segment of a VPC's IP address range where you can place resources like EC2 instances. Subnets are used to group resources and control how they communicate within the VPC.
   - **Types**:
     - **Public Subnet**: A subnet with a route to the Internet Gateway (for public access).
     - **Private Subnet**: A subnet without direct internet access.
   - **Use Cases**:
     - Separate resources based on access needs (public-facing vs. internal).
     - Enhance security by isolating sensitive workloads in private subnets.

---

### 2. **Security Groups**
   - **Definition**: A **security group** acts as a virtual firewall at the instance level, controlling inbound and outbound traffic for your resources.
   - **Key Features**:
     - Works at the instance level.
     - Stateful: When you allow inbound traffic, the outbound traffic is automatically allowed for that connection.
     - Rules are defined for specific ports, IP addresses, or CIDR blocks.
   - **Use Cases**:
     - Allow HTTP (port 80) and HTTPS (port 443) traffic to a web server.
     - Restrict database access to specific application servers.

---

### 3. **NACL (Network Access Control List)**
   - **Definition**: A **NACL** is a layer of security for controlling traffic at the subnet level.
   - **Key Features**:
     - Works at the subnet level.
     - Stateless: Inbound and outbound rules must be explicitly defined.
     - Rules are evaluated in numerical order (lowest to highest).
   - **Differences from Security Groups**:
     - Security Groups are stateful, while NACLs are stateless.
     - Security Groups work at the instance level, whereas NACLs work at the subnet level.
   - **Use Cases**:
     - Add an additional layer of security for specific subnets.
     - Block specific IP addresses or ranges at the subnet level.

---

### 4. **Route 53**
   - **Definition**: **Amazon Route 53** is a scalable and highly available DNS (Domain Name System) web service.
   - **Key Features**:
     - **DNS Management**: Map domain names to AWS resources (e.g., EC2, S3, CloudFront).
     - **Health Checks**: Monitor the health of resources and route traffic accordingly.
     - **Routing Policies**: 
       - Simple
       - Weighted
       - Latency-based
       - Geolocation
       - Failover
   - **Use Cases**:
     - Host a website and direct traffic to its resources.
     - Create disaster recovery setups using failover routing.
     - Manage internal DNS for AWS environments.

---

### 5. **GuardDuty**
   - **Definition**: **Amazon GuardDuty** is a threat detection service that continuously monitors your AWS accounts and workloads for malicious activity and unauthorized behavior.
   - **Key Features**:
     - Uses machine learning, anomaly detection, and threat intelligence.
     - Provides detailed security findings for actions.
     - Supports multi-account setups for centralized threat detection.
   - **Use Cases**:
     - Detect unusual login attempts or API calls.
     - Identify compromised EC2 instances running unauthorized processes.
     - Monitor and secure AWS environments without manual intervention.

---

### Summary Table

| Service        | Purpose                                      | Key Feature                          | Use Case                                      |
|----------------|----------------------------------------------|---------------------------------------|----------------------------------------------|
| **Subnet**     | Divide VPC into smaller networks.            | Public/Private types.                 | Isolate public-facing resources.             |
| **Security Group** | Instance-level firewall.                   | Stateful traffic rules.               | Allow HTTP/HTTPS for a web server.           |
| **NACL**       | Subnet-level traffic control.                | Stateless, ordered rules.             | Block specific IP ranges.                    |
| **Route 53**   | Scalable DNS and traffic management service. | Routing policies, health checks.      | Host a website and route domain traffic.     |
| **GuardDuty**  | Threat detection and monitoring service.     | Uses ML and anomaly detection.        | Detect and respond to security threats.      |
