---
title: "Week 2 Worklog"
date: 2024-10-15T00:00:00Z
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---



### Week 2 Objectives:

* Deepen understanding of AWS networking by designing and deploying a VPC with public and private subnets, configuring route tables, attaching an Internet Gateway, and using a NAT Gateway where appropriate; the goal is to comprehend how each component isolates and routes traffic between resources while maintaining security boundaries.
* Improve storage management skills through hands-on practice with advanced S3 features such as versioning and lifecycle rules, as well as EBS snapshots; the objective is to learn how to protect data, manage retention and costs, and recover data when necessary.
* Familiarize with monitoring and logging tools by configuring CloudWatch to collect metrics and create basic alarms, and enabling CloudTrail to record API activity for auditing and troubleshooting purposes.
* Get an introductory experience with Infrastructure as Code (IaC) by authoring and deploying a simple CloudFormation template (or Terraform configuration) to automate creation of a small set of resources; the aim is to understand the workflow of reproducing infrastructure from code rather than manual console steps.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Began the week by studying VPC concepts and then created a new VPC in the AWS Console containing at least one public subnet and one private subnet. Configured an Internet Gateway and attached it to the VPC, then created route tables and associated them with the appropriate subnets to validate the expected routing behavior.                                                                                                   | 09/15/2025 | 09/16/2025      |https://000003.awsstudygroup.com/vi/1-introduce/
| 3   | - Configured a NAT Gateway to allow instances in the private subnet to access the internet for updates and package downloads. Verified connectivity from a private EC2 instance using standard network tools and reviewed route table entries to understand how the NAT device is referenced and used in practice.| 09/16/2025 | 09/18/2025      | <https://000003.awsstudygroup.com/vi/1-introduce/1.4-natgateway/> |
| 4   | Explored advanced S3 capabilities by enabling versioning on a test bucket and creating lifecycle rules to transition older objects to cheaper storage classes or delete them after a retention period. Also created EBS snapshots for a test volume and documented the restore procedure and timings.| 09/17/2025 | 09/19/2025      | <https://000057.awsstudygroup.com/vi/1-introduce/> |
| 5   | Set up CloudWatch to collect EC2 metrics and created a simple dashboard displaying CPU, network, and disk metrics. Configured an alarm to notify on high CPU utilization and enabled CloudTrail at the account level to capture API activity, then examined sample CloudTrail logs to understand event structure.| 09/18/2025 | 09/20/2025      | <https://000004.awsstudygroup.com/vi/> |
| 6   | Wrote a basic CloudFormation template (optionally Terraform) that provisions an EC2 instance with a Security Group and an S3 bucket. Deployed the stack to observe resource creation flow, then deleted the stack to practice safe teardown and observe how IaC handles lifecycle operations.| 09/19/2025 | 09/21/2025      | <https://000004.awsstudygroup.com/vi/5-amazonec2basic/> |


### Week 2 Achievements:

* Successfully designed and deployed a simple VPC with public and private subnets, attached an Internet Gateway, and created route tables to direct traffic appropriately; this clarified how subnet separation supports security and operational patterns.
* Configured Security Group rules for EC2 instances to permit SSH and HTTP while identifying overly permissive settings to avoid, reinforcing secure defaults for access control.
* Enabled S3 versioning and created lifecycle policies for a test bucket, demonstrating how to reduce storage costs and protect against accidental deletions through automated retention policies.
* Created EBS snapshots for a test volume and executed a restore to validate the backup and recovery process, documenting the steps and time required for recovery.
* Implemented a CloudWatch dashboard and alarm for EC2 metrics and enabled CloudTrail to capture API calls, giving basic observability and auditability for the account.
* Authored and deployed a simple CloudFormation template to automate resource creation and practiced stack deletion to observe clean teardown behavior, gaining practical IaC experience.

