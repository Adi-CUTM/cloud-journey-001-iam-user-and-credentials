# 🔐 IAM Policies — Project 001

## Overview

This directory contains custom AWS IAM policy examples developed during Project 001 of my Cloud Journey.

The objective is to understand how JSON-based IAM policies control access to AWS resources and how the principle of least privilege can be implemented.

## Policy Inventory

| Policy | Purpose | Permission Type |
|---|---|---|
| IAM-Self-Inspection-ReadOnly.json | Allows an IAM user to view its own user details, MFA devices and access-key metadata | Read-only |

## 1. IAM Self-Inspection Read-Only

**File:** `IAM-Self-Inspection-ReadOnly.json`

### Purpose

This policy allows an IAM user to inspect selected information about its own identity.

### Allowed Actions

- `iam:GetUser` — Retrieve information about the current IAM user.
- `iam:ListMFADevices` — View MFA devices associated with the current IAM user.
- `iam:ListAccessKeys` — View access-key metadata associated with the current IAM user.

### Resource Restriction

The policy uses:

`arn:aws:iam::*:user/${aws:username}`

This restricts the permitted operations to the IAM user represented by the current username.

### Security Considerations

- Does not grant administrator access.
- Does not permit modification of IAM users.
- Does not permit creation or deletion of access keys.
- Does not allow management of other IAM users.
- Does not allow MFA enrollment or deactivation.

## Testing Strategy

The policy should first be reviewed and tested using the AWS IAM Policy Simulator in Custom Policy mode.

Expected results:

| IAM Action | Expected Result |
|---|---|
| `iam:GetUser` | Allowed |
| `iam:ListMFADevices` | Allowed |
| `iam:ListAccessKeys` | Allowed |
| `iam:CreateUser` | Implicitly denied |
| `iam:DeleteUser` | Implicitly denied |
| `iam:CreateAccessKey` | Implicitly denied |
| `iam:DeleteAccessKey` | Implicitly denied |

These are expected results when evaluating this policy by itself, without other policies, permissions boundaries, SCPs or explicit denies affecting the request.

## Important Notes

This is an educational policy example. Test it before attaching it to an IAM group.

An explicit deny in another applicable policy can override an allow statement.

Never commit passwords, access keys, secret keys, MFA recovery codes or other credentials to this repository.

## Learning Outcome

This exercise demonstrates:

- IAM JSON policy structure.
- Allow effects.
- IAM actions.
- Resource-level permission restrictions.
- AWS policy variables.
- Least-privilege permission design.
- Implicit deny.

**Project:** 001 — AWS IAM User and Credentials Management

**Learning Focus:** AWS IAM Policy Management and Identity Security.