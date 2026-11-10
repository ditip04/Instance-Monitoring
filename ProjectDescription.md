# AWS EC2 Server Monitoring and IAM Access Management

## Project Overview

This project demonstrates the implementation of server monitoring, automated alerting, and identity and access management (IAM) using Amazon Web Services (AWS).

A client deployed a Windows Server 2012 EC2 instance to support its internal operations. To maintain server performance, reliability, and security, a monitoring and access-control framework was established using **Amazon CloudWatch, Amazon SNS, and AWS IAM**.

The project focuses on monitoring EC2 CPU utilisation, configuring automated email alerts, and managing administrative permissions through IAM groups and users.

## Objectives

- Monitor and analyse CPU utilisation metrics for an EC2 instance.
- Configure a CloudWatch alarm to detect CPU utilisation below 3% for three consecutive five-minute evaluation periods.
- Send automated email notifications through Amazon SNS.
- Create an IAM group named `Administrator Group` with full administrative permissions.
- Create an IAM user and assign administrative access through group membership.
- Apply security best practices for administrative access.

## AWS Services Used

| AWS Service | Purpose |
|---|---|
| Amazon EC2 | Hosts the Windows Server 2012 instance. |
| Amazon CloudWatch | Monitors EC2 CPU utilisation metrics and performance. |
| Amazon SNS | Delivers automated email notifications. |
| AWS IAM | Manages users, groups, and permissions. |

## Implementation

### 1. EC2 Instance Monitoring Using Amazon CloudWatch

- Accessed the AWS Management Console and navigated to the EC2 service.
- Selected the deployed Windows Server 2012 instance.
- Opened the **Monitoring** tab to view CPU utilisation metrics.
- Analysed real-time and historical CPU performance graphs.
- Used CloudWatch metrics to monitor resource utilisation and identify potential performance issues.

**Outcome:** Established visibility into EC2 instance performance to support proactive monitoring and troubleshooting.

### 2. CloudWatch Alarm Configuration

Created a CloudWatch alarm to monitor CPU utilisation and notify the support team when the configured threshold was breached.

**Alarm Configuration:**

| Parameter | Configuration |
|---|---|
| Metric | `CPUUtilization` |
| Condition | Less than 3% |
| Evaluation Periods | 3 |
| Period | 5 minutes |
| Notification Service | Amazon SNS |
| Notification Email | `HCMonitor@client.com` |

**Implementation Steps:**

1. Navigated to Amazon CloudWatch.
2. Selected **Alarms → Create Alarm**.
3. Selected the EC2 `CPUUtilization` metric.
4. Configured the threshold to trigger when CPU utilisation fell below 3%.
5. Set three evaluation periods of five minutes each.
6. Configured an Amazon SNS notification to send email alerts to `HCMonitor@client.com`.
7. Completed the alarm configuration.

**Outcome:** Implemented automated email alerting to notify the monitoring team of sustained low CPU utilisation, helping identify potential application or server issues.

### 3. IAM Group Creation – Administrator Group

Created a centralised IAM group to manage administrative permissions.

**Implementation Steps:**

1. Navigated to the AWS IAM service.
2. Selected **User Groups → Create Group**.
3. Created a group named `Administrator Group`.
4. Attached the AWS managed policy `AdministratorAccess`.
5. Verified that the group had the required administrative permissions.

**Outcome:** Established centralised permission management for users requiring administrative access.

### 4. IAM User Provisioning and Access Management

Created a new IAM user for an employee requiring administrative privileges.

**Implementation Steps:**

1. Navigated to **IAM → Users → Create User**.
2. Created a new employee IAM user.
3. Configured AWS Management Console access and programmatic access as required.
4. Added the user to the `Administrator Group`.
5. Verified that the user inherited administrative permissions through group membership.
6. Applied security measures, including MFA and appropriate password policies.

**Outcome:** Successfully provisioned an administrative IAM user using group-based permission management.

## Project Outcomes

The project successfully established an EC2 monitoring and IAM access-management framework for the client.

Key achievements include:

- **Server Monitoring:** Gained visibility into EC2 CPU utilisation through Amazon CloudWatch.
- **Automated Alerting:** Configured threshold-based email notifications using CloudWatch and Amazon SNS.
- **Centralised Access Management:** Created an IAM group with administrative permissions.
- **User Provisioning:** Created and assigned an IAM user to the appropriate administrative group.
- **Security:** Incorporated MFA and password security practices into the access-management approach.
- **Operational Reliability:** Improved infrastructure monitoring and supported proactive issue detection.

## Key Skills Demonstrated

- Amazon EC2 Instance Monitoring
- Amazon CloudWatch Metrics and Alarms
- Amazon SNS Notifications
- AWS Identity and Access Management (IAM)
- IAM Users, Groups and Policies
- AWS Managed Policies
- Cloud Infrastructure Monitoring
- Access Control and Security Management
- Troubleshooting and Operational Support

## Conclusion

This project provided practical experience in AWS infrastructure monitoring, automated alert configuration, and identity and access management. It demonstrates how AWS CloudWatch, SNS, and IAM can be used together to improve infrastructure visibility, support operational reliability, and manage administrative access within a cloud environment.

---
**Technology Stack:** AWS | Amazon EC2 | Amazon CloudWatch | Amazon SNS | AWS IAM
