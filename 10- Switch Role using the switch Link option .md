
<img src="https://i.imgur.com/z1b0hbr.jpeg" height="100%" width="100%" /> 

### **1. IAM Roles Section (Left Sidebar Highlighted)**

* The **“Roles”** menu item in the IAM sidebar is highlighted.
* This shows the user Data-Interns@Hawa.Tombo has logged-i and  **navigated specifically into the Roles section** of IAM.

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

   * `Policy@DataInterns001` defines what interns can do after assuming the role.

