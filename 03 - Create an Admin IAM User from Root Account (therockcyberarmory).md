###  The Root User therockcyberarmory creating a an ADMIN USER


<img src="https://i.imgur.com/SIaJ1xw.png" height="100%" width="100%" />  

The image shows the AWS Management Console in the Identity and Access Management (IAM) section, specifically under the **"Users"** tab. 

 **Summary of Actions and Status:**
 
- The IAM dashboard was accessed, focusing on user management.
- No IAM users have been created yet — the main panel displays **"No resources to display."**
- The account currently logged in is **"therockcyberarmory"**, visible in the top-right corner.
- Options to **"Create user"** and **"Delete"** are available, indicating readiness to begin user provisioning.

###  Steps to Create a New IAM User

Clicking "Create user" will launch a guided setup. 
- Specify User Details Enter a username (e.g., developer01, admin-temp, etc.). , Choose AWS credential type , Permissions, Tags (Optional),Review & Create and Retrieve Password


<img src="https://i.imgur.com/sCsii5i.png" height="100%" width="100%" />    


###  User Creation  configuration Specifics
- **User Name**: `CloudAdmin_Tuss` was typed in
- **Access Type**: AWS Management Console access is being configured.
- **User Type Selection**:
  - Option chosen: **“I want to create an IAM user”** (instead of using Identity Center)

###  Console Password Settings
- **Password Type**: Custom password entered (with option to show password)
- **Password Reset Requirement**: Checkbox selected for “Users must create a new password at next sign-in” (recommended)

### Additional Notes
- There's a mention of **programmatic access** options via:
  - Access keys
  - Service-specific credentials (e.g., AWS CodeCommit, Amazon Keyspaces)                This setup is tailored for creating a traditional IAM user with console access and secure password practices. 

###  Select Next to proceed


<img src="https://i.imgur.com/xKai2Mc.png" height="100%" width="100%" /> 


#### **Step 1: Specify User Details**
- This step is completed prior to the screenshot.
- Typically includes entering the username and selecting access type (e.g., programmatic access, AWS Management Console access).

#### **Step 2: Set Permissions** *(Current Step in Screenshot)*

1. **Choose Permission Assignment Method**
    
   -  **Attach policies directly**  was selected
     (Other options available: Add user to group, Copy permissions from existing user)

3. **Select Policy to Attach**  
   From the list of AWS managed policies, the following was selected:  
   -  **AdministratorAccess**  
     - Grants full access to AWS services and resources.
     - Marked as a "job function" policy.

4. **View and Filter Policies**  
   - Search bar and filters are available to narrow down policy options.
   - Other visible policies include:
     - AccessAnalyzerServiceRolePolicy
     - AdministratorAccess-Amplify

5. **Additional Controls Available**  
   - Option to **Create a new policy** if needed.
   - Option to set **Permissions boundary** (not used in this step).
  
    ### Select Next to proceed


<img src="https://i.imgur.com/TwF2da7.png" height="100%" width="100%" /> 


###  Step-by-Step Summary: IAM User Creation

#### **Step 1: User Details**
- **User name**: `CloudAdmin_Tuss`
- **Console access**: Enabled
- **Password type**: Custom password set
- **Password reset required**: Yes (user must change password at next sign-in)

#### **Step 2: Permissions**
- **Attached policies**:
  - `AdministratorAccess` – AWS managed policy granting full access
  - `IAMUserChangePassword` – AWS managed policy allowing user to change their own password

#### **Step 3: Tags (Optional)**
- No tags added
- Option to add key-value tags for identification or billing purposes remains available

#### **Step 4: Review & Create**
- All configurations are reviewed
- Buttons available:
  - `Previous` – to go back and edit
  - `Cancel` – to discard the process
  - `Create user` – to finalize and provision the IAM user.This was selected to proceed


<img src="https://i.imgur.com/AZxSRMD.png" height="100%" width="100%" /> 


###  IAM User Creation Workflow (as shown in the image)

1. **Specify User Details**
   - Entered a username: `CloudAdmin_Tuss`
   - Selected AWS Management Console access

2. **Set Permissions**
   - Assigned permissions (not visible in the image, but typically involves attaching policies or adding to groups)

3. **Review and Create**
   - Reviewed all settings and confirmed creation

4. **Retrieve Password**
   - AWS confirms successful user creation with a green banner
   - Console sign-in URL is provided
   - Password is generated (hidden by default, with option to reveal)
   - Options available:
     -  Email sign-in instructions
     -  Download credentials as a `.csv` file
     -  Return to users list or cancel

This final screen is crucial for securely capturing the user's initial credentials. AWS won't show the password again, so downloading or emailing it is best practice.


<img src="https://i.imgur.com/hk5Twqe.png" height="100%" width="100%" /> 

###  Confirmation and Feedback
- Received a green banner: “User created successfully.”
- Option to click “View user” to inspect or modify user settings.
- User Listed in IAM Table
- The new user "CloudAdmin_Tuss" now appears in the Users list.
- Columns show metadata like:
- MFA status
- Password age
- Console last sign-in
- Account age

