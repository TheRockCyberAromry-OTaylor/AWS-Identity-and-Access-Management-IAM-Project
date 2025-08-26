

<img src="https://i.imgur.com/hurPfI1.png" height="100%" width="100%" /> 




 IAM Dashboard Actions

#### **1. Reviewing IAM Resource Summary**

- **Users (7)** and **Roles (2)** exist, but **User Groups (0)** and **Policies (0)** are empty.
- This suggests the account has individual users and roles set up, but no grouping or centralized policy management yet.

 *Implication:* The admin is likely preparing to organize users into groups for scalable permission management.



#### **2. Navigating to “User Groups” Section**
- The **User Groups** tab selected.
- No groups exist yet, and the **“Create group”** button is highlighted.

*Implication:* The admin is initiating the process to create a user group—essential for applying permissions to multiple users at once.



###  What Happens Next: Creating a User Group

 Admin clicks **“Create group,”** here’s what typically follows:

#### **Step 1: Name the Group**
- Choose a descriptive name (e.g., `DevOpsTeam`, `FinanceUsers`) to reflect the group's purpose.

#### **Step 2: Add Users to the Group**
- Select from the list of existing users (those 7 users shown in the dashboard).
- This step helps consolidate access control.

#### **Step 3: Attach Policies**
- Choose one or more IAM policies to define what the group can do.
- Since **Policies = 0**, the admin may need to create or import policies first (e.g., `AmazonS3ReadOnlyAccess`, `AdministratorAccess`).

 *Tip:* You can use AWS managed policies or create custom ones tailored to your organization's needs.



### Security Considerations from the Dashboard

The **Quick Links** section points to:
- **MFA setup**
- **Access key management**
- **Security credentials**

These are critical for hardening IAM access. Since organization's are methodical about IAM onboarding, this is a great moment to:
- Enforce MFA for all users
- Audit access keys and rotate them regularly
- Set password policies (e.g., minimum length, expiration)






<img src="https://i.imgur.com/FbXZbRY.png" height="100%" width="100%" />    


###  Steps Taken in the AWS IAM Console

#### 1. **Name the Group**
- **Action**: Entered `"Interns"` in the **Group Name** field.
- **Purpose**: This defines the identity of the group, useful for organizing access based on roles (e.g., interns, developers, admins).

#### 2. **Add Users to the Group (Optional)**
- **Action**: Selected **2 out of 7** available users:
  - `Data-Interns@Hawa.Tombo`
  - `Data-Interns@Julie.Tombo`
- **Purpose**: These users will inherit the permissions attached to the group. This step streamlines access management by assigning policies at the group level rather than individually.

#### 3. **Attach Permissions Policies (Optional)**
- **Action**: Selected **0 policies** out of 1066 available: NO policy was attached at this stage
- **Purpose**:Policies defines what actions group members can perform.Attaching  policies to interns should be carefully reviewed,especially if the group is meant for limited access.

#### 4. **Review and Create**
- **Action**: Clicked the **"Create user group"** button.
- **Purpose**: Finalizes the group creation, applying the selected users and permissions.



