# Group users assuming roles

<img src="https://i.imgur.com/z1b0hbr.jpeg" height="100%" width="100%" /> 

### **1. Navigate to IAM → Roles(sidebar highlighted).**
* User Data-Interns@Hawa.Tombo logged-in   
  * In the left Sidebar **navigated specifically into the Roles section** of IAM
  * Roles are central to this setup. Instead of attaching policies directly to interns (users), access is being **delegated via an IAM role**.
  * This aligns with AWS best practice: *grant permissions to roles, then let users/groups assume them*.
    

### **2. Role Selection in Roles List (Top Half – Red Box & Arrow)**
* From the list of available roles,select **`Role@DataInterns001`**
* Other roles (like `AWSServiceRoleForSupport` and `AWSServiceRoleForTrustedAdvisor`) are AWS service-linked roles, not for human users.
* **Action taken here:** Explicitly opened `Role@DataInterns001` to manage and configure it for interns.

### **3. Validate that `Role@DataInterns001` has  policy or policies attached to it**

   * Click on permissions to verify if policy or policies was  attached to the  selected `Role@DataInterns001`
    * The purpose of clicking on **Permissions** for `Role@DataInterns001` is to **confirm that the correct policies are attached**.
    * This ensures the role has the intended access, supports  least privilege,and  prevents misconfigurations.


### **4. Switch Role Link (Middle Right – Red Box & Arrow)**
* Inside the details of `Role@DataInterns001`, the **“Link to switch roles in console”** is highlighted.
* This link is crucial:

  * Interns can click or copy and paste this link in a browser interface to assume the role from the AWS Management Console.
  * No need to manually enter the role ARN or account ID.
  * It ties directly to the earlier policy (`Policy@DataInterns002`) given to the Interns group, which allows them to call **`sts:AssumeRole`**.



### **5. Attached Policy on the Role (Bottom Half – Red Box & Arrow)**
* The **Permissions policies** section shows `Policy@DataInterns001` is attached to the role.
* This is a **customer-managed policy**, not AWS-managed - meaning it was manually created to define what this role can do.
* **Significance:**

  * Without this policy, the role would exist but be powerless.
  * By attaching `Policy@DataInterns001`, the admin ensures that once interns assume the role, they inherit its permissions.


#  Steps Taken in the AWS "Switch Role" Interface

<img src="https://i.imgur.com/heWQjYU.png" height="100%" width="100%" /> 

 
#### 1. **Navigating to the Role Switch URL**
- Use a direct URL for switching roles:  `https://signin.aws.amazon.com/switchrole?...` paste in a browser(coppied earlier)
- This URL is often bookmarked or shared internally to streamline access to specific roles.

#### 2. **Entering the Target Account ID**
- **Field:** `Account ID`  
  - Input the AWS account ID want to switch into.  
  - In the case, it begins with `3743********` suggesting a truncated or partially redacted value for privacy.

#### 3. **Specifying the IAM Role Name**
- **Field:** `IAM role name`  
  - Enter `Role@Datainterns001`, which is likely a predefined IAM role in the target account.  
  - This role governs what permissions the user will have once switched.

#### 4. **Customizing the Role Display**
- **Field:** `Display name - optional`  
  - Enter `Role@Datainterns001` here, which will appear in the AWS console header once the role is assumed.
  - **Field:** `Display color - optional`  
  - In this case selects **Green**, which helps visually distinguish this role from others in the console UI.

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



