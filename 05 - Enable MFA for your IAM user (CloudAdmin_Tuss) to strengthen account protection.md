###  Add or Enable Multi-Factor Authentication (MFA) for your IAM user (`CloudAdmin_Tuss`) using the AWS Console:


<img src="https://i.imgur.com/WOZAgr5.png" height="100%" width="100%" /> 

###  Enable MFA via IAM Dashboard Security Recommendation

####  Step 1: Open the IAM Dashboard
- Go to your AWS Console:  
  `https://3743********.signin.aws.amazon.com/console`
- Navigate to **IAM** from the AWS services menu.

####  Step 2: Locate the Security Recommendation
- On the **IAM Dashboard**, find the **Security recommendations** panel.
- You’ll see:  
  **“Add MFA for yourself”** → Click the **“Add MFA”** link or button next to it.


<img src="https://i.imgur.com/XkT0vla.png" height="100%" width="100%" /> 

####  Step 3: Choose MFA Device Type
- Select **Virtual MFA device** (recommended for most users).
-  Select MFA Device
This is the first configuration stage where the user defines the MFA device type and its identifier.
- Device Name Entered:
- Value: Device@Admin
- Purpose: This name becomes part of the device’s Amazon Resource Name (ARN), helping uniquely identify it.
- Constraints: Up to 64 characters, allowing letters, numbers, and symbols like @, =, ., -, _.
-  MFA Device Type Selected:
- Chosen Option: Authenticator app 
- Other Options Available:
- Passkey or Security Key: Uses biometric or screen lock via FIDO2.
- Hardware TOTP Token: Uses a physical device generating time-based codes.
- Why Authenticator App selected ? It’s widely supported, easy to set up, and doesn’t require physical hardware.
-  Action Taken:
- The user has selected the Authenticator app radio button.
- The Next button is highlighted, indicating readiness to proceed to Step 2.
- Click **Next**.





####  Step 4: Set Up Virtual MFA
- Open your authenticator app (e.g., **Authy**, **Google Authenticator**, **Microsoft Authenticator**).
- Select Google Authenticator

- ### Configure Google Authenticator on a phone

<img src="https://i.imgur.com/a14Pw9H.jpeg" height="30%" width="30%" /> 


###  Android Users
- **Download Location**: **Google Play Store**
- **Access**: Pre-installed on most Android devices; also accessible via [play.google.com](https://play.google.com) to download the Google Authenticator app
  
### iPhone Users
- **Download Location**: **Apple App Store**
- **Access**: Pre-installed on all iOS devices; also accessible via [apps.apple.com](https://apps.apple.com) to download the Google Authenticator app
  
-Then click the Get started button at the bottom to proceed with the configuration


<img src="https://i.imgur.com/6FX612U.png" height="30%" width="30%" /> 



###  Key Google Authenticator configuration steps

| **Step** | **Action** | **Purpose** |
|---------|------------|-------------|
| 1️ | Launch Google Authenticator | Begin setup for two-factor authentication |
| 2 | Show Google account (`therockcyberarmory001@gmail.com`) | Offer to sync codes with this account |
| 3 | Present two options:  **Continue as therockcyberarmory** **Use without an account** | Choose between cloud backup or offline-only use |


<img src="https://i.imgur.com/d5BsYHu.jpeg" height="30%" width="30%" /> 

<img src="https://i.imgur.com/eBHUt3N.jpeg" height="30%" width="30%" /> 


 **App Opened**:The **Google Authenticator** app on a mobile device is lunched

**No Codes Present**: The app currently shows **no authentication codes** saved or configured.

 **Prompt to Add**: There's a visible **"Add a code"** button, suggesting the next step is to manually add or scan a QR code to begin using the app for two-factor authentication (2FA).

<img src="https://i.imgur.com/kirlqUp.png" height="50%" width="50%" /> 

Use the Google Authenticator in your phone to scan the QR code on  the  AWS dashboard in your computer to initiate  two-factor authentication (2FA).

<img src="https://i.imgur.com/4jfz5l6.png" height="50%" width="50%" /> 

First code gererated  by the **Google Authenticator** app

<img src="https://i.imgur.com/jbcRxKp.png" height="50%" width="50%" />

Second code gererated  by the **Google Authenticator** app


<img src="https://i.imgur.com/VOFaGXv.jpeg" height="100%" width="100%" />

- Scan the QR code displayed.
- Enter **two consecutive MFA codes**  generated from the Google Authenticator app to verify.

####  Step 5: Complete Setup
- Click on Add MFA
- Once verified, MFA will be enabled for your IAM user (`CloudAdmin_Tuss`).
- You’ll now be prompted for an MFA code at each login.


###    Alternatively configuration using "My Security Credentials"

####  1. Navigate to "My Security Credentials"
- From the **IAM Dashboard**, locate the **Quick Links** section.
- Click on **“My security credentials”** — this takes you directly to your user’s credential management page.

####  2. Locate the MFA Section
- On the **Security Credentials** page, scroll to the **Multi-Factor Authentication (MFA)** section.
- You’ll see the current status (likely “Not assigned” if MFA isn’t set up yet).

####  3. Click “Assign MFA Device”
- Choose **“Assign MFA device”** to begin the setup.
- AWS will prompt you to select the type of MFA device:
  - **Virtual MFA device** (e.g., Authy, Google Authenticator)
  - **U2F security key** (e.g., YubiKey)
  - **Other hardware MFA device**

####  4. Set Up a Virtual MFA Device (Recommended)
- Select **Virtual MFA device** and click **Continue**.
- Open your authenticator app on your phone.
- Scan the **QR code** displayed on the AWS console.
- Enter **two consecutive MFA codes** from your app to verify.

#### 5. Confirm and Save
- Once verified, AWS will confirm that MFA is successfully enabled.
- You’ll now see the MFA status updated to “Assigned.”


###  Bonus Tips for Security
- **Enable MFA for the root user** too (via “Root access management” in the sidebar).
- Consider enforcing MFA across your organization using IAM policies or AWS Organizations.


###    The IAM user CloudAdmin_Tuss successfully logs in using Multi-Factor Authentication (MFA) following its configuration.


<img src="https://i.imgur.com/KnZMSAM.png" height="50%" width="50%" />

Code generated from Google Authenticator in the phone


<img src="https://i.imgur.com/DvyW4Mm.png" height="100%" width="100%" />                                                          

###  IAM User Sign-In 
- **Account ID or alias entered**: `3743********`
- **IAM username entered**: `CloudAdmin_Tuss`
- **Password entered**: (hidden with asterisks)
- **Options selected**: "Remember this account" checkbox is visible; "Show Password" option is available but not selected
- **Next action**: Clicked the **Sign in** button

###  MFA Verification 
- **MFA prompt displayed**: Indicates the account is protected by multi-factor authentication
- **MFA code entered**: `452608`
- **Next action**: Clicked the **Sign in** button again to complete authentication


<img src="https://i.imgur.com/0CcYEFl.png" height="100%" width="100%" />      

CloudAdmin_Tuss successfully logs into the AWS interface using Multi-Factor Authentication (MFA) 
