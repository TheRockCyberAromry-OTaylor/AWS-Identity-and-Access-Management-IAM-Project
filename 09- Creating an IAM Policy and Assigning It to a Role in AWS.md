
<img src="https://i.imgur.com/eOuf9LD.png" height="100%" width="100%" /> 


###  Steps in Creating an IAM Policy via (Visual Editor Flow)

#### **1. Navigate to IAM Policies**
- From the AWS Management Console, go to **IAM**.
- Select the **Policies** tab to view existing policies.
- It displays a filtered view of **AWS managed policies**, such as `AdministratorAccess`, which are pre-built by AWS.

#### **2. Start Creating a New Policy**
- Click **Create policy** at the top right
- Choose the **Visual editor** tab to build the policy using a guided interface.

#### **3. Specify Permissions**
- Under the **Specify permissions** section:
  - Select a service from the dropdown. In the image, **Amazon S3** is chosen.
  - This determines which AWS service the policy will apply to.
  - Click next to proceed

<img src="https://i.imgur.com/Cco4Y7M.png" height="100%" width="100%" /> 
<img src="https://i.imgur.com/gcwHV8B.png" height="100%" width="100%" /> 



#### 4. **Policy Effect Selection**
- **Action:** Toggle the policy effect to **“Allow”**.
- **Purpose:** Grants the specified permissions to the IAM entity (user, group, or role).

#### 4a. **Permission Scope: Amazon S3**
- **Action:** Select **Amazon S3** as the service for which permissions are being configured.
- **Purpose:** Targets S3-specific actions like bucket and object management.

#### 4b. **Action Categories **
- **Action:** Expand the  three key action categories:
  - **List**
  - **Read**
  - **Write**
- **Purpose:** To view and select granular permissions within each category.

#### 4c. **Granular Permission Selection**
- **Action:** Specific checkboxes under each category were selected to define access:
  - **List Actions:** e.g., `ListBucket`, `ListAllMytBucket`
  - **Read Actions:** e.g., `GetAccessPoint`, `GetBuckeLocation`,`GetAccountPublicAccessBlock`
  - **Write Actions:** e.g., `CreateBucket`
- **Purpose:** Tailors the policy to allow only the necessary operations, following least privilege principles.


#### 5. **Resource Scope Selection**
- **Radio Buttons: "All" vs. "Specific"**
  - **"All"** applies the wildcard `*`, granting access to all resources for the selected actions.This was selected
  - **"Specific"** allows the user to define exact ARNs (Amazon Resource Names), tightening access control.

 **Security Implication:**  
The warning message rightly flags that using `*` is overly permissive. Switching to specific ARNs aligns with least privilege principles.



#### 6. **Security Warning Displayed**
- **Message:** _“The all wildcard '*' may be overly permissive…”_
  - This is a built-in safeguard nudging users toward better permission hygiene.
  - It’s likely triggered by the selection of sensitive actions (e.g., `iam:PassRole`, `s3:PutObject`, etc.) that should never be paired with `*`.

 **Best Practice Tip:**  
Use scoped ARNs like `arn:aws:s3:::my-secure-bucket/*` to avoid accidental privilege escalation.


#### 7. **Permission Expansion**
- **Button:** `+ Add more permissions`
  - Lets the user append additional actions/resources to the current policy block.


#### 8. **Navigation Controls**
- **Buttons:** `Cancel` and `Next`
  - Standard UI flow for discarding or advancing the permission setup.
  - Click `Next` to proceed .
    
 # Add and sprecify DMS (Database Migration Service) permissions to the policy


<img src="https://i.imgur.com/5ZuxOjo.png" height="100%" width="100%" /> 
<img src="https://i.imgur.com/S3NjI3S.png" height="100%" width="100%" /> 



###  Steps Reflected in the Image: Creating a DMS-Focused IAM Policy

#### 1. **Navigating to the Policy Creation Interface**
- The user is in the **IAM > Policies** section of the AWS Management Console.
- They’ve clicked **“Create policy”**, launching the policy editor in **Visual mode** (not JSON).

#### 2. **Choosing the Service: DMS**
- Under **“Specify permissions”**,Select **DMS (Database Migration Service)** from the service list.
- This filters available actions and resources to those relevant to DMS.


#### **3. Specify Permissions**
- Under the **Specify permissions** section:
  - Select a service from the dropdown. In the image, **Amazon DMS** is chosen.
  - This determines which AWS service the policy will apply to.
  - Click next to proceed


#### 4. **Policy Effect Selection**
- **Action:** Toggle the policy effect to **“Allow”**.
- **Purpose:** Grants the specified permissions to the IAM entity (user, group, or role).

#### 4a. **Permission Scope: Amazon DMS **
- **Action:** Select **Amazon DMS ** as the service for which permissions are being configured.
-  Purpose: Grants access to DMS-specific actions such as creating replication tasks, managing endpoints, and monitoring migration jobs.

#### 4b. **Action Categories **
- **Action:** Expand the  three key action categories:
  - **List**
  - **Read**
  - **Write**
- **Purpose:** To view and select granular permissions within each category.

#### 4c. **Granular Permission Selection**
- **Action:** Specific checkboxes under each category were selected to define access:
  - **List Actions:** e.g.,NO Actions
  - **Read Actions:** e.g., `DescribeAccountAttributes`, `DescribeReplications`,`DescribeReplicationsTask` ,`ListTagsForResources` `TestConnection`
  - **Write Actions:** NO Actions
- **Purpose:** Tailors the policy to allow only the necessary operations, following least privilege principles.


#### 5. **Resource Scope Selection**
- **Radio Buttons: "All" vs. "Specific"**
  - **"All"** applies the wildcard `*`, granting access to all resources for the selected actions.This was selected
  - **"Specific"** allows the user to define exact ARNs (Amazon Resource Names), tightening access control.

 **Security Implication:**  
The warning message rightly flags that using `*` is overly permissive. Switching to specific ARNs aligns with least privilege principles.



#### 6. **Security Warning Displayed**
- **Message:** _“The all wildcard '*' may be overly permissive…”_
  - This is a built-in safeguard nudging users toward better permission hygiene.
  - It’s likely triggered by the selection of sensitive actions that should never be paired with `*`.

 **Best Practice Tip:**  
Use scoped ARNs like  e.g `arn:aws:dms:us-east-1:123456789012:task:my-replication-task` to avoid accidental privilege escalation.


#### 7. **Permission Expansion**
- **Button:** `+ Add more permissions`
  - Lets the user append additional actions/resources to the current policy block.


#### 8. **Navigation Controls**
- **Buttons:** `Cancel` and `Next`
  - Standard UI flow for discarding or advancing the permission setup.
  - Click `Next` to proceed .





 <img src="https://i.imgur.com/rYLZ5R7.png" height="100%" width="100%" /> 
<img src="https://i.imgur.com/6aaf6Vg.png" height="100%" width="100%" /> 

# Add and sprecify ClousWatch permissions to the policy


###  Steps Reflected in the Image: Creating a DMS-Focused IAM Policy

#### 1. **Navigating to the Policy Creation Interface**
- The user is in the **IAM > Policies** section of the AWS Management Console.
- They’ve clicked **“Create policy”**, launching the policy editor in **Visual mode** (not JSON).

#### 2. **Choosing the Service:  CloudWatch**
- Under **“Specify permissions”**,Select **DMS (Database Migration Service)** from the service list.
- This filters available actions and resources to those relevant to DMS.


#### **3. Specify Permissions**
- Under the **Specify permissions** section:
  - Select a service from the dropdown. In the image, **Amazon  CloudWatch** is chosen.
  - This determines which AWS service the policy will apply to.
  - Click next to proceed


#### 4. **Policy Effect Selection**
- **Action:** Toggle the policy effect to **“Allow”**.
- **Purpose:** Grants the specified permissions to the IAM entity (user, group, or role).

#### 4a. **Permission Scope: Amazon CloudWatch **
- **Action:** Select **Amazon  CloudWatch** as the service for which permissions are being configured.
-  Purpose: Grants access to CloudWatch-specific actions for retrieving metric data and listing available metrics. This policy enables users or services to monitor performance and visualize operational health without modifying dashboards or resources.
   
#### 4b. **Action Categories **
- **Action:** Expand the  three key action categories:
  - **List**
  - **Read**
  - **Write**
- **Purpose:** To view and select granular permissions within each category.

#### 4c. **Granular Permission Selection**
- **Action:** Specific checkboxes under each category were selected to define access:
  - **List Actions:** e.g.,`ListMetricks`
  - **Read Actions:** e.g., `DescribeAlarms`
  - **Write Actions:** NO Actions
- **Purpose:** Tailors the policy to allow only the necessary operations, following least privilege principles.


#### 5. **Resource Scope Selection**
- **Radio Buttons: "All" vs. "Specific"**
  - **"All"** applies the wildcard `*`, granting access to all resources for the selected actions.This was selected
  - **"Specific"** allows the user to define exact ARNs (Amazon Resource Names), tightening access control.

 **Security Implication:**  
The warning message rightly flags that using `*` is overly permissive. Switching to specific ARNs aligns with least privilege principles.



#### 6. **Security Warning Displayed**
- **Message:** _“The all wildcard '*' may be overly permissive…”_
  - This is a built-in safeguard nudging users toward better permission hygiene.
  - It’s likely triggered by the selection of sensitive actions that should never be paired with `*`.

 **Best Practice Tip:**  
Use scoped ARNs like arn:aws:cloudwatch:us-east-1:123456789012:dashboard/MyApp-Metrics to restrict access to specific CloudWatch resources. This minimizes the risk of accidental privilege escalation and ensures users only interact with approved dashboards or metric sets.


#### 7. **Permission Expansion**
- **Button:** `+ Add more permissions`
  - Lets the user append additional actions/resources to the current policy block.


#### 8. **Navigation Controls**
- **Buttons:** `Cancel` and `Next`
  - Standard UI flow for discarding or advancing the permission setup.
  - Click `Next` to proceed .
 

#    ###   Review and Create Policy Details Configuration


 <img src="https://i.imgur.com/3RHBuUc.png" height="100%" width="100%" /> 



* This is the **final step (Step 2: Review and create)** after selecting permissions in Step 1.

#### **Policy Details**

* **Policy name**: `Policy@DataInterns001`

  * This is the chosen name for the IAM policy.
  * AWS requires the name to be unique within the account.
  * Allowed characters: alphanumeric plus `+=,.@-`.

* **Description (optional)**:

  * This field is empty 
  * Here you can provide a short explanation about what the policy is for.
  * Example: *“This policy grants read access to DMS and CloudWatch, and read/write to S3.”*
  * Max length: **1,000 characters**.


### **Top Section: Explicit Deny**

* **DMS (Database Migration Service)**

  * **Access level:** Limited: Write
  * **Resource:** All resources
  * **Request condition:** None

 This means the policy **explicitly denies** the ability to perform **write operations** in AWS Database Migration Service (DMS). Explicit denies always take precedence over allows, so even if another policy grants write to DMS, this deny will block it.



### **Bottom Section: Allow**

This section lists the services that are allowed under this policy.

1. **CloudWatch**

   * **Access level:** Limited: List, Read
   * **Resource:** All resources
   * **Request condition:** None
      The user can **list and read** monitoring and log data in CloudWatch but cannot write, delete, or create alarms.

2. **DMS**

   * **Access level:** Limited: Read
   * **Resource:** All resources
   * **Request condition:** None
      The user can **read information** from AWS Database Migration Service (DMS) but cannot perform write operations. (The explicit deny above enforces this restriction more strongly.)

3. **S3**

   * **Access level:** Limited: List, Read, Write
   * **Resource:** All resources
   * **Request condition:** None
     The user can **list, read, and write** objects in S3 buckets. This includes uploading, retrieving, and listing objects. However, it’s "limited," meaning certain admin actions like bucket policy changes may not be included.

### **Key Takeaways**

* **Explicit Deny on DMS Write** → User cannot perform write actions in DMS (migration tasks, modifications, etc.).
* **Allow CloudWatch (read-only)** → User can only view metrics and logs.
* **Allow DMS (read-only)** → User can view but not write in DMS.
* **Allow S3 (list, read, write)** → User has moderate-level permissions in S3.

This policy essentially gives the user **read-only access** to CloudWatch and DMS while giving **read/write access** to S3, with a strict **deny on DMS write** operations to prevent database migration changes.



### **Section: Add tags – optional**

* **Tags** are key-value pairs you can attach to AWS resources (like IAM policies, users, roles, EC2 instances, etc.).

* They are **optional**, but very useful for:

  * **Identification** → Example: `Owner=DataTeam`
  * **Organization** → Example: `Department=Interns`
  * **Cost tracking** (via AWS Cost Explorer)
  * **Automation/Filtering** (finding resources by tag)

* **Current status**:

  * No tags have been added yet.
  * You can add a new tag by clicking **Add new tag**.
  * AWS allows up to **50 tags per resource**.


### **Bottom Navigation Buttons**

* **Cancel** → Aborts the policy creation process.
* **Previous** → Goes back to the prior step (Review & Create).
* **Create policy (yellow button)** → Finalizes the creation of this IAM policy with the defined permissions, name, and optional tags.



<img src="https://i.imgur.com/LU2lY20.png" height="100%" width="100%" /> 

Perfect — this screenshot confirms that your IAM policy was **successfully created** in AWS. Let’s go over the details:


### **Top Green Banner**

* **Message:**  *Policy `Policy@DataInterns001` created.*
* This is AWS’s confirmation that the policy was created successfully and is now stored in IAM.
* There’s also a **View policy** button that lets you see the JSON and details of this new policy.


### **Main Section – Policies List**

* **Policies (1380)** → This means the AWS account currently has **1,380 IAM policies** (including AWS-managed and customer-managed).
* **Filter/Search** → You searched for `Policy@DataInterns001`. The system filtered the list to show only that matching policy.
* **Policy name:**

  * `Policy@DataInterns001` → This is the new **customer-managed IAM policy**.
  * The clickable blue link lets you open it to view/edit JSON, permissions, tags, etc.

#   Creating role to assign to the created policy  `Policy@DataInterns001`

      <img src="https://i.imgur.com/qPvn7Le.jpeg" height="100%" width="100%" />

## **Top Half (Existing Roles Overview)**

* **On the left pane :** `IAM access Management slect Roles`

* **Roles (2):**

  * `AWSServiceRoleForSupport`
  * `AWSServiceRoleForTrustedAdvisor`
    These are **AWS Service-linked roles**, automatically created by AWS so services (Support, Trusted Advisor) can perform actions on your behalf.

* **Columns:**

  * **Role name** → The name of the role.
  * **Trusted entities** → Which services/accounts can assume this role.
  * **Last activity** → When the role was last used.

* **Actions:**

  * **Create role (orange button)** → Starts the process of creating a new IAM role. Clicke on it
  * **Delete** → Option to delete selected roles (with restrictions).


## **Bottom Half (Creating a Role – Step 1: Select Trusted Entity)**

### **Trusted entity type options**

This determines **who/what can assume the role**:

1. **AWS service** → Lets AWS services (like EC2, Lambda) assume the role.
2. **AWS account ( is selected)** → Allows users, roles, or services in **your AWS account or another AWS account** to assume the role.
3. **Web identity** → Lets federated users sign in via identity providers (like Google, Amazon, Facebook, Cognito).
4. **SAML 2.0 federation** → For enterprise single sign-on using SAML identity providers.
5. **Custom trust policy** → Lets you manually define the trust policy JSON.




* **AWS account option selected** → Meaning this role can be assumed by entities in your own AWS account (`3743********`) or optionally another AWS account.

* **Options:**

  * **Require external ID** → Best practice when allowing third parties to assume the role (adds security).
  * **Require MFA** → Ensures that only users with MFA enabled can assume the role.

* **Buttons:**

  * **Cancel** → Exit the process.
  * **Next** (yellow) → Proceed to **Step 2: Add permissions**, where you attach policies (like the `Policy@DataInterns001` you just created).



<img src="https://i.imgur.com/3O0wKSO.jpeg" height="100%" width="100%" /> 


###  **Step 2: Add Permissions**
This section is where you attach policies to the IAM role:

- **Policy Selected**: `Policy@DataInterns001`  
  - Type: *Customer managed*
  - Description: *Empty* — consider adding a short summary for clarity in future documentation.
- **Filter Applied**: *Customer managed*  
  - This narrows the list to only policies created and managed within your account.
- **Visual Cue**: The dark mode interface enhances contrast, which could be useful for accessibility screenshots in your guides.



###  **Step 3: Name, Review, and Create**
This is the final checkpoint before role creation:

- **Role Name**: `Policy@DataInterns0011`  
  - Matches the policy name, suggesting a naming convention — possibly part of your branded “Cyber Armory” theme.
- **Description**: *Empty*  
  - AWS allows up to **64 characters**, including `+=,.@-` — a good reminder to include this in onboarding checklists.
- **Validation Note**: AWS enforces character limits and allowed symbols, which is useful to highlight in your permission hygiene documentation.

<img src="https://i.imgur.com/IxnzcUF.jpeg" height="100%" width="100%" /> 



###  **Step 1: Select Trusted Entities**
This is where the trust relationship is defined — essentially, who can assume the role.

- **Trust Policy (JSON)**:
  ```json
  {
    "Version": "2012-10-17",
    "Statement": [
      {
        "Effect": "Allow",
        "Principal": {
          "Service": "ec2.amazonaws.com"
        },
        "Action": "sts:AssumeRole"
      }
    ]
  }
  ```
  - **Principal**: `ec2.amazonaws.com` — this means EC2 instances are allowed to assume the role.
  - **Action**: `sts:AssumeRole` — the standard action that enables role assumption.
  - This setup is typical for granting EC2 instances access to AWS resources via IAM roles.

 *Tip for documentation*: You could visually annotate this JSON with callouts like “Who can assume?” and “What action is allowed?” to make it beginner-friendly.



### **Step 2: Add Permissions**
This section summarizes the policies that will be attached to the role.

- **Permissions Policy Summary**:
  - Columns shown: **Policy name**, **Type**, **Attached as**
  - No policies are listed in this screenshot — possibly a placeholder or pre-attachment state.
 *Suggestion*: Include a checklist in your guide for verifying that appropriate policies (e.g., read-only, S3 access) are attached before proceeding.



###  **Step 3: Add Tags (Optional)**
Tags help organize and manage roles across environments.

- **Add Tag Button**: Prompts the user to input key-value metadata.
  - Example tags: `Environment=Production`, `Team=Security`, `Project=CyberArmory`

* **Buttons:**

  * **Cancel** → Exit the process.
  * **Previous** → To go back
  * **Next** (yellow) → Proceed to Create the Role


<img src="https://i.imgur.com/9Ya1VuV.jpeg" height="100%" width="100%" /> 




 This is the AWS IAM (Identity and Access Management) console 

- A new IAM role has been successfully created.see the green banner  “Role Role@DataInterns001 created.”

-  Select the Roles section from the left-hand sidebar.
    - In the Roles section, the search bar shows Role@DataInterns001, and the console confirms 1 match.

- The role is associated with a specific AWS account (3743*******) as a trusted entity.

Other IAM features are visible (Roles Anywhere, X.509 Standard, Temporary credentials), but they weren’t acted on in this step — just informational.

  ##  Role Details Viewed:



- The ARN (Amazon Resource Name) for the role is shown.

- A console link to switch to this role is displayed (used by users in the AWS Management Console to assume this role).

- Maximum session duration is set to 1 hour.

- Permissions Policies Section:

- Currently, no policies are attached (the table shows “No resources to display”).

Buttons available: Simulate, Remove, and Add permissions → meaning the next step would be to grant this role permissions.

#  Assign created role to a user or group

<img src="https://i.imgur.com/4EFag0J.jpeg" height="100%" width="100%" /> 

- Navigate to IAM → User Groups
- From the AWS Console, go to IAM under Security, Identity, & Compliance.
- In the left sidebar, select User groups under Access management.
- Select User Group "Interns"
- Select Add Permission

- #  create a  policy so that a user group (likely “Interns”) can assume the IAM role Role@DataInterns001.

<img src="https://i.imgur.com/DAB9b4H.jpeg" height="100%" width="100%" /> 


### **What We’re Seeing**

* **Service:** AWS IAM → **Create Policy** workflow.
* **Step 1:** "Specify permissions" is selected.
* The **Policy editor** is open in **JSON mode**.


1. **Writing a Custom IAM Policy (in JSON):**

   * The JSON policy grants permission for the action **`sts:AssumeRole`**.
   * This allows the entity (such as a user or group) to assume a specific IAM role.

2. **Policy Content (explained line by line):**

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "Statement1",
         "Effect": "Allow",
         "Action": [
           "sts:AssumeRole"
         ],
         "Resource": [
           "arn:aws:iam::374XXXXXXX:role/Role@DataInterns001"
         ]
       }
     ]
   }
   ```

   * `"Version": "2012-10-17"` → Standard version for IAM policies.
   * `"Effect": "Allow"` → Grants the permission.
   * `"Action": "sts:AssumeRole"` → Lets the principal call the `AssumeRole` action.
   * `"Resource": "arn:aws:iam::...:role/Role@DataInterns001"` → Restricts this permission to **only the role `Role@DataInterns001`**.

3. **UI Elements Noticed:**

   * On the right side, it says **“Select a statement”** → you can add or edit JSON statements.
   * At the bottom, it shows **0 errors, 0 warnings** → meaning the JSON is valid.
   * Button **“Next”** is available to proceed to **Step 2 (Review and create)**.

* Once attached, members of the “Interns” group will be able to **switch to the role** and operate under its permissions (though currently, the role itself still has no policies attached — so it needs permissions too).


#   Create a custom IAM policy (Policy@DataInterns002) that allows members of the Interns group to assume the role Role@DataInterns001

<img src="https://i.imgur.com/5IVIKXy.jpeg" height="100%" width="100%" /> 


### **Step 2: Review and Create**

* After defining permissions in the JSON editor,review the policy before creating it.

1. **Policy name**

   * Chosen name: **`Policy@DataInterns002`**
   * This identifies the policy in IAM. The name suggests it’s tied to interns and is the second iteration (`002`).

2. **Permissions defined in this policy**

   * **Service:** **STS** (AWS Security Token Service)
   * **Access level:** Limited → Write
   * **Action Allowed:** `sts:AssumeRole`
   * **Resource:** Restricted specifically to

     ```
     Role@DataInterns001
     ```

     This means the only thing allowed is for the entity with this policy to assume the IAM role `Role@DataInterns001`.

3. **Request conditions**

   * None have been set → So there are no restrictions like MFA enforcement, source IP limits, or tag-based conditions.


### **Final Step**

* At the bottom, the **“Create policy”** button is highlighted.
* Once clicked,the policy will be created and can be **attached to a user, group, or another role** (in this case, likely the **Interns user group**).

* Just created a custom IAM policy (`Policy@DataInterns002`) that allows members of the Interns group to **assume the role `Role@DataInterns001`**.
* This fits into a **two-step access control system**:

  1. **Interns Group** → gets the AssumeRole policy (so they can switch into the role).
  2. **Role\@DataInterns001** → will need its own permissions (e.g., read-only access to S3, CloudWatch logs, etc.) to define what interns can actually do once they assume it.



<img src="https://i.imgur.com/UjswBdl.jpeg" height="100%" width="100%" /> 

1. **Policy Creation Confirmation**

   * The green banner at the top confirms:
      **“Policy Policy\@DataInterns002 created.”**

2. **Interns Group Details**

   * **User group name:** `Interns`
   * **Creation time:** July 24, 2025, 17:46 (UTC-04:00)
   * **ARN:** Unique Amazon Resource Name for this IAM group is displayed.
   * This group currently has **2 users** (seen under the *Users* tab).

3. **Permissions Tab**

   * The newly created policy **`Policy@DataInterns002`** is listed under *Permissions policies*.
   * This confirms that the **Interns group** has been granted the ability to **assume the role `Role@DataInterns001`**.

* **Interns Group** → Has the policy allowing **`sts:AssumeRole`** into `Role@DataInterns001`.
* **Interns Users (2 of them)** → As members of this group, they inherit this policy.
* **Next Step Required:** The role `Role@DataInterns001` itself must have policies attached (e.g., read-only access to S3, CloudWatch logs, etc.). Otherwise, even if interns assume it, they won’t be able to do anything useful.


