
<img src="https://i.imgur.com/nb5rPCP.png" height="100%" width="100%" />    


1. **Logged into AWS Console**  
   - The top bar shows the signed-in user as `CloudAdmin_Tuss @ 3743********`, indicating access via the AWS Management Console.

2. **Accessed IAM (Identity and Access Management)**  
   - From the AWS services menu or search bar, navigate to the IAM dashboard.

3. **Selecte “Users” from the Left Sidebar**  
   - The IAM navigation pane on the left includes options like Dashboard, User groups, Users, Roles, and Policies.  
   - “Users” was selected to view individual IAM user accounts.



###  IAM User Creation Flow (Starting from the Yellow Button)

####  Step 1: Click **Create user**
- Located top-right on the **Users** page.
- Launches the IAM user creation wizard.

####  Step 2: Set user details
- **User name**: Enter a unique name (e.g., `Test.user`).
- **Access type**:
  -  *AWS Management Console access* — for GUI login.
  -  *Programmatic access* — for CLI/API usage (generates access keys).

####  Step 3: Configure credentials
- **Console password**: Choose auto-generated or custom.
- Optionally require password reset on first sign-in.
- MFA setup is not done here — it’s configured post-creation.

####  Step 4: Set permissions
- Choose one of:
  - **Add user to group** — inherit group policies.
  - **Copy permissions from existing user**.
  - **Attach policies directly** — not recommended for long-term scaling.

####  Step 5: Add tags (optional)
- Key-value pairs for tracking, billing, or automation.

####  Step 6: Review and create
- Summary of all selections.
- Click **Create user** to finalize.






###  AWS IAM User Creation Summary

1. **Click “Create user”** — top-right yellow button on the Users page.
2. **Enter user details** — name, access type (console or programmatic).
3. **Set credentials** — choose password options; MFA is configured later.
4. **Assign permissions** — via groups, existing users, or direct policies.
5. **Add tags (optional)** — for tracking or automation.
6. **Review & create** — confirm settings and finalize user creation.


<img src="https://i.imgur.com/4vvGdBT.png="100%" width="100%" />   



###  Step-by-Step Breakdown: Creating an IAM User in AWS Console

#### **Step 1: Specify User Details**
You're on the first step of the IAM user creation flow.

- ** Username Entered:**  
  `SalesAssoc.jane`  
  This follows a clear naming convention—likely role-based (`SalesAssoc`) with a personal identifier (`jane`). This helps with traceability and access auditing.



#### ** Access Type Selection**
Two options are presented for user access:

- **Option 1 (Recommended):**  
  *Specify a user in Identity Center* – This is AWS’s preferred method for centralized identity management.

- **Option 2 (Selected):**  
   *I want to create an IAM user* – choose to create a traditional IAM user directly in AWS.


#### ** Console Access Configuration**
 Enabling access to the AWS Management Console:

- **Console Password Type:**  
   Selected **Custom password**, which triggers the password policy requirements.


###  Password Requirements (Highlighted)
To meet AWS’s security standards, the custom password must:

- Be **at least 12 characters**
- Include **one uppercase letter** (A–Z)
- Include **one lowercase letter** (a–z)
- Include **one number** (0–9)
- Include **one non-alphanumeric character**  
  Examples: `@ # $ % ^ & * ( ) _ + - = [ ] { } | ?`

These requirements are designed to enforce strong password hygiene and reduce brute-force vulnerabilities.


#### ** Additional Security Option**
-  *Require password reset at next sign-in*  
  This checkbox is selected, ensuring the user sets a personal password upon first login—great for initial onboarding security.



#### ** Programmatic Access (Optional)**
A note is included about enabling programmatic access via:

- **Access keys**
- **Service-specific credentials** (e.g., AWS CodeCommit, Amazon Keyspaces)

This step isn’t configured yet but is relevant if the user needs CLI or API access.


#### ** Navigation**
- The **“Next”** button is highlighted, indicating readiness to proceed to **Step 2: Set Permissions**.


                                                                                 
