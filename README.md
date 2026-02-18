# aws-security-foundation-lab

Project Overview
This repository documents a structured hands-on lab focused on building a secure AWS account foundation using industry best practices.
The purpose of this project is to implement and understand:
AWS Identity and Access Management (IAM)
Least-privilege access control
Multi-factor authentication (MFA)
Credential reporting and auditing
IAM Access Analyzer
Federation concepts and temporary credentials
Governance design using AWS Organizations and Control Tower concepts
This lab simulates the responsibilities of a Cloud Security Engineer securing an enterprise AWS environment.
Objectives
Secure and protect the AWS root account
Implement IAM users and groups following least-privilege principles
Enforce MFA for human access
Generate and analyze credential reports
Create and validate custom IAM policies
Use IAM Access Analyzer to detect risky access
Implement IAM roles and simulate federation
Design a multi-account governance structure using Organizational Units (OUs)
Apply AWS security best practices
Architecture Overview
Copy code

AWS Account
├── Root Account (Secured with MFA)
├── IAM Users
│   ├── admin-user
│   ├── dev-user
│   └── intern-user
├── IAM Groups
│   ├── Admins
│   ├── Developers
│   └── Interns
├── IAM Policies
│   ├── AWS Managed Policies
│   └── Custom Least-Privilege Policies
├── IAM Roles
│   └── ReadOnlyRole (Temporary Access Simulation)
└── Governance Model (Simulated OU Design)
Implementation Phases

Phase 1 – IAM Core Setup

Focus: Foundational Identity Security

Tasks completed:
Secured root account with MFA
Created IAM groups (Admins, Developers, Interns)
Created IAM users and assigned via groups
Attached AWS managed policies
Enforced MFA for human users
Generated and analyzed credential report
Security concepts applied:
Root account protection
Group-based permission management
Least privilege
MFA enforcement

Phase 2 – Policy Hardening & Analysis

Focus: Policy precision and risk detection

Tasks completed:
Created custom IAM policy for restricted S3 access
Implemented policy conditions (e.g., IP restriction or MFA requirement)
Used IAM Access Analyzer to validate permissions
Reviewed public and cross-account access findings
Simulated access key lifecycle (creation and deactivation)
Security concepts applied:
Policy validation
Conditions in IAM policies
Access review and analysis
Long-term vs temporary credential understanding

Phase 3 – Federation & Temporary Credentials

Focus: Role-based access and STS

Tasks completed:
Created IAM role for read-only access
Tested role switching
Studied AWS STS temporary credentials
Compared long-term credentials vs short-term credentials
Researched IAM Identity Center (federated workforce access)
Security concepts applied:
Role assumption
Temporary credentials
Identity federation
Reduced reliance on long-term IAM users

Phase 4 – Governance & Guardrails (Design Simulation)

Focus: Multi-account security architecture

Designed Organizational structure:
//Copy code

Root
├── Security OU
├── Development OU
└── Production OU
Concepts studied:
AWS Organizations
Organizational Units (OUs)
Service Control Policies (SCPs)
Guardrails (Mandatory, Strongly Recommended, Elective)
AWS Control Tower landing zone basics
Guardrail inheritance in Account Factory

Security concepts applied:

Enterprise governance
Preventive vs detective controls
Account-level permission boundaries
AWS Security Best Practices Applied
Root user secured and not used for daily tasks
MFA required for human users
Least-privilege permissions implemented
Policies validated using IAM Access Analyzer
Temporary credentials preferred over long-term access keys
Regular review of credential reports
Governance model designed for scale

Key Learnings

How IAM policy evaluation works
Differences between identity-based and resource-based policies
Risks of over-permissioned accounts
Importance of temporary credentials (STS)
How federation reduces credential management risk
How governance scales across multiple AWS accounts

Future Enhancements

Implement permissions boundaries
Integrate with AWS KMS and Secrets Manager
Deploy a Spring Boot microservice and secure it using IAM roles
Implement CI/CD with least-privilege IAM policies
Explore real AWS Organizations setup with multiple accounts

Author
D.M.S.Kenulya
Cloud Security Engineering Lab
Focused on backend systems, cloud security, and secure architecture design.
