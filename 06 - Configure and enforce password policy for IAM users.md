## Configure and enforce password policy for IAM users



 <img src="https://i.imgur.com/CTGIgEr.png" height="100%" width="100%" />                                                                               




##  AWS IAM Password Policy Configuration – Step-by-Step

###  1. Navigate to IAM Account Settings
- From the **AWS Console**, go to the **IAM (Identity and Access Management)** service.
- In the **left-hand navigation menu**, locate and click **Account settings** under the **Access management** section.

###  2. Review Current Password Policy
- The **main content panel** displays the current **Password policy**.
- Key default settings visible:
  - **Minimum length**: 8 characters
  - **Character mix requirement**: At least 3 of the following:
    - Uppercase letters (A–Z)
    - Lowercase letters (a–z)
    - Numbers (0–9)
    - Non-alphanumeric characters (e.g., !, @, #)
  - **Password expiration**: Set to *Never expire*
  - **Identity check**: Password must not match AWS account name or email

###  3. Modify Password Policy
- Click the **Edit** button next to the Password policy section.
- This opens a form where you can:
  - Adjust minimum length
  - Toggle complexity requirements
  - Set expiration rules
  - Enforce identity-based restrictions


###  4. Dashboard Context
- The **IAM dashboard** on the left provides quick access to:
  - **User groups**, **Users**, **Roles**, **Policies**
  - **Identity providers** and **Root access management**
- This layout supports efficient navigation for managing access control across AWS resources.

   <img src="https://i.imgur.com/QgIXLzH.png" height="100%" width="100%" />     


### **Password Policy Configuration Steps**

#### 1. **Select Password Policy Type**
- **Option Chosen**: `Custom` (instead of IAM default)
- This unlocks granular control over password requirements.

#### 2. **Set Minimum Password Length**
- **Value**: `12 characters`
- AWS allows between 6 and 128 characters.
- Strong baseline for security without overwhelming users.

#### 3. **Enable Password Strength Requirements**
Each checkbox enforces a specific character type:
-  **Uppercase letter**: Latin alphabet (A–Z)
-  **Lowercase letter**: Latin alphabet (a–z)
-  **Number**: 0–9
-  **Non-alphanumeric character**:  
  Includes symbols like `! @ # $ % ^ & * ( ) _ + - = [ ] { } | '`

These selections ensure passwords are complex and resistant to brute-force attacks.

#### 4. **Configure Expiration Settings**
-  **Password Expiration Enabled**
- **Duration**: `90 days` (within AWS’s 1–1095 day range)
-  **Require Administrator Reset**
- Forces admin intervention post-expiration—ideal for tighter control.
-  **Allow Users to Change Their Own Password**
- Empowers users to manage credentials proactively.

#### 5. **Prevent Password Reuse**
-  **Remember Last 24 Passwords**
  - This is the **maximum** AWS allows.
  - Prevents cycling back to old passwords—excellent for long-term hygiene.

#### 6. **Finalize Changes**
- Bottom right options:
  -  `Save changes` to apply the policy
  -  `Cancel` to discard edits

                                                                                                                        
<img src="https://i.imgur.com/DRSEWl5.png" height="100%" width="100%" />  



1. **Initiation of Password Policy Update**
   - The user accesses the IAM dashboard, likely under a **Security Settings** or **User Management** section.
   - A prompt appears titled something like **“Set Custom Password Policy”**, indicating a configuration change is about to be made.

2. **Impact Notification**
   - The modal clearly states:  
     _“This will impact any new user creation and all the existing users changing their passwords.”_  
     This is a crucial compliance cue—highlighting that the change is **forward-facing** and **retroactive for password changes**.

3. **User Decision Point**
   - Two action buttons are presented:
   - **Cancel**: Aborts the operation.
   - **Set Custom**: Confirms and applies the new password policy.
   - This binary choice ensures clarity and prevents accidental enforcement.

4. **Confirmation Feedback**
   - Upon clicking **“Set Custom”**, a green notification bar appears at the bottom:
   -  “Password requirements for IAM users are updated.”
   - This toast-style alert confirms successful application of the new policy.

##    Verifying or Performing compliance checkthe on newly configured password policy settings.


                                            
<img src="https://i.imgur.com/JH0BqO4.png" height="100%" width="100%" />  



### Steps Taken in the AWS IAM Console

#### 1. **Navigating to IAM → Users → Add User**
- Accesse the AWS Management Console and entere the **IAM (Identity and Access Management)** section.
- TheN initiate the process to **create a new IAM user**.

#### 2. **Entering User Details**
- **Username entered**: `Test.User`
  - This is visible in the “User name” field.
  - AWS allows alphanumeric characters and certain symbols like periods (`.`), which are used here.

#### 3. **Selecting AWS Access Type**
- The checkbox for **“Provide user access to the AWS Management Console”** is selected.
  - This means the user will be able to log in to the AWS Console via a browser.
- The option **“I want to create an IAM user”** is selected.
  - This is the recommended choice for programmatic access and fine-grained permissions.

#### 4. **Setting Console Password**
- The user chose **“Custom password”** instead of auto-generating one.
  - This allows manual entry of a password for the new IAM user.

#### 5. **Password Policy Enforcement**
- An error message appears:  
  **“Password does not conform to the account password policy. It must be at least 12 characters long.”**
  - This indicates that the entered password is too short.
  - AWS enforces password policies set in the **Account Settings**, which may include:
    - Minimum length (e.g., 12 characters)
    - Character complexity (uppercase, lowercase, numbers, symbols)
    - Password expiration or reuse restrictions


###  Visual Cues & Dashboard Highlights

- The **red error message** is a visual alert that guides the user to correct the input.
- The **highlighted fields** (like the password input box) are bordered in red, signaling validation failure.






