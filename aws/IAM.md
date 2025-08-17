# AWS IAM (Identity and Access Management) - Elite Notes

AWS IAM is the **foundation of secure cloud operations**, controlling who can do what in your AWS account. Mastering IAM is critical for scalable, compliant, and auditable cloud architecture.

## Core Concepts

- **Root User**: Created automatically with your AWS account; has unrestricted access. Enterprise best practice: enable MFA, store credentials offline, use only for billing or recovery.
- **IAM Users**: Individual identities for humans or applications; assign least privilege permissions.
- **Groups**: Logical collections of IAM users; assign policies at the group level for maintainability.
- **Roles**: Assignable identities without long-term credentials; use for cross-account access, EC2 instances, Lambda, or federated users.

## Permissions

Permissions define **what actions a user or role can perform on which resources**. They are implemented via policies and evaluated whenever a request is made.
Example permission in JSON:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:ListBucket",
      "Resource": "arn:aws:s3:::example-bucket"
    }
  ]
}
```

## Policies

Policies are **JSON documents that define permissions** for users, groups, and roles.

- **Types of Policies**:

  1. Managed Policies: Reusable policies provided by AWS or created by your organization.
  2. Inline Policies: Directly attached to a single user, group, or role.

- Enterprise Insight: Always prefer managed policies for consistency, version control, and auditing.
  Example of an inline policy in JSON:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": "ec2:TerminateInstances",
      "Resource": "*"
    }
  ]
}
```

## Access Methods

IAM identities can interact with AWS via:

- AWS Management Console: Browser-based GUI for users.
- AWS CLI: Terminal-based commands, ideal for automation and scripting.
- AWS SDKs: Programmatic access via Python (boto3), Java, Node.js, etc.
- Federated Access / SSO: Integration with corporate identity providers.

## AWS CLI Setup on macOS

1. Install AWS CLI:

```bash
brew install awscli
```

2. Configure credentials:

```bash
aws configure
```

Enter:

- AWS Access Key ID
- AWS Secret Access Key
- Default Region
- Default Output Format

3. Verify IAM access:

```bash
aws iam list-users
```

## CloudShell

- Browser-based shell pre-configured with IAM credentials.
- No installation required; ideal for quick commands and scripting.
- Example: List IAM users

```bash
aws iam list-users
```

## Enterprise-Level Best Practices

1. Root User Security: Enable MFA, store credentials offline.
2. Least Privilege Principle: Assign only required permissions.
3. Use Groups and Roles: Avoid assigning permissions to individual users.
4. Temporary Credentials: Use IAM roles and STS; never hardcode secrets.
5. Multi-Factor Authentication: Required for sensitive roles and root accounts.
6. Key Rotation: Automate rotation of access keys for compliance.
7. Centralized Auditing: Monitor IAM activity using AWS CloudTrail.
8. Segregation of Duties: Separate admin, developer, and auditor roles.
9. Tag IAM Resources: Enables cost tracking, auditing, and policy scoping.
10. Federation / SSO: Integrate with corporate IdPs (Active Directory, Okta) for enterprise identity management.

**Tags:** `#AWS #IAM #IdentityManagement #CloudSecurity #EnterpriseAWS #BestPractices #CloudEngineering #AWSCLI #CloudShell #Roles #Policies #Permissions`
