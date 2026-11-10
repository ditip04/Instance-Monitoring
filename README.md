Project : Instance Monitoring

Overview -
Client launched a Windows Server 2012 EC2 instance on AWS to support internal operations. Once the instance was deployed, the next critical phase was establishing a robust monitoring and alerting framework to ensure system reliability, performance visibility, and proactive issue detection. This project focused on implementing AWS CloudWatch monitoring, configuring automated alarms, and establishing secure administrative access through IAM.

Objectives -
The monitoring and support teams were tasked with achieving the following:
•	Observe and analyse CPU utilization metrics for the EC2 instance.
•	Configure a CloudWatch alarm that triggers an email notification to HCMonitor@client.com when CPU utilization drops below 3%, occurring three consecutive times within a five minute period.
•	Create an IAM group named Administrator Group with full administrative privileges.
•	Provision a new IAM user requiring administrator access and add the user to the Administrator Group.

Implementation Details -
1. Monitoring EC2 CPU Utilization -
The team accessed AWS CloudWatch through the AWS Management Console to begin monitoring the EC2 instance. Key actions included:
•	Navigating to EC2 → Monitoring to view real time and historical CPU utilization graphs.
•	Analysing CPU performance trends to ensure the instance was operating within expected thresholds.
•	Using CloudWatch metrics to support debugging and performance tuning.
This provided continuous visibility into system behaviour and helped identify potential performance bottlenecks.
2. Configuring CloudWatch Alarm -
To ensure proactive monitoring, a CloudWatch alarm was created with the following configuration:
•	Metric: CPUUtilization
•	Threshold: < 3%
•	Evaluation Periods: 3
•	Period Duration: 5 minutes
•	Action: Send notification to HCMonitor@client.com via Amazon SNS
This alarm ensures the support team is immediately notified if the server becomes underutilized, which may indicate service degradation, misconfiguration, or application failure.
3. IAM Group Creation – Administrator Group -
To enforce secure and structured access management:
•	An IAM group named Administrator Group was created.
•	The AdministratorAccess AWS managed policy was attached to the group, granting full administrative privileges across the AWS account.
•	This group serves as the central access control point for all users requiring elevated permissions.
4. IAM User Provisioning -
A new IAM user was created for an employee requiring administrative access:
•	The user was provisioned with programmatic and console access.
•	The user was added to the Administrator Group, inheriting full administrative permissions.
•	Security best practices were applied, including enforcing MFA and secure password policies.
This ensured the employee could perform administrative tasks while maintaining compliance with AWS security standards.

Outcome -
The project successfully established a complete monitoring and access control framework for the EC2 instance. Client now benefits from:
•	Real time visibility into server performance.
•	Automated alerting for abnormal CPU behaviour.
•	Structured and secure IAM access management for administrative users.
•	Improved operational reliability through proactive monitoring and controlled access.
This monitoring setup forms a foundational component of Client’ cloud infrastructure strategy, supporting stability, security, and operational efficiency.
