
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

After creation, the new user (e.g., `CloudAdmin_Tuss`) appears in the list with details like MFA status, password age, and last activity.

---

Want this turned into a visual checklist or onboarding snippet for your documentation? I can help sketch that out next.

