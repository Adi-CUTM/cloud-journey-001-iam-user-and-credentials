# Project 001: AWS IAM User and Credentials Management

<p align="center">
  <strong>AWS Cloud Engineering | Identity and Access Management | Cloud Security</strong>
</p>

## 📌 Project Overview

This project is part of my **Cloud Journey**, where I am developing practical skills in AWS Cloud Engineering and Cloud Security.

The objective of this project is to understand AWS Identity and Access Management (IAM), explore different authentication methods, and learn how identities and credentials are managed securely within an AWS environment.

Through this hands-on lab, I will explore IAM users, authentication credentials, permissions, and essential security practices.

## 🎯 Project Objectives

- Understand the purpose of AWS IAM.
- Understand the difference between the AWS account root user and an IAM user.
- Learn how to create and configure an IAM user.
- Understand console access and programmatic access.
- Explore IAM policies and permissions.
- Understand the role of Multi-Factor Authentication (MFA).
- Learn secure credential management practices.
- Apply the principle of least privilege.

## 🏗️ AWS Environment

| Component | Details |
|---|---|
| Cloud Provider | Amazon Web Services (AWS) |
| AWS Service | Identity and Access Management (IAM) |
| Project Type | Hands-on Lab |
| Difficulty | Beginner |
| Primary Focus | Identity and Credential Management |
| Account Type | AWS Free Tier account |
| Status | In Progress |

## 🧰 AWS Services and Tools

- **AWS IAM:** Identity and access management.
- **AWS Management Console:** Web-based interface for managing AWS services.
- **GitHub:** Project documentation and version control.

## 📖 Concepts Covered

### 1. AWS Root User

The root user is the original identity created when an AWS account is registered. It has full access to the account and should be protected carefully.

### 2. IAM User

An IAM user is an identity within an AWS account that can be assigned specific permissions.

IAM users are useful to understand for this lab and for certain legacy or specialized use cases. For workforce access, AWS generally recommends IAM Identity Center or federated access where appropriate.

### 3. Authentication Credentials

This project explores the following credential types:

- Console password
- Access Key ID
- Secret Access Key
- Multi-Factor Authentication (MFA)

**Security note:** Access keys will not be created unless required for a specific learning objective. Actual credentials will never be included in this repository.

### 4. IAM Policies

IAM policies define what actions an identity can perform and which AWS resources it can access.

### 5. Principle of Least Privilege

Users and identities should receive only the permissions necessary to perform their intended tasks.

## 🔨 Implementation Plan

The project will be completed in the following stages:

- [ ] Review AWS root user security.
- [ ] Understand IAM users and their purpose.
- [ ] Create a test IAM user.
- [ ] Configure appropriate console access, if required.
- [ ] Explore IAM policies and permissions.
- [ ] Configure MFA where applicable.
- [ ] Understand programmatic credentials and access key security.
- [ ] Validate the configured access.
- [ ] Document observations and lessons learned.
- [ ] Review and clean up lab resources.

## 🔐 Security Best Practices

Throughout this project, the following security practices will be followed:

- Protect the root user with MFA.
- Avoid using the root user for everyday administration.
- Follow the principle of least privilege.
- Avoid unnecessary long-term access keys.
- Never share passwords or secret credentials.
- Never upload AWS credentials to GitHub.
- Review IAM permissions regularly.
- Remove unused identities and credentials.
- Prefer temporary credentials and recommended federation methods where appropriate.

## 🧪 Validation and Testing

The following checks will be documented after implementation:

- Verify that the IAM identity has been created successfully.
- Verify the configured authentication method.
- Confirm that permissions behave as expected.
- Test that unauthorized actions are denied.
- Confirm that MFA works, if configured.

## 📸 Screenshots

Sanitized screenshots will be added here to demonstrate the implementation.

Screenshots must not expose account-sensitive information, passwords, access keys, secret keys, MFA codes, or other confidential details.

## 📂 Repository Structure

```text
cloud-journey-001-iam-user-and-credentials/
│
├── README.md
│
├── screenshots/
│   └── .gitkeep
│
├── policies/
│   └── .gitkeep
│
└── lessons-learned.md
```

## 💡 Key Learnings

This section will be updated after completing the hands-on implementation.

Topics will include:

- Differences between root users and IAM users.
- Understanding AWS authentication mechanisms.
- IAM permissions and policies.
- Credential security.
- MFA and account protection.
- Practical application of least privilege.

## 🎤 Interview Preparation

Some questions explored through this project:

1. What is AWS IAM?
2. What is the difference between an AWS root user and an IAM user?
3. What is an IAM policy?
4. What is the principle of least privilege?
5. What is the difference between console access and programmatic access?
6. What are Access Key IDs and Secret Access Keys?
7. Why should access keys not be shared or committed to GitHub?
8. What is MFA, and why is it important?
9. What are temporary credentials?
10. Why does AWS recommend alternatives to long-lived IAM user credentials for human access?

## 💰 Cost Considerations

AWS IAM does not have an additional charge for its core identity and access management features. However, any other AWS services used during this or future labs may incur charges.

All resources and billing implications will be reviewed before deployment.

## 🧹 Cleanup

After completing the lab:

- Review the IAM user and attached permissions.
- Remove unnecessary test identities.
- Delete unused credentials.
- Ensure no unnecessary resources remain.
- Maintain secure root account settings.

## 📚 References

- [AWS Identity and Access Management (IAM)](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
- [IAM Security Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
- [AWS Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/)

## 👨‍💻 Author

**Cloud Journey — AWS Cloud Engineering and Cloud Security**

This project is part of my ongoing journey from cybersecurity foundations toward practical AWS Cloud Engineering and Cloud Security skills.

---

⭐ *Learn by building. Secure by design. Improve with every project.*