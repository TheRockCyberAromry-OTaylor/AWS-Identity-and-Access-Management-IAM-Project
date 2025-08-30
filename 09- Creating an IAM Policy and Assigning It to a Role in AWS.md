
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


 <img src="https://i.imgur.com/rYLZ5R7.png" height="100%" width="100%" /> 
