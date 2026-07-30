  # 🚀 Scalable and Secure Compute Infrastructure in Google Cloud

> A comprehensive hands-on Google Cloud Platform (GCP) project demonstrating the deployment of scalable, secure, highly available, and cost-optimized compute infrastructure using Google Compute Engine, Managed Instance Groups, Load Balancing, Google App Engine, Cloud Functions, and Cloud Monitoring.

---

## 📖 Table of Contents

- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Project Scope](#project-scope)
- [Architecture Overview](#architecture-overview)
- [Technologies Used](#technologies-used)
- [Prerequisites](#prerequisites)
- [Implementation](#implementation)
- [Security Best Practices](#security-best-practices)
- [Cost Optimization](#cost-optimization)
- [Challenges Encountered](#challenges-encountered)
- [Lessons Learned](#lessons-learned)
- [Project Outcome](#project-outcome)
- [Screenshots](#screenshots)
- [Conclusion](#conclusion)
- [References](#references)

---

# 📌 Project Overview

Cloud computing enables organizations to deploy applications that are scalable, reliable, and resilient without investing in physical infrastructure. Google Cloud Platform (GCP) provides a wide range of managed services that simplify infrastructure deployment while improving security, availability, and operational efficiency.

This project demonstrates the deployment and management of a scalable compute environment using *Google Compute Engine (GCE). The implementation begins with provisioning a virtual machine, configuring secure remote access, and deploying an Apache web server. The infrastructure is then enhanced with **Instance Templates, **Managed Instance Groups, **Autoscaling, **HTTP Load Balancing, **Health Checks, and **Custom VM Images* to improve scalability and fault tolerance.

The project further explores Google's serverless offerings through *Google App Engine* and *Cloud Functions, and concludes by implementing **Google Cloud Monitoring* to observe system health, performance metrics, and operational status.

By completing this project, practical experience was gained in designing cloud-native infrastructure that aligns with industry best practices for security, scalability, reliability, and cost optimization.

---

# 🎯 Objectives

The primary objectives of this project are to:

- Deploy a Compute Engine Virtual Machine on Google Cloud Platform.
- Configure secure SSH access for remote server administration.
- Install and configure the Apache Web Server.
- Verify web server accessibility through the VM's external IP address.
- Create an Instance Template for standardized VM deployments.
- Configure a Managed Instance Group for high availability.
- Enable Autoscaling based on workload demand.
- Implement an HTTP Load Balancer to distribute incoming traffic.
- Configure Health Checks to monitor backend instance availability.
- Create a reusable Custom VM Image.
- Explore Platform as a Service (PaaS) deployment using Google App Engine.
- Deploy a Serverless Function using Google Cloud Functions.
- Monitor compute resources using Google Cloud Monitoring.
- Apply cloud security and cost optimization best practices throughout the deployment.

---

# 📂 Project Scope

The project covers the following Google Cloud services:

- Google Compute Engine
- Virtual Machine Administration
- SSH Connectivity
- Apache Web Server Deployment
- Instance Templates
- Managed Instance Groups
- Autoscaling
- HTTP Load Balancing
- Health Checks
- Custom VM Images
- Google App Engine
- Google Cloud Functions
- Google Cloud Monitoring
- Identity and Access Management (IAM)
- Virtual Private Cloud (VPC) Firewall Rules

The implementation reflects a simplified production-ready cloud infrastructure suitable for hosting scalable web applications.

---

# 🏗️ Architecture Overview

The project architecture is designed to provide scalability, reliability, security, and efficient resource utilization by combining multiple Google Cloud services.

```text
                              Internet Users
                                     │
                                     ▼
                     HTTP Load Balancer (Global)
                                     │
                    ┌────────────────┴────────────────┐
                    │                                 │
                    ▼                                 ▼
           VM Instance 1                     VM Instance 2
            (Apache Web Server)              (Apache Web Server)
                    │                                 │
                    └───────────────┬─────────────────┘
                                    │
                       Managed Instance Group
                                    │
                           Instance Template
                                    │
                        Google Compute Engine
                                    │
                     Debian GNU/Linux 13 Server
                                    │
                              Apache2 Web Server

             Additional Google Cloud Services

             • Google App Engine
             • Google Cloud Functions
             • Google Cloud Monitoring
             • IAM
             • VPC Firewall Rules
```

---

# ⚙️ Technologies Used

| Technology | Purpose |
|------------|---------|
| *Google Cloud Platform (GCP)* | Cloud infrastructure provider |
| *Google Compute Engine (GCE)* | Virtual machine hosting |
| *Debian GNU/Linux 13* | Operating system |
| *Apache2* | Web server |
| *SSH* | Secure remote administration |
| *Managed Instance Groups (MIG)* | Automatic VM management |
| *Instance Templates* | Standardized VM configuration |
| *HTTP Load Balancer* | Traffic distribution |
| *Health Checks* | Backend availability monitoring |
| *Custom VM Images* | Rapid server deployment |
| *Google App Engine* | Platform-as-a-Service (PaaS) |
| *Google Cloud Functions* | Serverless computing |
| *Google Cloud Monitoring* | Performance monitoring |
| *IAM* | Identity and Access Management |
| *VPC Firewall Rules* | Network security |

---

# 📋 Prerequisites

Before beginning this project, ensure the following requirements are available:

- Active Google Cloud Platform account
- Google Cloud project
- Billing enabled (where required)
- Compute Engine API enabled
- App Engine API enabled
- Cloud Functions API enabled
- Internet connection
- Modern web browser
- Basic Linux command-line knowledge

---

# 🔄 Project Workflow

The project follows a structured deployment process:

1. Provision a Compute Engine virtual machine.
2. Configure secure SSH remote access.
3. Install and configure the Apache web server.
4. Verify web server accessibility.
5. Create an Instance Template.
6. Deploy a Managed Instance Group.
7. Enable Autoscaling.
8. Configure an HTTP Load Balancer.
9. Configure Health Checks.
10. Create a reusable Custom VM Image.
11. Explore Google App Engine deployment.
12. Deploy a Serverless Cloud Function.
13. Configure Cloud Monitoring.
14. Review security configurations.
15. Apply cloud cost optimization strategies.

---

# 🎯 Expected Outcomes

After completing this project, the following outcomes were achieved:

- Successfully deployed a Compute Engine virtual machine.
- Configured secure SSH access.
- Installed and verified the Apache web server.
- Created reusable infrastructure templates.
- Implemented autoscaling capabilities.
- Configured load balancing for high availability.
- Monitored backend health using health checks.
- Created reusable VM images.
- Explored serverless and PaaS services.
- Implemented monitoring for operational visibility.
- Applied cloud security best practices.
- Demonstrated cost-conscious cloud deployment techniques.

---

# 🚀 Implementation

This section outlines the practical steps followed to deploy a scalable and secure compute infrastructure on Google Cloud Platform.

---

## Step 1: Deploy a Google Compute Engine Virtual Machine

A Google Compute Engine (GCE) virtual machine was created to serve as the primary compute resource for hosting the web application.

### Configuration

| Parameter | Value |
|-----------|-------|
| VM Name | `web-server-1` |
| Region | `us-central1` |
| Zone | Same zone selected during deployment |
| Machine Type | `e2-micro` |
| Operating System | `Debian GNU/Linux 13` |
| Boot Disk | Standard Persistent Disk |
| Firewall | Allow HTTP and HTTPS Traffic |

### Purpose

This virtual machine provides the compute environment where the web server and application services are hosted.

### Screenshot

![VM Configuration](screenshots/02-m-creation.png)

---

## Step 2: Verify VM Deployment

After deployment, the virtual machine was verified to ensure it was successfully provisioned and running.

The following information was confirmed:

- VM Status
- Internal IP Address
- External IP Address
- Machine Type
- Zone
- Boot Disk

### Screenshot

![Running Virtual Machine](screenshots/03-vm-instance-running.png)

---

## Step 3: Configure Secure SSH Access

Secure Shell (SSH) was used to establish a secure remote connection to the virtual machine for server administration.

### Command

```bash
lsb_release -a
```

This command confirms the Linux distribution installed on the server.

### Screenshot

![SSH Connection](screenshots/04-ssh-access.png)

---

## Step 4: Install Apache Web Server

The Apache web server was installed to host web content.

### Update Package Repository

```bash
sudo apt update
```

### Install Apache

```bash
sudo apt install apache2 -y
```

### Verify Apache Status

```bash
sudo systemctl status apache2
```

A successful installation displays:

```text
Active: active (running)
```

### Screenshot

![Apache Installation](screenshots/05-apache-service-running.png)

---

## Step 5: Verify Apache Deployment

The Apache web server was verified by accessing the VM's external IP address in a web browser.

Expected Result:

The default Apache web page should be displayed.

Example:

```

http://YOUR_EXTERNAL_IP
```

### Screenshot

![Apache Default Page](screenshots/06-apache-default-page.png)

---

## Step 6: Create an Instance Template

An Instance Template was created to standardize the configuration of future virtual machine instances.

### Configuration

- Machine Type: e2-micro
- Operating System: Debian GNU/Linux
- HTTP Enabled
- HTTPS Enabled

### Purpose

Instance Templates provide consistency and simplify infrastructure deployment by ensuring all future VM instances use identical configurations.

### Screenshot

![Instance Template](screenshots/07-instance-template-created.png)

---

## Step 7: Create a Managed Instance Group

A Managed Instance Group (MIG) was created using the previously defined Instance Template.

### Autoscaling Configuration

| Setting | Value |
|----------|-------|
| Minimum Instances | 2 |
| Maximum Instances | 5 |
| Scaling Metric | CPU Utilization |

### Benefits

- Automatic VM creation
- Automatic VM replacement
- High Availability
- Automatic Scaling

### Screenshot

![Managed Instance Group](screenshots/08-managed-instance-group.png)

---

## Step 8: Configure an HTTP Load Balancer

To ensure high availability and efficient traffic distribution, an HTTP Load Balancer was configured. The load balancer distributes incoming client requests across multiple virtual machine instances within the Managed Instance Group.

### Configuration

| Parameter | Value |
|-----------|-------|
| Load Balancer Name | `web-load-balancer` |
| Backend Service | `web-backend-service` |
| Frontend | `web-frontend` |
| Protocol | HTTP |
| Port | 80 |
| Backend | Managed Instance Group |
| Health Check | `web-health-check` |

### Purpose

The HTTP Load Balancer improves application availability by distributing incoming traffic evenly across healthy backend instances. If one instance becomes unavailable, traffic is automatically redirected to healthy instances.

### Screenshot

![HTTP Load Balancer](screenshots/09-http-load-balancer-created.png)

---

## Step 9: Configure Health Checks

A Health Check was configured to continuously monitor the status of backend virtual machines.

### Configuration

| Parameter | Value |
|-----------|-------|
| Health Check Name | `web-health-check` |
| Protocol | HTTP |
| Port | 80 |
| Check Interval | Default |
| Timeout | Default |

### Purpose

Health Checks allow Google Cloud Load Balancing to determine whether backend instances are healthy. Unhealthy instances are automatically removed from traffic distribution until they recover.

### Screenshot

![Health Check](screenshots/10-health-check-cretaed.png)

---

## Step 10: Create a Custom VM Image

A reusable Custom VM Image was created from the configured Compute Engine virtual machine.

### Image Configuration

| Parameter | Value |
|-----------|-------|
| Image Name | `web-server-image` |
| Source | Existing VM Boot Disk |
| Storage Location | Multi-region |

### Benefits

- Rapid deployment of identical virtual machines
- Standardized server configuration
- Disaster recovery support
- Improved deployment consistency

### Screenshot

![Custom VM Image](screenshots/11-custom-vm-image-creted.png)

---

## Step 11: Google App Engine

Google App Engine was explored as Google's fully managed Platform as a Service (PaaS) solution for deploying web applications.

### Expected Configuration

| Parameter | Value |
|-----------|-------|
| Runtime | Python |
| Region | `us-central1` |

### Challenge Encountered

During deployment, the App Engine region selector displayed the message:

> *"No items to display."*

As a result, the application could not be created. This appears to be a Google Cloud Console or project limitation rather than a configuration error.

### Screenshot

![App Engine Region Limitation](screenshots/12-app-engine-error.png)

---

## Step 12: Deploy a Google Cloud Function

A serverless HTTP-triggered Cloud Function was deployed using Python.

### Function Code

```python
def hello_world(request):
    return "Hello, GCP Compute!", 200
```

### Function Configuration

| Parameter | Value |
|-----------|-------|
| Function Name | `hello-function` |
| Runtime | Python |
| Trigger | HTTP |
| Authentication | Allow unauthenticated |

### Purpose

Cloud Functions enable developers to execute code without managing infrastructure. Google automatically provisions resources, scales the function based on demand, and handles server maintenance.

### Screenshot

![Cloud Function](screenshots/13-cloud-function-deployed.png)

---

## Step 13: Configure Cloud Monitoring

Google Cloud Monitoring was used to observe the health, performance, and availability of deployed resources.

### Metrics Monitored

- CPU Utilization
- Virtual Machine Health
- Network Traffic
- Disk Utilization
- Logs
- Performance Metrics

### Purpose

Cloud Monitoring provides real-time visibility into infrastructure performance, enabling administrators to identify issues early, configure alerts, and maintain service reliability.

### Screenshot

![Cloud Monitoring](screenshots/14-cloud-monitoring-dashboard.png)


---

# 🔒 Security Best Practices

Security was considered throughout the deployment process to ensure that compute resources were protected and accessible only through approved methods.

The following security measures were implemented:

- Enabled secure SSH access for remote administration.
- Configured VPC firewall rules to allow only required HTTP (Port 80) and HTTPS (Port 443) traffic.
- Used Google Cloud Identity and Access Management (IAM) to control administrative permissions.
- Configured HTTP Health Checks to ensure only healthy instances receive production traffic.
- Leveraged Managed Instance Groups for automatic instance recovery.
- Applied the Principle of Least Privilege (PoLP) by granting only the permissions required for each task.

These practices improve infrastructure security while maintaining service availability.

---

# 💰 Cost Optimization

Cloud cost optimization is essential for building efficient and sustainable infrastructure. Several optimization techniques were incorporated into this project.

## Implemented Strategies

- Selected the *e2-micro* machine type for cost-efficient compute resources.
- Used *Managed Instance Groups* to automate resource management.
- Enabled *Autoscaling* so additional instances are created only when demand increases.
- Used *Cloud Monitoring* to observe resource utilization and identify underutilized resources.

## Recommended Production Optimizations

For larger production environments, the following strategies are recommended:

- Right-size virtual machines based on workload.
- Use *Preemptible/Spot VMs* for fault-tolerant workloads.
- Purchase *Committed Use Discounts (CUDs)* for predictable long-term workloads.
- Regularly monitor usage with Cloud Monitoring and Billing Reports.

These techniques help reduce operational costs while maintaining application performance.

---

# ⚠️ Challenges Encountered

During implementation, several challenges were encountered and successfully resolved.

| Challenge | Resolution |
|------------|------------|
| Temporary Compute Engine stockout in selected zone | Switched to an available zone/region |
| Apache web page initially inaccessible | Verified Apache installation and firewall configuration |
| App Engine region selector displayed *"No items to display"* | Confirmed project configuration and documented the platform limitation |
| Cloud service provisioning delays | Allowed additional time for Google Cloud services to initialize |

These experiences demonstrate the importance of troubleshooting and adapting to cloud platform constraints.

---

# 📚 Lessons Learned

This project provided valuable hands-on experience with Google Cloud Platform and reinforced several cloud engineering concepts.

Key lessons include:

- Provisioning and managing virtual machines using Google Compute Engine.
- Configuring secure remote administration using SSH.
- Deploying and validating a Linux-based Apache web server.
- Building scalable infrastructure with Instance Templates and Managed Instance Groups.
- Implementing HTTP Load Balancing and Health Checks for high availability.
- Creating reusable Custom VM Images.
- Understanding Platform as a Service (PaaS) using Google App Engine.
- Deploying event-driven applications using Google Cloud Functions.
- Monitoring cloud infrastructure using Google Cloud Monitoring.
- Applying cloud security and cost optimization best practices.

---

# 🎯 Project Outcome

The project successfully demonstrated the deployment of a scalable, secure, and highly available compute infrastructure on Google Cloud Platform.

Major achievements include:

- Successfully deployed a Compute Engine virtual machine.
- Configured secure SSH access.
- Installed and verified an Apache web server.
- Implemented Instance Templates and Managed Instance Groups.
- Configured HTTP Load Balancing and Health Checks.
- Created a reusable Custom VM Image.
- Explored App Engine deployment.
- Deployed a serverless Cloud Function.
- Implemented Cloud Monitoring for infrastructure visibility.
- Applied security and cost optimization best practices.

This project reflects industry-standard cloud engineering practices used to build reliable and resilient cloud environments.

---

# 📸 Screenshots

| Screenshot | Description |
|------------|-------------|
| 01 | Compute Engine VM Configuration |
| 02 | Running Virtual Machine |
| 03 | SSH Access and OS Verification |
| 04 | Apache Installation |
| 05 | Apache Default Web Page |
| 06 | Instance Template |
| 07 | Managed Instance Group |
| 08 | HTTP Load Balancer |
| 09 | Health Check |
| 10 | Custom VM Image |
| 11 | App Engine Region Limitation |
| 12 | Cloud Function Deployment |
| 13 | Cloud Monitoring Dashboard |

---

# ✅ Conclusion

This project successfully demonstrated how Google Cloud Platform can be used to build secure, scalable, and resilient compute infrastructure. Beginning with a single Compute Engine virtual machine, the deployment evolved into a highly available architecture through the use of Instance Templates, Managed Instance Groups, HTTP Load Balancing, and Health Checks. Additional services such as Google Cloud Functions and Cloud Monitoring showcased Google's serverless and observability capabilities, while security and cost optimization practices ensured that the infrastructure aligned with modern cloud engineering standards.

Overall, this project strengthened practical skills in infrastructure deployment, Linux administration, networking, scalability, monitoring, and cloud security, providing a solid foundation for deploying production-ready workloads on Google Cloud Platform.

---

# 📖 References

- [Google Cloud Documentation](https://cloud.google.com/docs)
- [Google Compute Engine Documentation](https://cloud.google.com/compute/docs)
- [Google Cloud Load Balancing Documentation](https://cloud.google.com/load-balancing/docs)
- [Managed Instance Groups Documentation](https://cloud.google.com/compute/docs/instance-groups)
- [Google App Engine Documentation](https://cloud.google.com/appengine/docs)
- [Google Cloud Functions Documentation](https://cloud.google.com/functions/docs)
- [Google Cloud Monitoring Documentation](https://cloud.google.com/monitoring/docs)
- [Google Cloud IAM Documentation](https://cloud.google.com/iam/docs)
- [Google Cloud Architecture Framework](https://cloud.google.com/architecture/framework)

---

# 👨‍💻 Author

## *Adepomola Ayomide*

*Cloud & DevOps Engineer*

### Skills Demonstrated

- Google Cloud Platform (GCP)
- Google Compute Engine
- Linux System Administration
- Cloud Networking
- Load Balancing
- Autoscaling
- Serverless Computing
- Cloud Monitoring
- Infrastructure Security
- Cost Optimization
- Git & GitHub

> "Building scalable, secure, and reliable cloud infrastructure through continuous learning and hands-on projects."

