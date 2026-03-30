
Here it is reorganized into the same **sectioned format** used above for consistency and professional structure:

---

## **Section 0 – Project Title & Overview**

| Section | Title                           | Description                                                                                                                                                                                                        |
| ------- | ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 0.0     | Project Title & Overview        | Defines the project title and the high-level purpose of the AWS IAM hardening and least-privilege lab.                                                                                                             |
| 0.1     | Introduction & Project Overview | Provides an overview of the project goals, relevance, and expected security outcomes (IAM best practices, MFA, password policy, roles, least privilege).                                                           |
| 0.2     | Objective & Scope               | Establishes project objectives: secure root account, create administrative IAM users, enforce MFA and password policies, implement group-based access, create custom policies and roles, and test least privilege. |
| 0.3     | Project Methodology             | Describes the end-to-end IAM methodology: from AWS account creation to role assumption and permission validation.                                                                                                  |
| 0.4     | Lab Environment Setup           | Details the AWS account, IAM resources, and configuration steps used throughout the lab.                                                                                                                           |
| 0.5     | Key Sources, Frameworks & Tools | Consolidates authoritative references: AWS documentation, IAM best practices, MITRE ATT&CK for privilege escalation, and supporting tools (HashMyFiles for hash verification, etc.).                               |

---

## **Section 1 – AWS Account Setup & Root Access**

| Section | Title                           | Description                                                                                                                       |
| ------- | ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| 1.0     | AWS Account Setup & Root Access | Overview of AWS account registration, identity verification, payment method, support plan selection, and first root user sign-in. |

---

## **Section 2 – Admin IAM User Creation from Root**

| Section | Title                             | Description                                                                                                        |
| ------- | --------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| 2.0     | Admin IAM User Creation from Root | Creation of an administrative IAM user (CloudAdmin_Tuss) with full AdministratorAccess and initial password reset. |

---

## **Section 3 – IAM User First-Time Sign-In**

| Section | Title                       | Description                                                                            |
| ------- | --------------------------- | -------------------------------------------------------------------------------------- |
| 3.0     | IAM User First-Time Sign-In | Process for the new admin user to sign in, change password, and verify console access. |

---

## **Section 4 – Multi-Factor Authentication (MFA) Enforcement**

| Section | Title                                         | Description                                                                                                           |
| ------- | --------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| 4.0     | Multi-Factor Authentication (MFA) Enforcement | Step-by-step configuration of virtual MFA (Google Authenticator) for the admin user to strengthen account protection. |

---

## **Section 5 – Password Policy Configuration**

| Section | Title                         | Description                                                                                                                              |
| ------- | ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| 5.0     | Password Policy Configuration | Customisation of IAM password policy: minimum length (12), complexity requirements, expiration (90 days), and password reuse prevention. |

---

## **Section 6 – IAM User Creation**

| Section | Title             | Description                                                                                                                    |
| ------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| 6.0     | IAM User Creation | Bulk creation of IAM users for different roles (interns, sales, analysts, operators) with console access and custom passwords. |

---

## **Section 7 – IAM User Groups & Permission Grouping**

| Section | Title                                 | Description                                                                                        |
| ------- | ------------------------------------- | -------------------------------------------------------------------------------------------------- |
| 7.0     | IAM User Groups & Permission Grouping | Creation of logical groups (Interns, ProjectX-Team, CloudAdmin) and assignment of users to groups. |

---

## **Section 8 – Custom IAM Policies & Role Assignment**

| Section | Title                                 | Description                                                                                                                                                                                                   |
| ------- | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 8.0     | Custom IAM Policies & Role Assignment | Design and attachment of customer-managed policies (Policy@DataInterns001, Policy@DataInterns002) to control access to S3, DMS, and CloudWatch. Creation of a role (Role@DataInterns001) with those policies. |

---

## **Section 9 – Role Assumption via Switch Role**

| Section | Title                           | Description                                                                                                                                                      |
| ------- | ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 9.0     | Role Assumption via Switch Role | Configuration of a policy that allows the Interns group to assume Role@DataInterns001; demonstration of the “Switch Role” URL and console-based role assumption. |

---

## **Section 10 – Least-Privilege Testing & Validation**

| Section | Title                                | Description                                                                                                                                                                                                  |
| ------- | ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 10.0    | Least-Privilege Testing & Validation | Verification that the intern user ([Data-Interns@Hawa.Tombo](mailto:Data-Interns@Hawa.Tombo)) cannot access S3, DMS, or CloudWatch directly, but gains those permissions after assuming Role@DataInterns001. |

---

If you want next, I can **merge both AWS + Azure projects into one polished GitHub portfolio repo structure** (this is *very* powerful for SOC/Cloud Security job applications).
