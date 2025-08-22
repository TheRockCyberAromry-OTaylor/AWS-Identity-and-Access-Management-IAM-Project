## Configure and enforce password policy for IAM users



 <img src="https://i.imgur.com/5rrrWa8.png" height="100%" width="100%" />                                                                               




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

---

## 🧠 Bonus Tips for Documentation
- Use platform icons (e.g., 🔐 for security, 🧭 for navigation) to enhance clarity.
- Consider adding screenshots with callouts for each step.
- Highlight branding elements like “THE ROCK CYBER ARMORY” to reinforce organizational identity.

Would you like help turning this into a branded visual guide or markdown template for your workflow library?
