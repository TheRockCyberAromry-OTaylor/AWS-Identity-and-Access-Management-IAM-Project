
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


 <img src="https://i.imgur.com/3RHBuUc.jpeg" height="100%" width="100%" /> 



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





