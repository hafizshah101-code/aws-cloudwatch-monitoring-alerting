# AWS Cloud Operations Monitoring & Alerting Lab

## Project Overview

This project demonstrates how to build a basic AWS Cloud Operations environment with monitoring, observability, and alerting using native AWS services.

The objective is to deploy an EC2 instance inside a custom VPC, configure CloudWatch monitoring, visualize infrastructure metrics through a CloudWatch Dashboard, and implement automated email notifications using CloudWatch Alarms and Amazon SNS.

---

## Architecture

Internet
    │
    ▼
Internet Gateway
    │
    ▼
Public Subnet
    │
    ▼
Amazon EC2 (Amazon Linux 2023)
    │
    ├── CloudWatch Agent
    │
    ▼
Amazon CloudWatch
    │
    ├── Dashboard
    ├── Metrics
    ├── Alarm
    │
    ▼
Amazon SNS
    │
    ▼
Email Notification

---

## AWS Services Used

- Amazon VPC
- Public Subnet
- Internet Gateway
- Route Table
- Security Group
- Amazon EC2
- IAM Role
- CloudWatch Agent
- Amazon CloudWatch
- CloudWatch Dashboard
- CloudWatch Alarm
- Amazon SNS

---

## Project Objectives

- Deploy an EC2 instance in a custom VPC.
- Configure IAM Role for CloudWatch Agent.
- Install and configure CloudWatch Agent.
- Publish EC2 system metrics to CloudWatch.
- Create a CloudWatch Dashboard.
- Configure CPU utilization alarms.
- Send email notifications using Amazon SNS.
- Validate monitoring by generating CPU load with stress-ng.

---

## Project Workflow

### 1. AWS Networking

- Created a custom VPC
- Created a public subnet
- Configured Internet Gateway
- Configured Route Table
- Configured Security Group

---

### 2. EC2 Deployment

- Launched Amazon Linux 2023 EC2
- Assigned IAM Role
- Connected via SSH
- Updated operating system

---

### 3. CloudWatch Agent

Installed CloudWatch Agent.

Configured the agent to publish:

- CPU Metrics
- Memory Utilization
- Disk Utilization

Verified that custom metrics appeared inside CloudWatch.

---

### 4. CloudWatch Dashboard

Created a dashboard containing:

- CPUUtilization
- Memory Utilization

The dashboard provides real-time infrastructure monitoring.

---

### 5. CloudWatch Alarm

Created a CloudWatch Alarm with:

Metric:
- CPUUtilization

Condition:
- Greater than 70%

Evaluation:
- 1 datapoint within 1 minute

---

### 6. Amazon SNS

Created an SNS Topic.

Subscribed an email endpoint.

Configured the CloudWatch Alarm to publish notifications to the SNS Topic.

---

### 7. Stress Test

Installed stress-ng.

Generated high CPU utilization to validate monitoring and alerting.

Example:

```bash
sudo stress-ng --cpu 4 --timeout 300s
```

The test successfully increased CPU utilization above 90%.

---

## Validation Results

✅ CloudWatch Dashboard displayed live CPU metrics.

✅ CloudWatch Agent successfully published custom memory metrics.

✅ CPU utilization exceeded the configured threshold.

✅ CloudWatch Alarm entered the ALARM state.

✅ Amazon SNS successfully delivered an email notification.

---

## Screenshots

### Architecture

Go to architecture.png

---

### Custom VPC

01-vpc.png

---

### EC2 Instance

02-ec2-running.png

---

### CloudWatch Agent

11-cloudwatchagent-installed-version.png

---

### CloudWatch Dashboard

04-dashboard.png

---

### CPU Stress Test

06-cpu-usage-at-terminal.png

---

### CloudWatch Alarm

08-alarm-triggered.png

---

### Email Notification

10-email-notification.png

---

## Skills Demonstrated

- AWS Networking (VPC)
- EC2 Deployment
- IAM Roles
- Linux Administration
- CloudWatch Monitoring
- CloudWatch Dashboards
- CloudWatch Agent
- CloudWatch Alarms
- Amazon SNS
- Infrastructure Monitoring
- Observability
- Cloud Operations
- Incident Alerting

---

## Learning Outcomes

This project demonstrates the implementation of an end-to-end AWS monitoring solution that includes infrastructure deployment, metric collection, dashboard visualization, automated alerting, and notification workflows commonly used in Cloud Operations and DevOps environments.
