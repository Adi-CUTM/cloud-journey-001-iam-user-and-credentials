# ☁️ Project 001 — AWS IAM User and Credentials Management

\<p align="center">   \<strong>AWS CLOUD ENGINEERING | IDENTITY & ACCESS MANAGEMENT | CLOUD SECURITY\</strong> \</p>

\<p align="center">   \<img src="[https://img.shields.io/badge/AWS-IAM-orange?style=for-the-badge&logo=amazonaws](https://img.shields.io/badge/AWS-IAM-orange?style=for-the-badge\&logo=amazonaws)" />   \<img src="[https://img.shields.io/badge/Project-001-blue?style=for-the-badge](https://img.shields.io/badge/Project-001-blue?style=for-the-badge)" />   \<img src="[https://img.shields.io/badge/Level-Beginner-green?style=for-the-badge](https://img.shields.io/badge/Level-Beginner-green?style=for-the-badge)" />   \<img src="[https://img.shields.io/badge/Status-Completed-success?style=for-the-badge](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)" /> \</p>

\<p align="center">   \<em>Learn by Building. Secure by Design. Improve with Every Project.\</em> \</p>

---

## 🧭 Project Navigation

| Section                                        | Description                 |
| ---------------------------------------------- | --------------------------- |
| [📌 Overview](#-project-overview)              | Introduction to the project |
| [🎯 Objectives](#-project-objectives)          | Learning goals              |
| [🏗️ Environment](#️-aws-environment)          | Lab configuration           |
| [📚 Concepts](#-concepts-learned)              | AWS IAM fundamentals        |
| [⚙️ Implementation](#️-implementation)         | Practical implementation    |
| [📸 Screenshots](#-implementation-screenshots) | Visual project evidence     |
| [📜 IAM Policies](#-iam-policies)              | Policy documentation        |
| [🔐 Security](#-security-observations)         | Security observations       |
| [🎤 Interview Prep](#-interview-preparation)   | Interview questions         |
| [💡 Learnings](#-lessons-learned)              | Key takeaways               |

---

## 📌 Project Overview

This project is part of my **Cloud Journey**, where I am transitioning from cybersecurity foundations toward practical AWS Cloud Engineering and Cloud Security.

The objective was to understand how AWS Identity and Access Management (IAM) controls authentication and authorization within an AWS environment.

Through this hands-on project, I created an IAM user, configured group-based permissions, enabled Multi-Factor Authentication (MFA), explored IAM policies, and investigated access-denied scenarios.

The project emphasizes secure identity management and the principle of least privilege.

## 🎯 Project Objectives

- Understand AWS Identity and Access Management.
- Differentiate between the AWS root user and IAM users.
- Create and configure an IAM user.
- Understand console authentication.
- Create an IAM group and assign permissions.
- Configure Multi-Factor Authentication.
- Explore AWS-managed and customer-managed IAM policies.
- Understand authorization and access-denied errors.
- Explore the IAM Policy Simulator.
- Apply the principle of least privilege.
- Document practical security observations.

## 🏗️ AWS Environment

| Component             | Configuration                  |
| --------------------- | ------------------------------ |
| Cloud Provider        | Amazon Web Services            |
| AWS Service           | Identity and Access Management |
| AWS Region            | Global service                 |
| Account Type          | AWS Free Tier account          |
| IAM User              | `cloud-journey-lab-user`       |
| IAM Group             | `cloud-journey-lab-group`      |
| Authentication        | Console password + MFA         |
| Permission Management | Group-based                    |
| AWS-managed Policy    | `IAMUserChangePassword`        |
| Project Difficulty    | Beginner                       |
| Project Status        | Completed                      |

## 🧰 Tools and Technologies

- **AWS IAM:** Identity and access management.
- **AWS Management Console:** Managing AWS services.
- **IAM Policy Simulator:** Exploring IAM authorization decisions.
- **JSON:** Understanding IAM policy structure.
- **Git and GitHub:** Version control and project documentation.

## 📚 Concepts Learned

### 1. AWS Root User

The root user is the original identity associated with an AWS account.

It has extensive account-level privileges and should not be used for everyday administrative activities.

**Security practice:** Protect the root user with MFA and avoid routine root-user access.

### 2. IAM User

An IAM user is an identity within an AWS account that can receive permissions and authentication credentials.

For this project, I created:

`cloud-journey-lab-user`

IAM users are useful for understanding AWS identity management and legacy workloads. For human workforce access, AWS generally recommends federation and IAM Identity Center where appropriate.

### 3. IAM Groups

IAM groups allow administrators to manage permissions for multiple IAM users collectively.

For this project, I created:

`cloud-journey-lab-group`

The IAM user was added to this group to demonstrate centralized, group-based permission management.

### 4. IAM Policies

IAM policies are JSON documents that define which AWS actions are allowed or denied on specified resources.

This project explored:

- AWS-managed policies.
- Customer-managed policy concepts.
- Identity-based permissions.
- Resource specifications.
- Explicit and implicit denial.

The project includes a self-inspection policy example in the `policies/` directory.

### 5. Multi-Factor Authentication (MFA)

MFA adds an additional authentication factor beyond the password.

It helps protect an account even if its password becomes compromised.

I configured MFA for the newly created IAM user.

### 6. Principle of Least Privilege

The principle of least privilege means granting only the permissions required to perform a specific task.

This reduces unnecessary access and limits the potential impact of compromised credentials.

### 7. Authentication vs Authorization

| Authentication            | Authorization                |
| ------------------------- | ---------------------------- |
| Verifies identity         | Determines permitted actions |
| Example: Password and MFA | Example: IAM policies        |
| Answers: Who are you?     | Answers: What can you do?    |

---

## ⚙️ Implementation Summary

The following activities were completed during the hands-on lab.

| Task | Implementation                              | Status    |
| ---- | ------------------------------------------- | --------- |
| 01   | Reviewed root-user security                 | Completed |
| 02   | Created IAM permissions group               | Completed |
| 03   | Created IAM user                            | Completed |
| 04   | Assigned user to IAM group                  | Completed |
| 05   | Configured console access                   | Completed |
| 06   | Configured MFA                              | Completed |
| 07   | Logged in using the IAM user                | Completed |
| 08   | Observed IAM access-denied scenarios        | Completed |
| 09   | Explored IAM policies and policy simulation | Explored  |
| 10   | Documented policy example and observations  | Completed |

### Important Observation: Access Denied

After logging in with the newly created IAM user, several IAM dashboard features displayed `Access Denied`.

Examples included:

- `iam:GetAccountSummary`
- `iam:ListAccountAliases`
- `iam:ListMFADevices`
- `iam:ListAccessKeys`

This occurred because the IAM user's assigned permissions did not authorize those actions.

**This is not necessarily a configuration failure.**

It demonstrates how AWS authorization works: an authenticated identity does not automatically receive permission to access every AWS service or perform every action.

For this beginner lab, I retained restricted permissions rather than granting unnecessary administrative access just to remove dashboard warnings.

### IAM Policy Simulator Observation

I explored the IAM Policy Simulator to understand policy evaluation.

During testing, the simulator displayed permission-related errors because the lab identity did not have all the permissions required by the simulator interface and its supporting operations.

The simulation was therefore treated as an exploration exercise rather than a fully validated authorization test.

---

## 📸 Implementation Screenshots

The following screenshots document the actual implementation process.

### 01. Root User Security Review



Reviewed the root account's security configuration before creating the IAM identity.

### 02. IAM Group Created



Created the `cloud-journey-lab-group` to demonstrate group-based permission management.

### 03. IAM User Review and Create



Reviewed the IAM user's configuration before creation.

### 04. IAM User Creation Successful



Successfully created the IAM user and configured the required group membership.

### 05. MFA Enabled



Configured Multi-Factor Authentication to strengthen the IAM user's authentication security.

### 06. First IAM User Login



Successfully logged in using the newly created IAM user.

---

## 📜 IAM Policies

This directory contains the policy documentation associated with this project.

**Policy artifact:**

`policies/IAM-Self-Inspection-ReadOnly.json`

The policy example demonstrates selected IAM self-inspection actions, including:

- `iam:GetUser`
- `iam:ListMFADevices`
- `iam:ListAccessKeys`

The intention is to understand how IAM policies define permitted actions and resource scope.

**Important:** This policy is a learning artifact, not a blanket recommendation for deployment. Review and validate its JSON syntax, resource ARN and permissions before using it in an AWS account. Its presence in this repository does not establish that all listed actions were successfully validated or attached to the IAM user.

## 🔐 Security Observations

Throughout this project, the following security practices were emphasized:

- Protect the AWS root account.
- Enable MFA for privileged identities.
- Avoid unnecessary administrative permissions.
- Use IAM groups for centralized permission management.
- Follow least privilege.
- Avoid unnecessary long-term access keys.
- Never commit credentials to GitHub.
- Never expose passwords, secret keys or MFA codes.
- Prefer temporary credentials and federation for human access where appropriate.
- Regularly review unused identities and permissions.

## 💡 Lessons Learned

1. AWS IAM is responsible for managing identities and access permissions.
2. Root users and IAM users serve different purposes.
3. IAM groups simplify permission management.
4. Policies define what an identity can and cannot do.
5. MFA adds another layer of authentication security.
6. Successful authentication does not guarantee authorization.
7. Access Denied errors can be expected when permissions are restricted.
8. Least privilege is an essential cloud security principle.
9. The IAM Policy Simulator requires appropriate permissions to perform certain operations.
10. Security should not be weakened merely to remove dashboard warnings.

## 🎤 Interview Preparation

**1. What is AWS IAM?**

AWS IAM is a service that manages identities and controls access to AWS resources.

**2. What is the difference between an IAM user and an IAM group?**

An IAM user represents an individual identity, while an IAM group organizes multiple users for shared permission management.

**3. What is MFA?**

Multi-Factor Authentication adds an additional authentication factor to strengthen account security.

**4. What is the principle of least privilege?**

Granting only the minimum permissions necessary to perform a task.

**5. What is an IAM policy?**

A JSON document defining permissions for AWS identities or resources.

**6. What is the difference between authentication and authorization?**

Authentication verifies identity, while authorization determines permitted actions.

**7. Why might an authenticated IAM user receive Access Denied?**

Because the identity does not have an applicable permission allowing the requested action.

**8. What is the difference between AWS-managed and customer-managed policies?**

AWS-managed policies are maintained by AWS, whereas customer-managed policies are created and maintained by customers.

**9. Why should AWS access keys not be committed to GitHub?**

Because exposed credentials can allow unauthorized access to AWS resources.

**10. Why is federation recommended for workforce access?**

Federation enables centralized identity management and can provide temporary credentials without requiring individual long-term IAM user credentials.

## 💰 Cost Considerations

AWS IAM's core identity and access management functionality is generally available without an additional charge.

However, other AWS services and resources used in future projects may incur charges.

Cost-conscious practices:

- Review the AWS Billing Dashboard.
- Check AWS Free Tier usage and applicable Free Tier offers.
- Review AWS Pricing pages before deploying resources.
- Configure billing alerts where appropriate.
- Remove unnecessary test resources.

Never assume that a resource is free simply because the account has Free Tier eligibility.

## 🧹 Cleanup and Account Security

Before considering this project closed:

- Review the IAM user's group membership.
- Confirm MFA remains enabled.
- Review attached permissions.
- Remove unnecessary credentials.
- Do not delete the IAM user if it is still required for your ongoing learning journey.
- Keep the root account protected.

## 📚 Official AWS References

- [AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
- [IAM Security Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
- [IAM Policies and Permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)
- [IAM Policy Simulator](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html)
- [AWS Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/)

---

## 👨‍💻 Author

**Cloud Journey — AWS Cloud Engineering & Cloud Security**

This project represents my first practical AWS identity-management implementation as I transition from cybersecurity toward cloud engineering and cloud security.

---

\<p align="center">
&#x20; ⭐ \<strong>Learn by Building. Secure by Design. Improve with Every Project.\</strong>
\</p>

\<p align="center">
&#x20; \<sub>Project 001 | AWS IAM User and Credentials Management | Cloud Journey\</sub>
\</p>
