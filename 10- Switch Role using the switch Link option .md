# Group users assuming roles

<img src="https://i.imgur.com/z1b0hbr.jpeg" height="100%" width="100%" /> 

### **1. IAM Roles Section (Left Sidebar Highlighted)**

* The **“Roles”** menu item in the IAM sidebar is highlighted.
* This shows the user Data-Interns@Hawa.Tombo has logged-in and  **navigated specifically into the Roles section** of IAM.

  * Roles are central to this setup. Instead of attaching policies directly to interns (users), access is being **delegated via an IAM role**.
  * This aligns with AWS best practice: *grant permissions to roles, then let users/groups assume them*.

### **2. Role Selection in Roles List (Top Half – Red Box & Arrow)**

* From the list of available roles, the user selected:
   **`Role@DataInterns001`**
* Other roles (like `AWSServiceRoleForSupport` and `AWSServiceRoleForTrustedAdvisor`) are AWS service-linked roles, not for human users.
* **Action taken here:** Explicitly opened `Role@DataInterns001` to manage and configure it for interns.


### **3. Switch Role Link (Middle Right – Red Box & Arrow)**

* Inside the details of `Role@DataInterns001`, the **“Link to switch roles in console”** is highlighted.
* This link is crucial:

  * Interns can click or copy and paste this link in a browser interface to assume the role from the AWS Management Console.
  * No need to manually enter the role ARN or account ID.
  * It ties directly to the earlier policy (`Policy@DataInterns002`) given to the Interns group, which allows them to call **`sts:AssumeRole`**.



### **4. Attached Policy on the Role (Bottom Half – Red Box & Arrow)**

* The **Permissions policies** section shows `Policy@DataInterns001` is attached to the role.
* This is a **customer-managed policy**, not AWS-managed → meaning it was manually created to define what this role can do.
* **Significance:**

  * Without this policy, the role would exist but be powerless.
  * By attaching `Policy@DataInterns001`, the admin ensures that once interns assume the role, they inherit its permissions.



## **Step-by-Step Flow with the Sidebar Context**

1. **Navigate to IAM → Roles** (sidebar highlighted).

   * This is the starting point to manage or create roles.

2. **Select `Role@DataInterns001` from the roles list.**

   * This is the role intended for interns.

3. **Review Role Details.**

   * ARN and max session duration visible.
   * Trusted entities = AWS account itself.

4. **Use/Share the Switch Role Console Link.**

   * Makes it easy for interns to assume the role.

5. **Attach Policy to Role.**


#  Steps Taken in the AWS "Switch Role" Interface

<img src="https://i.imgur.com/heWQjYU.png" height="100%" width="100%" /> 

 
#### 1. **Navigating to the Role Switch URL**
- The user accesses a direct URL for switching roles:  `https://signin.aws.amazon.com/switchrole?...` pasted in a browser(coppied earlier)
- This URL is often bookmarked or shared internally to streamline access to specific roles.

#### 2. **Entering the Target Account ID**
- **Field:** `Account ID`  
  - The user inputs the AWS account ID they want to switch into.  
  - In the image, it begins with `3743********` suggesting a truncated or partially redacted value for privacy.

#### 3. **Specifying the IAM Role Name**
- **Field:** `IAM role name`  
  - The user enters `Role@Datainterns001`, which is likely a predefined IAM role in the target account.  
  - This role governs what permissions the user will have once switched.

#### 4. **Customizing the Role Display**
- **Field:** `Display name - optional`  
  - The user repeats `Role@Datainterns001` here, which will appear in the AWS console header once the role is assumed.
- **Field:** `Display color - optional`  
  - The user selects **Green**, which helps visually distinguish this role from others in the console UI.

#### 5. **Executing the Role Switch**
- **Button:** `Switch Role`  
  - Clicking this submits the form and transitions the user into the specified role.  
  - The console will update to reflect the new role context, including the green highlight and display name.


<img src="https://i.imgur.com/T45nIoc.png" height="100%" width="100%" /> 



### Top Right: Account Info
- **User:** `Role@Datainterns001@3743********`currently logged into AWS as the IAM role Role@DataInterns001 in account 3743******** successfully.
- User not acting as original user directly.Once this role assumed,permissions are limited to what Policy@DataInterns001 (attached to the role) allows.

###  Region Selector
- **Region:** `US East (N. Virginia)`  
  This defines the AWS region where services are being accessed. It affects latency, data residency, and service availability.


###  Center Panel: Applications & Permissions
- **Applications (0):**  
  No applications are currently listed under the AWS Service Catalog.
- **Error Message:**  
  `"Access denied to servicecatalog:ListApplications"`  
  This means the current IAM user lacks permission to list applications via the Service Catalog API. It’s likely a missing policy or role assignment.
- **Button:** `Diagnose with Amazon Q`  
  This offers a diagnostic tool powered by Amazon Q to help troubleshoot permission issues—potentially useful for guided remediation.



### Left Sidebar: Recently Visited Services
- **Database Migration Service**  
  Indicates recent work involving data migration—possibly part of a cloud modernization or lift-and-shift workflow.
- **S3 (Simple Storage Service)**  
  Suggests recent interaction with object storage—could be for storing logs, assets, or migration targets.



