#    Create  user group for interns called "Interns"

<img src="https://i.imgur.com/JV52iux.png" height="100%" width="100%" /> 




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






<img src="https://i.imgur.com/ICaxdQw.png" height="100%" width="100%" />    


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


<img src="https://i.imgur.com/hXDUbvT.png" height="100%" width="100%" />    


#### **1. Navigating to IAM > User Groups**
- From the AWS Management Console, the user navigated to **IAM** via the left-hand menu.
- Selected **“User groups”** to manage group-based access control.

#### **2. Creating the “Interns” User Group**
- A green banner confirms successful creation of a group named **“Interns.”**
- This step likely involved:
  - Clicking **“Create group”**
  - Naming the group “Interns”
  - Optionally attaching policies (not shown in this view)

#### **3. Viewing Group Details**
- The Admin clicked **“View group”** next to “Interns” to inspect its configuration.
- The bottom panel shows the **Group Summary**, including:
  - **Group name:** Interns  
  - **Creation time:** July 18, 2023  
  - **ARN:** `arn:aws:iam::3743********group/Interns`

#### **4. Adding Users to the Group**
- Under the **“Users” tab**, two users were added:
  - `Intern_Hawa.Tombo`
  - `Intern_Julie.Tombo`
- Each entry includes:
  - **Console access status** (likely enabled)
  - **Last activity timestamp** (useful for auditing)

#### **5. Reviewing Access & Permissions**
- Tabs for **Permissions** and **Access Advisor** are visible:
  - **Permissions tab** would show attached policies (e.g., read-only access, S3 viewer, etc.)
  - **Access Advisor** helps monitor service usage for least privilege enforcement


### Notable Characters & Naming Convention

- The usernames follow a clear, role-based naming pattern:  
  `Intern_<FirstName>.Tombo`  
  This is excellent for traceability and aligns with best practices in IAM hygiene.
- The use of a dedicated **“Interns” group** allows centralized permission management — ideal for onboarding/offboarding workflows.


#    Create another user group for a project team called "ProjectX-Team"

<img src="https://i.imgur.com/aqOCbx8.png" height="100%" width="100%" />   
  
####  **Accessing the IAM Console**
- From the AWS Management Console homepage,navigate to **"IAM"** under the **Security, Identity, & Compliance** section.
- This opens the **IAM Dashboard**, which includes navigation links like:
  - **Dashboard**
  - **Access Management**
  - **Users**
  - **Groups**
  - **Roles**
  - **Policies**


### This captures a moment inside the **AWS Identity and Access Management (IAM)** console, specifically under **User groups**. Here's what stands out:

-  **Group Name:** `Interns`  
-  **Users in Group:** 2  
-  **Permissions:** Not yet defined  
-  **Created:** 2 days ago  
-  **Signed-in User:** `CloudAdmin_User @ 3743`  

###  Your Next Steps: Creating Another IAM Group

 **Navigate to IAM > User groups**  
   From the left sidebar, click on **Groups** under **Access management**.

 **Click “Create group”**  
   This opens the group creation wizard.

 **Name the Group**  
   Choose a descriptive name (e.g., `Contractors`, `DevOps_Team`, `SecurityAuditors`).

 **Add Users (Optional)**  
   You can assign users now or skip and add them later.

 **Attach Permissions Policies**  
   Select predefined AWS policies (like `ReadOnlyAccess`, `AmazonEC2FullAccess`) or attach custom ones.

 **Review and Create**  
   Confirm your selections and click **Create group**.


