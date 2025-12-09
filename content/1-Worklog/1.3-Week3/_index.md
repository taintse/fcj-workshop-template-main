---
title: "Week 3 Worklog"
date: 2024-10-15T00:00:00Z
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Practice a small, focused set of tasks: one EC2 instance, one S3 bucket, and basic CloudWatch checks.  
* Complete each step clearly and record commands and results for reproducibility.

### Tasks to carry out this week:
| Day | Task                                                                                                      | Start Date | Completion Date | Reference |
| --- | --------------------------------------------------------------------------------------------------------- | ---------- | --------------- | --------- |
| 2   | Launch an EC2 (t2.micro), select a key pair, set a Security Group that only allows SSH from your IP; record Public IP and Instance ID. | 09/22/2025 | 09/22/2025      |           |
| 3   | Update the OS and install git/curl; optionally create & mount a small EBS volume and verify read/write access. | 09/23/2025 | 09/23/2025      |           |
| 4   | Create a test S3 bucket, upload files via Console and CLI; optionally enable versioning and perform an object restore. | 09/24/2025 | 09/25/2025      | https://000057.awsstudygroup.com/vi/2-prerequiste/2.1-creates3bucket/ |
| 5   | Configure CloudWatch: view EC2 metrics, create a simple CPU alarm and (optional) SNS notification; check Log Group. | 09/25/2025 | 09/26/2025      | https://000004.awsstudygroup.com/vi/1-introduce/ |
| 6   | Weekly wrap-up: verify tags, delete unnecessary resources, capture screenshots of key steps, and document issues and fixes. | 09/26/2025 | 09/26/2025      |           |

### Achievements for Week 3:

* EC2 and access:
  * Launched an EC2 instance (t2.micro) and confirmed it is running; able to SSH into the instance using the created key pair (Public IP and Instance ID recorded).
  * Created, formatted, and mounted an EBS volume to the instance successfully; verified read/write permissions and documented the mount commands and path.

* S3:
  * Created a test S3 bucket and uploaded files using both the Console and AWS CLI to validate the workflow.
  * Enabled bucket versioning and practiced overwriting an object then restoring a previous version — restore completed successfully.

* CloudWatch & Logging:
  * Configured CloudWatch to collect EC2 metrics (CPU, Network, Disk) and created at least one simple CPU alarm.
  * Created a Log Group and sent logs from the EC2 instance; configured SNS and verified notifications to validate the alerting flow.

* Resource management & cost control:
  * Reviewed created resources and removed unnecessary items (terminated EC2, detached/deleted EBS, removed temporary S3 objects) to avoid incurring charges.
  * Recorded commands and configurations, and captured screenshots of key steps for the weekly report.

* Conclusion:
  * Completed the core hands-on tasks: EC2 is accessible via SSH, EBS (if used) mounted successfully, S3 upload/restore tested, CloudWatch alarms/logs and notifications verified, and extraneous resources cleaned up.
