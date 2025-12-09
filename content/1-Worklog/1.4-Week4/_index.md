---
title: "Week 4 Worklog"
date: 2025-10-06T00:00:00Z
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* Learn and apply core IAM concepts: users, groups, roles, policies, and best practices for least privilege.
* Configure account security: enable MFA, set a password policy, and review access keys.
* Practice role-based access and simple role assumption (optional) to understand trust and permissions.
* Audit and record findings for future hardening.

### Tasks to carry out this week
| Day | Task | Start Date | Completion Date | Reference |
| ---- | ----------------- | ------------ | --------------- | ------------------ |
| 2 | Review IAM concepts, create a developers group and 1–2 users assigned to the group. Attach minimal managed policies as needed (avoid AdministratorAccess). Record usernames and applied policies. | 09/29/2025 | 09/30/2025 | https://000002.awsstudygroup.com/vi/ |
| 3 | Create a custom policy and attach it to the group or a role. Test by signing in as the test user or using AWS CLI with that user's credentials. Save the policy JSON and test results. | 09/30/2025 | 10/01/2025 |  |
| 4 | Enable MFA for the created users; set an account password policy (minimum length, complexity). Rotate or delete unused access keys and document the steps. | 10/01/2025 | 10/02/2025 |  |
| 5 | Create an IAM role for EC2 or another service with an appropriate trust policy and assign least-privilege permissions. Launch a test EC2 or simulate to validate the role. (Optional) Set up a cross-account role to try role switching if possible. | 10/02/2025 | 10/03/2025 | https://000002.awsstudygroup.com/vi/2-create-admin-user-and-group/ |
| 6 | Audit and clean up: run IAM Access Analyzer or review Access Advisor, identify overly permissive policies and tighten or remove them. Save JSON policy files and screenshots. Summarize issues and remediation steps. | 10/03/2025 | 10/04/2025 | https://000002.awsstudygroup.com/vi/5-cleanup/ |

### Achievements this week

* IAM structure:
  * Created a developers group and test users with scoped permissions, avoiding broad admin rights.
  * Wrote and applied a custom policy limiting S3 access to a specific bucket and validated it via CLI/Console.

* Account security:
  * Enabled MFA for test users and configured a password policy (length and complexity).
  * Identified and rotated/deleted unused access keys to reduce exposure.

* Roles and delegation:
  * Created a service role with an appropriate trust policy and assigned least-privilege permissions; validated role usage from EC2 or via role assumption.
  * (Optional) Tested a cross-account role to understand trust relationships and role switching.

* Audit & cleanup:
  * Ran IAM Access Analyzer / Access Advisor to find overly permissive policies; tightened or removed risky policies.
  * Saved all policy JSONs, commands executed, and screenshots for the weekly report.

### Conclusion:

This week reinforced secure access management practices: applying least privilege, enforcing MFA and password policies, using roles for service access, and auditing permissions. The actions taken reduce risk and establish repeatable procedures for IAM administration.
