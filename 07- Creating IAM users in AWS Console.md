
<img src="https://i.imgur.com/jlgVRvB.png" height="100%" width="100%" />    


1. **Logged into AWS Console**  
   - The top bar shows the signed-in user as `CloudAdmin_Tuss @ 3743********`, indicating access via the AWS Management Console.

2. **Accessed IAM (Identity and Access Management)**  
   - From the AWS services menu or search bar, navigate to the IAM dashboard.

3. **Selecte “Users” from the Left Sidebar**  
   - The IAM navigation pane on the left includes options like Dashboard, User groups, Users, Roles, and Policies.  
   - “Users” was selected to view individual IAM user accounts.

#  STEP 1  **Click “Create user”** — top-right yellow button on the Users page.

###  IAM User Creation Flow (Starting from the Yellow Button)

####  step:  Click **Create user**
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


#  STEP 2  **Enter user details** — name, access type (console or programmatic).
  
<img src="https://i.imgur.com/xYs0Vcy.jpeg" height="100%" width="100%" />  



###  Creating an IAM User in AWS Console

#### **Step 1: Specify User Details

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
- The **“Next”** button is highlighted, indicating readiness to proceed to **Step 3: Set Permissions**.


 #  STEP 3  **Assign permissions** — via groups, existing users, or direct policies.   


 
<img src="https://i.imgur.com/SFGLfKN.png" height="100%" width="100%" />  



This step determines **what the new user can access or do** within the AWS environment.

####  **Choose How to Assign Permissions**
Three options are presented:
- **Add user to group**: Assign permissions via IAM groups.
- **Copy permissions from existing user**: Clone access from another IAM user.
- **Attach policies directly**: Manually select policies to apply to this user.

In this image, the **“Attach policies directly”** option is being used.As a best practice,we recommend attaching policies to a group instead.


#### 2. **Search and Select Policies**
 Browsing AWS-managed policies. Three are visible:

| Policy Name                         | Type           | Attached Entities |
|------------------------------------|----------------|-------------------|
| AmazonAPIGatewayPushToCloudWatchLogs | AWS Managed    | 0                 |
| AmazonAppFlowFullAccess            | AWS Managed    | 0                 |
| AmazonAppFlowReadOnlyAccess        | AWS Managed    | 0                 |

- These policies are **not yet attached** to any users, groups, or roles.
- The search bar allows filtering by keyword (e.g., “AppFlow”).


####  **(Optional) Set Permissions Boundary**
- This section lets you define the **maximum permissions** the user can have, even if other policies grant more.
- No boundary is set yet , which means the user will inherit full permissions from the selected policies.


 #  STEP 4   **Review & create** — confirm settings and finalize user creation.


<img src="https://i.imgur.com/8HkosvN.png" height="100%" width="100%" />  


#### **1. User Details Configuration Review**
- ** User name:** `SalesAssoc.jane`  
  - This follows a naming convention likely used for role-based access (e.g., Sales Associate). The dot notation (`Firstname.Lastname`) helps with clarity and traceability.
- ** Console password type:** *Custom password*  
  - Instead of auto-generating a password, the admin manually set one—useful for onboarding when credentials need to be shared securely.
- ** Require password reset:** *No*  
  - The user won’t be prompted to change their password on first login. This might be intentional for temporary access or pre-configured credentials.

#### **2. Permissions Summary**
- ** No resources listed**  
  - This means no policies or groups have been attached yet. The user has no permissions to interact with AWS services. It’s a placeholder state—permissions can be added post-creation or via group membership.

#### **3. Tags (Optional Metadata)**
- **🏷 No tags associated**  
  - Tags help with cost allocation, access control, and resource organization. None were added here, but the dashboard shows the option to add up to 50.
- ** “Add tag” button visible**  
  - This encourages admins to include metadata like department, role, or environment (e.g., `Department: Sales`, `Environment: Production`).


- Action Buttons:
- Cancel: Aborts the process and discards all inputs
- Previous: Returns to the prior step to modify permissions or user settings
- Create user: Finalizes creation with current settings and proceeds to credential download.This was selected
  

 #  STEP 5  "Retrieve password" is the final and critical step where AWS presents the one-time view of the newly created user's console password


 <img src="https://i.imgur.com/u9SAUqY.png" height="100%" width="100%" /> 

  Once the user is created, the dashboard displays:
  
 **Success Banner**
   - Green banner confirms: “User created successfully”.
   - Option to View user is available.

  
 **Console Sign-In Details**
  - Sign-in URL: A unique AWS console link for the user.
  - User name: SalesAssoc.jane
  - Console password: Masked for security, with an option to reveal.

  
**Important Note**
  
   - This is the only time the password can be viewed or downloaded. AWS does not store it for later retrieval.

     
 **Actions Available**
  
  - Email sign-in instructions: Sends credentials and sign-in link to the user.
  - Download .csv file: Exports credentials for secure storage or onboarding documentation.This option is selected
  - Cancel or Return to users list: Ends the workflow or navigates back
  - 

   #  STEP 6 Locating the downloaded AWS Credential File

 
<img src="https://i.imgur.com/8mLHAqi.jpeg" height="100%" width="100%" /> 

#### **1. Locating the Credential File**
- **Action:** Navigates to the `Downloads` folder in File Explorer.
- **Highlight:** The file `SalesAssoc.jane_credentials.xlsx` is selected.
- **Implication:** This suggests the user is preparing to access **Sales Associate role**, specifically for the user `jane`.



#### **2. Opening the Credential Dashboard**
- **Action:** The selected Excel file is opened, revealing a structured dashboard.
- **Layout Insight:**
  - **Column A:** `User name` — Identifies the IAM user (`SalesAssoc.jane`)
  - **Column B:** `Password` — Shows the assigned password (`aBc123@456`) - sample password
  - **Column C:** `Console sign-in URL` — Provides the AWS login link for this user



#### **3. Credential Provisioning Context**
- **Purpose:** This spreadsheet likely serves as a **manual credential distribution tool** for onboarding or role-based access.
- **Security Note:** The presence of plaintext passwords and URLs suggests this is a **preliminary or internal staging document**, not yet hardened for secure delivery.
- **NOTE**: Passwords is going to be hardened by the implementation of MFA
  

#  New User Accounts Added/Created for Project Workflow

<img src="https://i.imgur.com/tQZCJzx.png" height="100%" width="100%" /> 

  Once the user is created, the dashboard displays:
  
 **Success Banner**
   - Green banner confirms: “User created successfully”.
   - Option to View user is available.

  
 **Console Sign-In Details**
  - Sign-in URL: A unique AWS console link for the user.
  - User name: Data-Interns@Hawa.Tombo
  - Console password: Masked for security, with an option to reveal.

  
**Important Note**
  
   - This is the only time the password can be viewed or downloaded. AWS does not store it for later retrieval.

     
 **Actions Available**
  
  - Email sign-in instructions: Sends credentials and sign-in link to the user.
  - Download .csv file: Exports credentials for secure storage or onboarding documentation.This option is selected
  - Cancel or Return to users list: Ends the workflow or navigates back

#### **Locating the Credential File**
- **Action:** Navigates to the `Downloads` folder in File Explorer.**See File Explorer image above**
- **Select:** The file `Data-Interns@Hawa.Tombo_credentials.xlsx` 
- **Implication:** This suggests the user is preparing to access **Data Intern role**, specifically for the user `Hawa.Tombo`.


<img src="https://i.imgur.com/PPIZY2p.png" height="100%" width="100%" /> 

Once the user is created, the dashboard displays:
  
 **Success Banner**
   - Green banner confirms: “User created successfully”.
   - Option to View user is available.

  
 **Console Sign-In Details**
  - Sign-in URL: A unique AWS console link for the user.
  - User name: Data-Interns@Julie.Tombo
  - Console password: Masked for security, with an option to reveal.

  
**Important Note**
  
   - This is the only time the password can be viewed or downloaded. AWS does not store it for later retrieval.

     
 **Actions Available**
  
  - Email sign-in instructions: Sends credentials and sign-in link to the user.
  - Download .csv file: Exports credentials for secure storage or onboarding documentation.This option is selected
  - Cancel or Return to users list: Ends the workflow or navigates back

#### **Locating the Credential File**
- **Action:** Navigates to the `Downloads` folder in File Explorer.**See File Explorer image above**
- **Select:** The file `Data-Interns@Julie.Tombo_credentials.xlsx` 
- **Implication:** This suggests the user is preparing to access  **Data Intern role**, specifically for the user `Julie.Tombo`.



<img src="https://i.imgur.com/rMuUNZb.png" height="100%" width="100%" /> 


Once the user is created, the dashboard displays:
  
 **Success Banner**
   - Green banner confirms: “User created successfully”.
   - Option to View user is available.

  
 **Console Sign-In Details**
  - Sign-in URL: A unique AWS console link for the user.
  - User name: App-Operator.john
  - Console password: Masked for security, with an option to reveal.

  
**Important Note**
  
   - This is the only time the password can be viewed or downloaded. AWS does not store it for later retrieval.

     
 **Actions Available**
  
  - Email sign-in instructions: Sends credentials and sign-in link to the user.
  - Download .csv file: Exports credentials for secure storage or onboarding documentation.This option is selected
  - Cancel or Return to users list: Ends the workflow or navigates back

#### **Locating the Credential File**
- **Action:** Navigates to the `Downloads` folder in File Explorer.**See File Explorer image above**
- **Select:** The file `App-Operator.john_credentials.xlsx` 
- **Implication:** This suggests the user is preparing to access **App-Operator role**, specifically for the user `App-Operator.john`.


<img src="https://i.imgur.com/xnCs9uV.png" height="100%" width="100%" /> 


Once the user is created, the dashboard displays:
  
 **Success Banner**
   - Green banner confirms: “User created successfully”.
   - Option to View user is available.

  
 **Console Sign-In Details**
  - Sign-in URL: A unique AWS console link for the user.
  - User name: SecurityAnlst.Musa


  - Console password: Masked for security, with an option to reveal.

  
**Important Note**
  
   - This is the only time the password can be viewed or downloaded. AWS does not store it for later retrieval.

     
 **Actions Available**
  
  - Email sign-in instructions: Sends credentials and sign-in link to the user.
  - Download .csv file: Exports credentials for secure storage or onboarding documentation.This option is selected
  - Cancel or Return to users list: Ends the workflow or navigates back

#### **Locating the Credential File**
- **Action:** Navigates to the `Downloads` folder in File Explorer.**See File Explorer image above**
- **Select:** The file `SecurityAnlst.Musa_credentials.xlsx` 
- **Implication:** This suggests the user is preparing to access **Security analyst role**, specifically for the user `SecurityAnlst.Musa`.


<img src="https://i.imgur.com/VHBfmDG.png" height="100%" width="100%" /> 


Once the user is created, the dashboard displays:
  
 **Success Banner**
   - Green banner confirms: “User created successfully”.
   - Option to View user is available.

  
 **Console Sign-In Details**
  - Sign-in URL: A unique AWS console link for the user.
  - User name: Prod-Analyst.mike




  - Console password: Masked for security, with an option to reveal.

  
**Important Note**
  
   - This is the only time the password can be viewed or downloaded. AWS does not store it for later retrieval.

     
 **Actions Available**
  
  - Email sign-in instructions: Sends credentials and sign-in link to the user.
  - Download .csv file: Exports credentials for secure storage or onboarding documentation.This option is selected
  - Cancel or Return to users list: Ends the workflow or navigates back

#### **Locating the Credential File**
- **Action:** Navigates to the `Downloads` folder in File Explorer.**See File Explorer image above**
- **Select:** The file `Prod-Analyst.mike_credentials.xlsx` 
- **Implication:** This suggests the user is preparing to access **Product analyst role**, specifically for the user `Prod-Analyst.mike
`.

