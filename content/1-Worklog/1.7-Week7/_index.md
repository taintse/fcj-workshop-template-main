---
title: "Week 7 Worklog"
date: 2024-10-15T00:00:00Z
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---



### Week 7 Objectives:

* Learn about Amazon Cognito - user identity and authentication management service
* Practice creating User Pools and configuring authentication
* Learn about Amazon Location Service - geolocation and mapping service
* Integrate Cognito with applications and Location Service

### Tasks to carry out this week:
| Day | Task | Start Date | Completion Date | Reference |
| ---- | --------- | ------------ | --------------- | ------------------ |
| 2 | Learn Cognito basics: User Pools vs Identity Pools, authentication flow, and use cases. Create a simple User Pool with password policy. | 26/10/2025 | 27/10/2025 | https://docs.aws.amazon.com/cognito/latest/developerguide/user-pools.html |
| 3 | Configure Cognito User Pool: add users, set up email verification, multi-factor authentication (MFA), and password recovery. | 27/10/2025 | 28/10/2025 | https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-lambda-custom-message.html |
| 4 | Learn Amazon Location Service: create a map resource, use place search, and calculate routes. Test basic APIs. | 28/10/2025 | 29/10/2025 | https://docs.aws.amazon.com/location/latest/developerguide/what-is.html |
| 5 | Integrate Cognito with Location Service: configure IAM roles to allow Cognito users to access Location Service resources. Test end-to-end workflow. | 29/10/2025 | 30/10/2025 | https://docs.aws.amazon.com/cognito/latest/developerguide/iam-roles.html |
| 6 | Wrap-up: review security configuration for both Cognito and Location Service, check CloudWatch logs, and clean up resources. Document important steps. | 30/10/2025 | 1/11/2025 | Personal notes |

### Week's Achievements:

* Cognito User Pool:
  * Successfully created a User Pool with security configurations
  * Added users and configured authentication (email verification, MFA)
  * Understood authentication flow and JWT tokens

* Cognito Identity Pool:
  * Learned how to grant temporary credentials to unauthenticated users
  * Configured IAM roles for Cognito identities

* Location Service:
  * Created map resources and tested APIs
  * Used place search and route calculation
  * Understood pricing model

* Integration:
  * Successfully integrated Cognito authentication with Location Service resources
  * Configured IAM policies for user access
  * Verified end-to-end workflow

### Conclusion:

This week covered AWS identity management and geolocation services. Combining Cognito with Location Service enables location-aware applications with secure user authentication.
| 2   | - Get acquainted with FCJ members <br> - Read and take note of internship unit rules and regulations                                                                                                   | 08/11/2025 | 08/11/2025      |
| 3   | - Learn about AWS and its types of services <br>&emsp; + Compute <br>&emsp; + Storage <br>&emsp; + Networking <br>&emsp; + Database <br>&emsp; + ... <br>                                              | 08/12/2025 | 08/12/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Create AWS Free Tier account <br> - Learn about AWS Console & AWS CLI <br> - **Practice:** <br>&emsp; + Create AWS account <br>&emsp; + Install & configure AWS CLI <br> &emsp; + How to use AWS CLI | 08/13/2025 | 08/13/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Learn basic EC2: <br>&emsp; + Instance types <br>&emsp; + AMI <br>&emsp; + EBS <br>&emsp; + ... <br> - SSH connection methods to EC2 <br> - Learn about Elastic IP   <br>                            | 08/14/2025 | 08/15/2025      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - **Practice:** <br>&emsp; + Launch an EC2 instance <br>&emsp; + Connect via SSH <br>&emsp; + Attach an EBS volume                                                                                     | 08/15/2025 | 08/15/2025      | <https://cloudjourney.awsstudygroup.com/> |


### Week 7 Achievements:

* Understood what AWS is and mastered the basic service groups: 
  * Compute
  * Storage
  * Networking 
  * Database
  * ...

* Successfully created and configured an AWS Free Tier account.

* Became familiar with the AWS Management Console and learned how to find, access, and use services via the web interface.

* Installed and configured AWS CLI on the computer, including:
  * Access Key
  * Secret Key
  * Default Region
  * ...

* Used AWS CLI to perform basic operations such as:

  * Check account & configuration information
  * Retrieve the list of regions
  * View EC2 service
  * Create and manage key pairs
  * Check information about running services
  * ...

* Acquired the ability to connect between the web interface and CLI to manage AWS resources in parallel.
* ...

